------



## Go 语言结构体 (Struct) 详解

在 Go 语言中，**结构体 (Struct)** 是一种**复合数据类型**。它让你能把多个不同类型的数据字段组合成一个单一的实体。你可以把它想象成一个蓝图或模板，用来创建具有特定属性（字段）的对象。这与其他编程语言中的类（Class）或结构体概念类似，但 Go 语言的结构体更轻量级，没有继承等面向对象特性。

### 1. 为什么用结构体？

假设你要存储一个“学生”的信息，学生可能包含姓名（字符串）、年龄（整数）、学号（字符串）和平均分（浮点数）。没有结构体的话，你可能需要定义四个独立的变量：

```go
var studentName string
var studentAge int
var studentID string
var studentScore float64
```

这样做不仅分散了相关数据，还使得管理和传递这些数据变得麻烦。而使用结构体，你可以把这些相关数据封装在一起，形成一个有意义的整体：

```go
type Student struct {
    Name    string
    Age     int
    ID      string
    Score   float64
}
```

这样，`Student` 类型就代表了一个学生的完整信息，更符合现实世界的概念。

### 2. 如何定义结构体？

使用 `type` 关键字和 `struct` 关键字来定义结构体：

```go
type 类型名 struct {
    字段名1 字段类型1
    字段名2 字段类型2
    // ...
}
```

**示例：**

```go
// 定义一个表示人的结构体
type Person struct {
    Name string // 姓名
    Age  int    // 年龄
    City string // 城市
}
```

字段标签 (Field Tags)：

你可以在结构体字段后面添加字段标签，它是一段字符串字面量，通常用于在结构体和其它数据格式（如 JSON、XML、数据库表字段）之间进行映射。

```go
type User struct {
    ID       int    `json:"user_id"`     // JSON 序列化时字段名为 user_id
    Username string `json:"username,omitempty"` // omitempty 表示如果字段为空则忽略
    Password string `json:"-"`           // - 表示在 JSON 序列化时忽略此字段
}
```

字段标签在反射时可以被读取，但它们本身不影响结构体字段的类型或值。

### 3. 如何创建和初始化结构体？

创建结构体变量（也称为结构体实例或对象）有多种方式：

- **零值初始化：** 声明一个结构体变量而不显式初始化时，所有字段都会被初始化为它们的**零值**（数字为 0，布尔为 false，字符串为 ""，引用类型为 nil）。

  ```Go
  var p1 Person // p1.Name="", p1.Age=0, p1.City=""
  fmt.Println(p1) // 输出: { 0 }
  ```
  
- **字段名-值对初始化（推荐）：** 这是最常用和推荐的方式，它清晰明了，且不受字段顺序变化的影响。

  ```Go
  p3 := Person{
      Name: "Bob",
      Age:  25,
      City: "London",
  }
  fmt.Println(p3) // 输出: {Bob 25 London}
  ```
  
- **使用 `new` 关键字（返回指针）：** `new` 会为结构体分配内存，并返回指向该内存地址的**指针**。所有字段都被初始化为零值。

  ```go
  p5 := new(Person) // p5 是一个 *Person 类型，指向一个 Person 零值实例
  p5.Name = "David" // 可以直接通过指针访问字段，Go 会自动解引用
  fmt.Println(*p5)  // 输出: {David 0 }
  ```

### 4. 如何访问结构体字段？

使用 **点操作符 `.`** 来访问结构体实例的字段。

```Go
var p Person
p.Name = "Eva"
p.Age = 28
p.City = "Paris"

fmt.Println("姓名:", p.Name)
```

如果结构体变量是一个**指针**，你也可以直接使用点操作符访问其字段，Go 会自动进行解引用。

```go
pPtr := new(Person)
pPtr.Name = "Frank" // 相当于 (*pPtr).Name = "Frank"
fmt.Println("姓名 (通过指针):", pPtr.Name)

p := &Person{Name: "Daisy", Age: 22}
fmt.Println(p.Name)  // 自动解引用，输出 Daisy
```



### 5. 结构体的特性

- **值类型：** 结构体是**值类型**。这意味着当你把一个结构体变量赋值给另一个变量，或者把结构体作为函数参数传递时，都会进行**值拷贝**。

  ```Go
p1 := Person{"Alice", 30, "New York"}
  p2 := p1 // p2 是 p1 的一个副本，修改 p2 不会影响 p1
  p2.Age = 31
  fmt.Println(p1.Age) // 输出 30
  fmt.Println(p2.Age) // 输出 31
  ```
  
  如果你希望传递结构体的引用，可以使用**指针**。

- **没有继承：** Go 语言的结构体没有传统的类继承概念。但可以通过**匿名字段 (Anonymous Fields)** 实现**组合 (Composition)**，从而获得类似继承的效果（方法和字段的“提升”）。

  ```Go
  type Employee struct {
      Person // 匿名字段，Employee 会“拥有”Person 的所有字段和方法
      Company string
  }
  
  e := Employee{
      Person:  Person{Name: "Grace", Age: 35, City: "Berlin"},
      Company: "Google",
  }
  fmt.Println(e.Name) // 直接访问 Person 的字段
  ```
  
- **方法：** 你可以为结构体定义**方法 (Methods)**。方法是绑定到特定类型（通常是结构体）的函数。

  ```go
  // 为 Person 结构体定义一个 SayHello 方法
  func (p Person) SayHello() {
      fmt.Printf("Hello, my name is %s and I am %d years old.\n", p.Name, p.Age)
  }
  
  // 为 Person 结构体定义一个 UpdateAge 方法 (接收者是指针类型，会修改原结构体)
  func (p *Person) UpdateAge(newAge int) {
      p.Age = newAge // 这里修改的是原结构体的 Age
  }
  
  p := Person{"Henry", 40, "Tokyo"}
  p.SayHello() // 输出：Hello, my name is Henry and I am 40 years old.
  
  p.UpdateAge(42)
  fmt.Println(p.Age) // 输出 42 (原结构体已改变)
  ```
  
  选择**值接收者**还是**指针接收者**取决于你是否需要在方法内部修改结构体实例的值。如果需要修改，应使用指针接收者。

------

Go 语言的结构体是组织数据的核心方式，它提供了一种清晰、高效且类型安全的方法来管理复杂的数据集合。理解其值类型特性、字段标签、方法和匿名字段（组合）对于编写高质量的 Go 代码至关重要。





