您好，Mycat 是一个开源的分布式数据库中间件，用于实现数据库的**分库分表**（Sharding）和**读写分离**，让用户像使用单个数据库一样使用集群。

下面为您提供一份 Mycat 教程，包括其基本概念、核心功能、部署和常用配置。

------

## 📚 Mycat 分布式数据库中间件教程

### 一、Mycat 核心概念

Mycat 的核心思想是**将一个大数据库拆分成多个小数据库**，并在中间件层面进行路由和管理。

| **概念**                  | **解释**                                                     |
| ------------------------- | ------------------------------------------------------------ |
| **逻辑库 (Schema)**       | Mycat 向客户端（如 Java 应用）暴露的数据库名。客户端连接 Mycat 时使用的库名。 |
| **逻辑表 (Table)**        | 客户端在逻辑库中看到的表。该逻辑表的数据可能分散在多个真实数据库中。 |
| **分片键 (Sharding Key)** | 用于决定一行数据应该存储到哪个真实数据库（分片）的字段，例如用户 ID (`user_id`)。 |
| **分片规则 (Rule)**       | 根据分片键的值计算出数据目标存储位置（DataNode）的算法。     |
| **节点 (DataNode)**       | Mycat 配置中定义的**数据存储单位**，映射到后端一个或多个真实数据库实例的库名。 |
| **后端数据库 (DataHost)** | 物理数据库实例（如 MySQL 服务器）。一个 DataHost 可以包含多个 DataNode。 |

### 二、Mycat 核心功能

1. **分库分表（数据分片 Sharding）：** 这是 Mycat 的主要功能。通过配置分片规则，将原本存储在一个数据库中的数据分散到多个独立的数据库实例中，实现**高并发**和**大数据量**存储。
2. **读写分离：** Mycat 可以将 SQL 语句自动路由到后端的主库（Master）进行写入操作，路由到从库（Slave）进行读取操作，减轻主库压力。
3. **多数据源管理：** 支持 MySQL、Oracle、SQL Server、PostgreSQL 等多种数据库作为后端存储。
4. **全局序列号（Sequence）：** 解决分布式环境下的 ID 自增问题，提供高性能、全局唯一的 ID 生成服务。
5. **跨分片查询/聚合：** 自动处理需要聚合多个后端数据库结果的查询（如 `GROUP BY`, `ORDER BY`）。

### 三、Mycat 部署与启动

#### 1. 部署环境要求

- **Java 环境：** Mycat 基于 Java 运行，需要安装 JDK 8 或更高版本。
- **后端数据库：** 准备至少一个（通常是两个或更多）MySQL 数据库实例作为后端存储。

#### 2. 关键启动命令

- **启动 Mycat：**

  Bash

  ```
  # 进入 Mycat 安装目录
  cd $MYCAT_HOME/bin
  # 启动 Mycat 服务（后台运行）
  ./mycat start
  ```

- **停止 Mycat：**

  Bash

  ```
  ./mycat stop
  ```

#### 3. 客户端连接测试

Mycat 默认端口为 **8066**。您可以使用任何 MySQL 客户端工具连接 Mycat：

Bash

```
mysql -u [用户名] -p[密码] -h [Mycat服务器IP] -P 8066
```

### 四、Mycat 核心配置文件详解

Mycat 的核心配置位于 `$MYCAT_HOME/conf/` 目录下，主要有以下三个文件：

#### 1. `server.xml` (Mycat 服务器配置)

定义 Mycat 实例本身的行为，如用户、权限、日志等。

| **标签/配置项** | **作用**                                             | **示例**                                     |
| --------------- | ---------------------------------------------------- | -------------------------------------------- |
| `<user>`        | 定义登录 Mycat 的用户和密码。                        | 配置应用连接 Mycat 的账号和密码。            |
| `<schema>`      | 定义 Mycat 暴露给客户端的逻辑数据库。                | `<schema name="dbtest" dataNode="dn1,dn2"/>` |
| `<system>`      | 定义 Mycat 的系统级参数，如 SQL 限制、查询最大行数。 | `maxCon="1000"` (最大连接数)                 |

#### 2. `schema.xml` (逻辑结构配置)

定义 Mycat 的**逻辑库、逻辑表、分片规则**和**后端 DataNode** 映射关系。这是 Mycat 最核心的配置文件。

| **标签/配置项**         | **作用**                                                 | **示例**                                                     |
| ----------------------- | -------------------------------------------------------- | ------------------------------------------------------------ |
| `<schema>`              | 映射逻辑库到 DataNode 集合。                             | `<schema name="dbtest" dataNode="dn1,dn2"/>`                 |
| `<table name="t_user">` | 定义逻辑表。                                             | `<table name="t_user" dataNode="dn1,dn2" rule="mod-long" primaryKey="user_id"/>` |
| `dataNode`              | 逻辑表数据分布在哪些 DataNode 上。                       | `dn1,dn2`                                                    |
| `rule`                  | 指定对该逻辑表应用的分片规则。                           | `mod-long` (使用取模分片规则)                                |
| `<dataNode>`            | 定义数据节点，将逻辑节点名映射到 DataHost 和真实数据库。 | `<dataNode name="dn1" dataHost="host1" database="db_01"/>`   |
| `<dataHost>`            | 定义后端数据库实例的连接信息（IP、端口、用户、密码）。   | `<dataHost name="host1" maxCon="100" balance="0">...</dataHost>` |

#### 3. `rule.xml` (分片规则配置)

定义所有可用的分片算法，供 `schema.xml` 中的逻辑表引用。

| **标签/配置项**                                              | **作用**                             | **示例**                                                |
| ------------------------------------------------------------ | ------------------------------------ | ------------------------------------------------------- |
| `<tableRule>`                                                | 定义一个分片规则的名称和使用的算法。 | `<tableRule name="mod-long">`                           |
| `<function name="mod-long" class="io.mycat.route.function.AutoPartitionByLong">` | 定义分片算法的 Java 实现类。         | `property name="partitionCount" value="2"` (分片数为 2) |

### 五、配置实战示例：用户表分片

假设目标是将 `t_user` 表根据 `user_id` 字段进行取模分片到两个 DataNode (`dn1`, `dn2`)，对应后端两个数据库 `db_01` 和 `db_02`。

1. **`schema.xml` 中定义 DataHost 和 DataNode：**

   XML

   ```
   <dataHost name="host1" maxCon="100" balance="0">
       <property name="url">192.168.1.10:3306</property>
       <property name="user">root</property>
       <property name="password">123456</property>
   </dataHost>
   <dataNode name="dn1" dataHost="host1" database="db_01" />
   <dataNode name="dn2" dataHost="host1" database="db_02" />
   <schema name="dbtest" dataNode="dn1,dn2" checkSQLschema="false">
       <table name="t_user" dataNode="dn1,dn2" rule="mod-rule" primaryKey="user_id"/>
   </schema>
   ```

2. **`rule.xml` 中定义取模分片规则：**

   XML

   ```
   <tableRule name="mod-rule">
       <rule>
           <columns>user_id</columns>
           <algorithm>func_mod</algorithm>
       </rule>
   </tableRule>
   <function name="func_mod" class="io.mycat.route.function.PartitionByMod">
       <property name="count">2</property> </function>
   ```

通过以上配置，当应用执行 `INSERT INTO t_user (user_id, name) VALUES (101, 'Alice');` 时，Mycat 会计算 `101 % 2 = 1`，将数据路由到 `dn2` 对应的后端数据库 `db_02` 中。

您希望进一步了解 Mycat 的**读写分离配置**或**全局序列号**的实现方法吗？