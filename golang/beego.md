# Beego v1 ORM 教程

Beego ORM 是一个强大的Go语言ORM 库，支持多种数据库（MySQL、PostgreSQL、SQLite 等），提供了类似Django ORM的使用体验。以下是其核心功能和用法的详细介绍：

## 1. 模型定义

```go
type User struct {
    Id       int    `orm:"pk;auto"`       // 主键自增
    Username string `orm:"size(50)"`
    Email    string `orm:"size(100);unique"`
    Created  time.Time `orm:"auto_now_add;type(datetime)"`
}

func (u *User) TableName() string { return "users" } // 自定义表名

func init() {
    orm.RegisterModel(new(User))   // 注册模型
    orm.RunSyncdb("default", false, true)	// 自动建表（开发环境）
}
```

## 2. 模型标签说明

- `pk`：主键
- `auto`：自动增长
- `size`：字段长度
- `null`：允许为空
- `unique`：唯一约束
- `index`：索引
- `rel(fk)`：外键关联
- `reverse(many)`：反向关联

## 3、插入

```go
o := orm.NewOrm()

// 单条
user := User{Username: "Alice", Email: "alice@test.com"}
id, err := o.Insert(&user)               // 返回自增 ID
fmt.Println("插入 ID:", id)               // [^55^][^56^]

// 批量
users := []User{
    {Username: "Bob", Email: "bob@test.com"},
    {Username: "Cindy", Email: "cindy@test.com"},
}
nums, _ := o.InsertMulti(2, users)
fmt.Println("批量插入条数:", nums)
```

## 4. 查询

```go
// 按主键读取
u := User{Id: 1}
err := o.Read(&u)        // SELECT * FROM users WHERE id = 1

// 条件查询
var users []User
_, err = o.QueryTable("user").
    Filter("username__contains", "A").
    OrderBy("-id").
    Limit(10, 0).        // LIMIT 10 OFFSET 0
    All(&users)

// 分页示例
total, _ := o.QueryTable("user").Count()
_, _ = o.QueryTable("user").
    Limit(size, (page-1)*size).
    All(&users)          // 
```

## 5. 更新

```go
// 全字段更新（主键必须有值）
u := User{Id: 1}
_ = o.Read(&u)
u.Email = "new@example.com"
num, _ := o.Update(&u)              // UPDATE users SET ... WHERE id = 1

// 只更新指定字段
num, _ = o.Update(&u, "Email")      // [^55^][^56^]
```

## 6. 删除

```go
u := User{Id: 1}
num, _ := o.Delete(&u)              // DELETE FROM users WHERE id = 1
fmt.Println("删除行数:", num)         // [^56^]
```

## 7. 事务示例

```go
o := orm.NewOrm()
_ = o.Begin()

user := User{Username: "TxUser", Email: "tx@test.com"}
_, err := o.Insert(&user)
if err != nil {
    o.Rollback()
    return
}
_ = o.Commit()                      // 
```

## 8. 一对多 / 一对一关联

```go
type Profile struct {
    Id   int    `orm:"pk"`
    Age  int
    User *User  `orm:"reverse(one)"` // 反向一对一
}

type Post struct {
    Id   int
    Title string
    User *User `orm:"rel(fk)"`      // 外键
}
```

使用时：

```go
// 关联查询
var user User
_ = o.QueryTable("user").
    RelatedSel("Profile"). // 预加载
    Filter("Id", 1).
    One(&user)
```

## 9.表结构自动迁移

```go
// 开发环境自动建表
// 在init函数中调用
orm.RunSyncdb("default", false, true)
```

- 第 2 个参数：强制删除再建表（生产勿用）。
- 第 3 个参数：打印 SQL。

## 10.调试与日志

```go
// 启用ORM调试模式
orm.Debug = true

// 设置日志输出
orm.DebugLog = orm.NewLog(os.Stdout)
```

## 11. 常用命令行

```bash
bee run          # 热重载
bee api appname  # 生成 RESTful 骨架
bee generate model user -fields="username:string,email:string"
bee generate controller user  # 创建控制器
bee new demo     # 生成项目骨架
bee pack  # 打包可执行二进制 + 静态文件
```

## 📌 小结

| 功能     | 调用方式                        |
| -------- | ------------------------------- |
| 插入单条 | `o.Insert(&obj)`                |
| 批量插入 | `o.InsertMulti(n, slice)`       |
| 查询单条 | `o.Read(&obj)`                  |
| 条件查询 | `o.QueryTable().Filter().All()` |
| 分页     | `.Limit(size, offset)`          |
| 事务     | `o.Begin()/Commit()/Rollback()` |
| 关联     | `orm:"rel/reverse"`             |
| 自动迁移 | `RunSyncdb()`                   |

照此速查表，**半天即可用 Beego V1 ORM 跑完 CRUD**，如需进阶（分页、缓存、乐观锁、原生 SQL）再深入官方文档或项目示例即可。