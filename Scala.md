<img src="http://img.rmb520.com/test/mywechat.jpg" width="200px"><img src="http://img.rmb520.com/test/mypublic.jpg" width="240px">

# 一 Scala入门与基础

## 1 Scala的简介和应用

### 何为Scala

Scala 是 Scalable Language 的简写，是一门多范式的编程语言。

Scala 是将函数式编程与面向对象相结合的语言。

### Scala的关键特性

- 面向对象特性

- 支持命令式风格和函数式风格

- 自适应静态类型

- 简洁性

- 基于事件的并发模型

- 能与Java很好的兼容


### Scala应用

- Scala包含Java所有功能

  - 客户端应用程序

  - WEB应用，如Lift 框架和Play 框架
  - 大数据，如Spark、Flink等
- Scala还能shell一样，作为脚本语言

- Scala与Java无缝调用




## 2 Scala环境配置和安装

Scala是基于Java之上，大量使用Java的类库和变量，使用 Scala 之前必须先安装 Java（>1.5版本）。

环境准备

JDK1.8+Scala2.12.x

###  Scala在window安装

Scala的安装步骤(window平台)

1.安装JDK（java环境）

​	JDK1.8+，参考安装教程：https://zhuanlan.zhihu.com/p/644577172

2.下载和安装Scala

​	下载地址：http://www.scala-lang.org/downloads

​	安装步骤：一直下一步

3.配置环境变量

| **变量**     | **值 (举例)**                           |
| ------------ | --------------------------------------- |
| %SCALA_HOME% | c:\Progra~1\Scala  (修改自己的安装目录) |
| %PATH%       | %PATH%;%SCALA_HOME%\bin                 |



## 3 Scala的编译和运行

 Scala与Java的编译

### Scala的编写

​	Using REPL

​		Scala REPL（“Read-Evaluate-Print-Loop”）是一个交互式的命令行解释器。
  win+r 快捷键

```
$ scala
Welcome to Scala 2.13.16 (OpenJDK 64-Bit Server VM, Java 1.8.0_342).
Type in expressions for evaluation. Or try :help.

scala> _
```

```
scala> 1 + 1
val res0: Int = 2

scala> val x = 10
x: Int = 10

scala> val y = "Hello World"
y: String = Hello World

scala> println("Hello World!")
Hello World!
```

​		

​	Using an IDE.

​	在 VS Code 中

![img](https://docs.scala-lang.org/resources/images/scala3-book/intellij-worksheet.png)

​	在 IntelliJ 中

![img](https://docs.scala-lang.org/resources/images/scala3-book/metals-worksheet.png)

### Scala的主要运行方式

​	Using the command line.（命令行）

​		Java也可以在命令行上运行代码，具体是通过javac命令来编译写好的Java类，然后通过java命令运行编译好的这个类对应的class文件，Scala也是同样的方式，只是Scala使用的命令和Java不同。

```java
//创建文件 HelloWorld.java(文件名需与类名一致), 
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

```shell
$ javac HelloWorld.java
$ java HelloWorld
```

```
        javac               java
.java --------> .class ----------> run on JVM
.scala -------> .class ----------> run on JVM
        scalac              scala
```

​	Using REPL（Scala解释器）

​		在REPL中可以一边编写Scala程序，一边运行Scala程序。

​	Using an IDE.（集成开发环境：比如IntelliJ IDEA、Eclipse等）

​		也就是说既可以使用IDE开发程序，也可以直接在IDE上运行开发好的程序

### Scala的跨平台

![image-20250225011133649](http://img.rmb520.com/test/image-20250225011133649.png)

###  Scala程序的入口

​	•定义object，并实现main方法

​	•定义object，继承App特质

###  Scala编译和运行

#### 课程案例-编译与运行

**案例名称：HelloWorld案例的编译与运行**（21页）

​	需求描述：在控制台输出HelloWorld

​	使用技能：scalac、scala

```scala
//Scala的程序启动入口
//1 定义object，继承App特质
object HelloWorld extends App{
	println("person hello word !")
}
```

```scala
//2 定义object，并实现main方法
object HelloWord {
  def main(args: Array[String]): Unit = {
    println("hello world")
  }
}
```



```
//编译
C:\work\scala>scalac HelloWorld.scala

C:\work\scala>dir
//运行
C:\work\scala>scala HelloWorld
person hello word !

//反编译 scalap
C:\work\scala>scalap HelloWorld
object HelloWorld extends scala.AnyRef with scala.App {
  def this() = { /* compiled code */ }
}

C:\work\scala>scalap HelloWorld$

C:\work\scala>scalap HelloWorld$delayedInit$body
```

###  Scala的REPL命令

| use:help for a list of commands.                      |
| ----------------------------------------------------- |
| use:load to load a file of REPL input.                |
| use:paste to enter a class and object as  companions. |
| :quit  to  exit the interpreter                       |

#### 课程案例-REPL命令交互编程

​	**案例名称：使用REPL命令交互编程**（30页）

​	需求描述：熟悉常见的REPL命令和编程技巧

​	使用技能：REPL命令和Scala基础

```scala
C:\Users\fighting>scala
Welcome to Scala 2.12.20 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_431).
Type in expressions for evaluation. Or try :help.

scala> val x,y=1
x: Int = 1
y: Int = 1

scala> x+y
res0: Int = 2

scala> val a = Array(1,2,3)
a: Array[Int] = Array(1, 2, 3)

scala> a.sum
res1: Int = 6

scala> a.getClass
res2: Class[_ <: Array[Int]] = class [I

scala> val s = "hello world"
s: String = hello world

scala> s.
*                     concat             grouped               minBy                 segmentLength   toFloat

scala> s.sum
res3: Char = ?

scala> s.c
scala> val a = "4"
a: String = 4

scala> a.to
to          toBuffer      toDouble       toInt        toList        toMap   toShort    toTraversable

scala> a.toIn
toIndexedSeq   toInt

scala> a.toInt
   def toInt: Int

scala> a.toInt
   def toInt: Int

scala> a.toInt
res4: Int = 4

scala> 4.to
to               toByte   toDegrees   toFloat       toInt    toOctalString   toShort

scala> 4.toInt
res5: Int = 4
```

**//todo** 33页

#### REPL常见命令应用

```
C:\Users\fighting\Desktop\test>scala
scala> new Register()

C:\Users\fighting\Desktop>scala
Welcome to Scala 2.12.20 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_431).
Type in expressions for evaluation. Or try :help.

scala> new Register()
<console>:12: error: not found: type Register
       new Register()
           ^
           
scala> :load ./test/test.scala

scala> new Register()
res1: Register = Register@7645e64

C:\Users\fighting\Desktop>scala -cp ./test

scala> new Register()
res0: Register = Register@78479f2b
```



## 4 Scala的基础语法

###  Scala的标识符(identifier)

•标识符定义：

​	•标识符是用户编程时使用的名字，用于给变量、常量、函数、语句块等命名，以建立起名称与使用之间的关系

•注意事项:

​	•不能以数字开头，不能是Scala中的关键字。 

### 关键字和注释

 Scala与Java的关键字

![image-20250201235311045](http://img.rmb520.com/test/image-20250201235311045.png)

Scala代码中注释

- 和java一样
- `//` 单行注释
- `/* */` 多行注释
- `/** */` 文档注释，方法或者类前面，便于`scaladoc`生成文档。

注释作用:解释说明程序，提高程序的可读性。

### Scala分号

分号是表达式的分隔符，Scala自动推断分号。

#### **课程示例**（42）

一行编写多个表达式

```scala
val s = "hello"; println(s)
```

x=1，y=2 求z=x+y

Z与x+y在一行 

Z与x+y分多行

**先进入粘贴模式（:paste）**

```scala
val x =1
var y=2

var z1=x+y
val z2=x
+y
val z3=x+
y
val z4=(x
+y)

println("z1=" + z1) //3
println("z2=" + z2) //1
println("z3=" + z3) //3
println("z4=" + z4) //3
```

```scala
val x=1
var y=2
val z =
x+y

def out(s:String)={
	println("String = " + s)
}
out("scala")
```

编写一个方法，要求调用对象与方法不在一行

```scala
class Person {
    def sayHello(){println("hello scala")}
}
new Person().
sayHello()
```

### Scala变量

•变量声明

​	•var:声明可变变量

​	•val:声明不可变变量,常量,相当于Java中final修饰的变量;

•变量的类型声明

​	• var 变量名：类型

​	•val 变量名：类型

```scala
var name [:VariableType] = value // variable
val name [:ConstantType] = value // constant
```

•声明多变量

​	val|var 变量1,变量2,... =变量值

- 声明变量时，类型可以省略，编译器会自动推导。
- 静态类型，类型经过给定或推导确定后就不能修改。
- 变量和常量声明时，必须有初始值。
- 变量可变，常量不可变。
- 引用类型常量，不能改变常量指向的对象，可以改变对象的字段。
- **建议能用常量就不要用变量。**

#### **课程案例**（45页）

分别使用val和var定义一个变量name

使用val同时声明多个变量

```scala
scala> val name = "scala"
name: String = scala

scala> name = "java"
<console>:12: error: reassignment to val
       name = "java"
            ^

scala> var name = "scala"
name: String = scala

scala> name = "java"
name: String = java

scala> val a,b = 3
a: Int = 3
b: Int = 3

scala> var x,y = "scala"
x: String = scala
y: String = scala

scala> var name = "scala"
name: String = scala

scala> name = 2
<console>:12: error: type mismatch;
 found   : Int(2)
 required: String
       name = 2
              ^
```

### Scala变量内存结构

![image-20250225013907683](http://img.rmb520.com/test/image-20250225013907683.png)

#### **课程示例**（47页）

定义一个数组array，数组里有scala、java和go三个字符串，用两种方式实现下面要求：

将数组array里面的字符串改为python、rust和c三个字符串

```scala
C:\Users\Administrator\Desktop>scala
Welcome to Scala 2.12.20 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201).
Type in expressions for evaluation. Or try :help.

scala> val array = Array("java","scala","go")
array: Array[String] = Array(java, scala, go)

scala> array = Array("python","go","rust")
<console>:12: error: reassignment to val
       array = Array("python","go","rust")
             ^

scala> array(0) = "python"

scala> array
res1: Array[String] = Array(python, scala, go)

scala> array(1) = "go"

scala> array(2) = "rust"

scala> array
res4: Array[String] = Array(python, go, rust)

scala> var array = Array("java","scala","go")
array: Array[String] = Array(java, scala, go)

scala> array = Array("python","go","rust")
array: Array[String] = [Ljava.lang.String;@4c24c40a

scala> array
res5: Array[String] = Array(python, go, rust)	
```

### Scala的lazy变量

•Scala的lazy变量：在使用时才被赋值

•Scala的lazy变量语法

​	•lazy val 变量名

####  **课程案例**（49页）

演示Scala的lazy变量的惰性求值。

```scala
scala> var name = "shf"
name: String = shf

scala> lazy val name="scala"
name: String = <lazy>

scala> name
res11: String = scala

scala> lazy var name="df"
<console>:1: error: lazy not allowed here. Only vals can be lazy
       lazy var name="df"
```

### 编程题：（51页）

Scala编写一个注册类，含有用户名和密码两个属性，要求：
   （1）用户名不可修改；
   （2）密码可修改。
在REPL分别输出原始信息(用户名和密码)和修改后的信息。

```scala
class Register {
  val username = "scala"
  var password = "abc123"
}
```

REPL命令参考33页常见命令的应用

```
C:\Users\Administrator>scala
Welcome to Scala 2.12.20 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201).
Type in expressions for evaluation. Or try :help.

scala> class Register(val username:String, var password:String){ }
defined class Register

scala> var user = new Register("jack","123")
user: Register = Register@6889f56f

scala> user.username
res0: String = jack

scala> user.password
res1: String = 123

scala> user.username = "lucy"
<console>:12: error: reassignment to val
       user.username = "lucy"
                     ^

scala> user.password = "456"
user.password: String = 456

scala> user.password
res2: String = 456
```

# 二 Scala数据类型与基本运算

## Scala的数据类型

变量的数据类型的作用

- 限制一个变量能被赋予的值和这些数值的操作

- 限制一个表达式可产生的值


Scala数据类型的分类

- 数值类型
- 非数值类型

### Scala支持的数据类型

| **数据类型** | **描述**                                                     |
| ------------ | ------------------------------------------------------------ |
| Byte         | 8位有符号补码整数。数值区间为 -128 到 127                    |
| Short        | 16位有符号补码整数。数值区间为 -32768 到 32767               |
| Int          | 32位有符号补码整数。数值区间为 -2147483648 到  2147483647    |
| Long         | 64位有符号补码整数。数值区间为  -9223372036854775808 到 9223372036854775807 |
| Float        | 32 位, IEEE 754 标准的单精度浮点数                           |
| Double       | 64 位 IEEE 754 标准的双精度浮点数                            |
| Char         | 16位无符号Unicode字符, 区间值为 U+0000 到  U+FFFF            |
| String       | 字符序列                                                     |
| Boolean      | true或false                                                  |
| Unit         | 表示无值，和其他语言中void等同。用作不返回任何结果的方法的结果类型。Unit只有一个实例值，写成()。 |
| Null         | null 或空引用                                                |
| Nothing      | Nothing类型在Scala的类层级的最底端；它是任何其他类型的子类型。 |
| Any          | Any是所有其他类的超类                                        |
| AnyRef       | AnyRef类是Scala里所有引用类(reference  class)的基类          |



<img src="https://i-blog.csdnimg.cn/blog_migrate/b070a09e65dd230ff43749d51cbe2ce8.png" width="750px">

### 数值类型

Scala的基本类型**与Java的基本类型对应的取值区间完全相同**，使得Scala编译器可以在产生的字节码中将Scala的值类型转成Java的基本类型。

![image-20250129181622273](http://img.rmb520.com/test/image-20250129181622273.png)



```scala
scala> val a = 3
a: Int = 3

scala> val a = 3L
a: Long = 3

scala> val a = 06
<console>:1: error: Decimal integer literals may not have a leading zero. (Octal syntax is obsolete.)
       val a = 06
               ^
scala> val d=1.2
d: Double = 1.2

scala> val a = 1.2f
a: Float = 1.2

scala> val d=1.2d
d: Double = 1.2

scala> val a=true
a: Boolean = true

scala> val s='fhg
s: Symbol = 'fhg

scala> s.
equals   hashCode   name   toString

scala> s.name
res6: String = fhg

scala> 3.toDouble
res7: Double = 3.0

scala> 3.to
to               toByte   toDegrees   toFloat       toInt    toOctalString   toShort
toBinaryString   toChar   toDouble    toHexString   toLong   toRadians       toString

scala> 3.toLong
res8: Long = 3

scala> 3.toHexString
res9: String = 3

scala> 1.2.toInt
res2: Int = 1
```

4）Scala中的字面量

在Scala中，如果在编译的时候变量的值就可以确定的话，那么此时的变量值就是一个字面量。

Scala中常见的字面量有以下几种。

- 整型字面量：Scala中不支持八进制和以0开头的字面量，但Java中是支持八进制字面量的。

- 浮点字面量：Float型加F或f；Double型加D或d。

- 符号字面量：符号字面量是Scala中特有的一种类型，表示方法为'identifier，其中identifier是由数字、字母或下划线组成的标识符，但第一个字符不能是数字。

- 布尔字面量：true或false。

- 字符字面量的表示

  Scala中的字符字面量可以用以下两种方法表示。

  1. 直接通过“单引号+单字符”的形式表示，例如'a'、'A'等。
  2. 直接使用“单引号+Unicode编码值”的形式表示，格式为'\uXXXX'，其中XXXX是十六进制值，uXXXX部分可出现在Scala解释器的任意位置。

- 转义字符

  Scala和Java中都有一些表示空格、换行这样的特殊字符，当我们需要使用这些特殊字符时，就需要添加反斜杠“\”对它进行转义。我们把这种特殊字符称为转义字符，Scala中常见的转义字符：\t \n \r \\ \" \'`

  | **特殊字符** | **Unicode编码值** | **描述**                             |
  | ------------ | ----------------- | ------------------------------------ |
  | \t           | \u0009            | 水平制表（HT），跳到下一个Tab位置    |
  | \n           | \u000a            | 换行（LF），将当前位置移到下一行开头 |
  | \r           | \u000d            | 回车（CR），将当前位置移到本行开头   |
  | \\"          | \u0022            | 代表一个双引号（"）字符              |
  | \ \'         | \u0027            | 代表一个单引号（'）字符              |
  | \\\          | \u005c            | 代表一个反斜线字符 '\'               |

```scala
scala> val a = 'A'
a: Char = A

scala> 'A' + 1
res10: Int = 66

scala> 'A'.toInt
res11: Int = 65

scala> 'A'.toBinaryString
res12: String = 1000001

scala> a.toInt
res5: Int = 65

scala> val f = '\u0041'
f: Char = A

scala> val \u0041\u0042C = 2
ABC: Int = 2
```

### 非数值类型

Scala主要非数值类型

- String

- Collection

- Class

- Null

- Nothing


Scala的字符串可用双引号和三个引号表示

- “内容”
- """ 内容""" 
  1. 可以创建多个字符串；
  2. 可以包含单引号和双引号等转义字符。


#### 课程案例（60页）

按照要求在REPL上输出以下内容：

1. 输出hello scala字符串

2. 输出“hello scala”字符串

3. 输出 \hello scala\字符串


```scala
C:\Users\Administrator>scala
Welcome to Scala 2.12.20 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201).
Type in expressions for evaluation. Or try :help.

scala> println("hello scala")
hello scala

scala> println("\"hello scala\"")
"hello scala"

scala> println("\\hello scala\\")
\hello scala\

scala> println(""" "hello scala" """)
 "hello scala"

scala> println(""" \hello scala\ """)
 \hello scala\
```

#### Scala的字符串方法

字符串的常用方法

| **方法**                                             | **作用**                                                     |
| ---------------------------------------------------- | ------------------------------------------------------------ |
| char  charAt(int index)                              | 返回指定位置的字符                                           |
| int  indexOf(int ch)                                 | 返回指定字符在字符串中第一次出现处的索引                     |
| boolean  matches(String regex)                       | 告知此字符串是否匹配给定的正则表达式                         |
| String  replaceAll(String regex, String replacement) | 使用给定的replacement替换此字符串所有匹配给定的正则表达式的子字符串 |
| String[]  split(String regex)                        | 根据给定正则表达式的匹配拆分此字符串                         |
| Boolean  startsWith(String prefix)                   | 测试此字符串是否以指定的前缀开始                             |

•Scala字符串的分隔符：Scala的分隔符与Java的String方法类相似

```scala
scala> "hello,world".split(",")
res16: Array[String] = Array(hello, world)
```

5）使用正则表达式对象查找字符串

字符串的查找：

- Regex.findAllIn(String)：找出字符串String中**所有匹配**正则表达式的值并返回，其返回值有多个，是一个迭代器。
- Regex.findFristIn(String)：找到字符串String中**第一个匹配**正则表达式的值并返回，其返回值是一个Option对象。

创建正则表达式对象：

- "正则表达式".r
- new Regex(正则表达式)

```scala
scala> val regex="""(\d\d\d\d)-(\d\d)-(\d\d)""".r
regex: scala.util.matching.Regex = (\d\d\d\d)-(\d\d)-(\d\d)

scala> val result = regex.findAllIn("2015-03-20, 1985-11-24, 2019-1-2")
result: scala.util.matching.Regex.MatchIterator = <iterator>

scala> for(date<-result) println(date)
2015-03-20
1985-11-24

scala> val result = regex.findFirstIn("2015-03-20, 1985-11-24, 2019-1-2")
result: Option[String] = Some(2015-03-20)
```

Scala字符串的替换：利用正则表达式匹配一段字符串，然后替换。

- String.replaceAll（regex，替换的内容）
- regex.replaceAllIn（String，替换内容）
- String.replaceFirst(regex，“替换的值”)
- regex.replaceFirstIn（String，替换内容）

#### 课程示例

#### 按要求操作字符串“his basic salary is 10000，and bonus is 20000 ”

1. 将 basic salary的数字用*代替
2. 将salary 和bonus用*替换

```scala
scala> val s = "his basic salary is 10000，and bonus is 20000"
s: String = his basic salary is 10000，and bonus is 20000

scala> val regex = """\d{5}"""
regex: String = \d{5}

scala> s.replaceFirst(regex,"***")
res0: String = his basic salary is ***，and bonus is 20000

scala> val res = s.replaceFirst(regex,"***")
res: String = his basic salary is ***，and bonus is 20000

scala> res
res1: String = his basic salary is ***，and bonus is 20000

scala> val res = s.replaceAll(regex,"***")
res: String = his basic salary is ***，and bonus is ***

scala> res
res2: String = his basic salary is ***，and bonus is ***
```

####  Scala的字符串的遍历

for循环

​	 for{x <- String } {do something}

foreach 

​	 String.foreach（c=> do something ）

map

​	 String.map（c=> do something ）

#### Scala返回新的字符串

for循环/yield

​	for(x <- String ) { do something } [ yield x ]

foreach

​	String.foreach（c => do something ）

map

​	String.map（c => do something ）

#### 课程案例（67页）

使用三种方式遍历字符串scala。

```scala
scala> val name ="scala"
name: String = scala

scala> for(x<-name)println(x)
s
c
a
l
a

scala> name.foreach(x=>println(x))
s
c
a
l
a

scala> name.map(x=>println(x))
s
c
a
l
a
res39: scala.collection.immutable.IndexedSeq[Unit] = Vector((), (), (), (), ())
```

#### 课程案例（68页）

使用三种方式将字符串scala的每一个字符转成大写。

```scala
C:\Users\Administrator>scala
Welcome to Scala 2.12.20 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201).
Type in expressions for evaluation. Or try :help.

scala> val name = "scala"
name: String = scala

scala> name.map( x=>x.toUpper)
res0: String = SCALA

scala> val s = for(x<-name) yield x.toUpper
s: String = SCALA

scala> val sb = new StringBuilder()
sb: StringBuilder =

scala> name.foreach( x=> sb.append(x.toUpper)  )

scala> sb
res2: StringBuilder = SCALA

scala> name
res3: String = scala
```



#### 案例名称：字符替换（70页）

需求描述：身份证210404197681232113后四位用*代替。

```scala
scala> val iden = "210404197681232113"
iden: String = 210404197681232113

scala> val subiden = iden.substring(iden.length-4)
subiden: String = 2113

scala> val result = iden.replaceAll(subiden,"****")
result: String = 21040419768123****

scala> result
res0: String = 21040419768123****
```



#### 课后作业

1. 提取字符串“123456”偶数部分，返回一个新字符串。
2. 判断身份证号s是否是北京省份证。
3. 将字符串'123456'变成‘234567’

```scala
//利用正则表达式匹配偶数字符（0, 2, 4, 6, 8）
scala> val s = "123456"
s: String = 123456

scala> val regex = "[24680]".r
regex: scala.util.matching.Regex = [24680]

scala> val result = regex.findAllIn(s)
result: scala.util.matching.Regex.MatchIterator = <iterator>

scala> val r = for(x<-result) println(x)
2
4
6
r: Unit = ()

scala> var sb = new StringBuilder
sb: StringBuilder =

scala> result.foreach(x=>sb.append(x))

scala> sb
res25: StringBuilder = 246

scala> result
res27: scala.util.matching.Regex.MatchIterator = <iterator>
//mkString 方法主要用于将集合（如数组、列表、序列等）中的元素转换为一个字符串
scala> val result = regex.findAllIn(a).mkString
result: String = 246
```

```scala
//根据身份证号码判断是否为北京地区的身份证，可以通过提取身份证号码的前两位数字来实现。
//中国大陆身份证号码的前两位代表省份代码，其中“11”对应北京市
scala> val s = "11324223929922992xx"
s: String = 11324223929922992xx

scala> val subiden = s.substring(0,2)
subiden: String = 11

scala> val subiden = s.substring(0,2).toInt
subiden: Int = 11

scala> subiden == 11
res46: Boolean = true

scala> val s = "211324223929922992xx"
s: String = 211324223929922992xx

scala> val subiden = s.substring(0,2).toInt
subiden: Int = 21

scala> subiden == 11
res47: Boolean = false
```

```scala
//将字符串 '123456' 变成 '234567'，本质上是将每个字符（数字）加1
 val s = "123456"
s: String = 123456
//asDigit 是 Char 类型的一个方法，用于将字符转换为其对应的数字值
scala> val newS = s.map(c => (c.asDigit + 1).toString).mkString
newS: String = 234567
//将字符转换为字符串，然后使用 toInt 方法。
scala> val res = s.map(x=>x.toString.toInt+1).mkString
res: String = 234567
//在 ASCII 码表中，数字字符 '0' 到 '9' 是连续的，因此可以通过减去 '0' 的 ASCII 值来将字符转换为对应的数字。
//'5' - '0' 的结果是 5，因为 '5' 的 ASCII 值是 53，'0' 的 ASCII 值是 48，相减后得到数字 5。
scala>  s.map(x=> x-'0'+1 ).mkString
res24: String = 234567
```

####  Scala的字符串插值

Java拼接字符串

- ​	String name=“scala”
- ​	 “his name is”+name


Scala字符串的插值

- ​	S插值: 表示s" " 例子: s“his name is $name” 

- ​	f插值: 表示 f" "例子: f“his name is $name” 

- ​	raw插值:表示raw" "例子: raw“his name is $name” 


#### 课程案例（72页）

假设已经定义好了姓名、年龄和体重的三个变量（name=jason,age=10,weight =180），并且这些变量是不能改变的，现要求分别输出以下四项字符串：

1.  name is Jason, 10 years old and weighs is 180 kg

2.  name is Jason, 10 years old and weighs is 180.00 kg

3.  name is Jason, 10 years old and weighs is 180.00 kg\n1000g

4.  are you 10 ?true/false（年龄是10岁就输出true，否则输出false）

```scala
//Java的拼接方式

```



#### 案例名称：主机名匹配（74）

需求描述：比较用户输入的主机名hadoop01是否在已知字符串str=“host01,host03,hadoop01,hadoop010”存在，如果存在打印，find 主机名，否则打印unfind 主机名(不区分大小写)

```scala
scala> val input = "hadoop01"
input: String = hadoop01

scala> val hostsList = "host01,host02,hadoop01,hadoop010"
hostsList: String = host01,host02,hadoop01,hadoop010

scala> val hosts=hostsList.split(",")
hosts: Array[String] = Array(host01, host02, hadoop01, hadoop010)

scala> val hostsname = for(host<-hosts if(input.toUpperCase==host.toUpperCase)) yield host
hostsname: Array[String] = Array(hadoop01)

scala> if(hostsname.length>0) println(s"i find $input") else println(s"i unfind $input")
i find hadoop01

scala> val input = "hadoop"
input: String = hadoop

scala> val hostsname = for(host<-hosts if(input.toUpperCase==host.toUpperCase)) yield host
hostsname: Array[String] = Array()

scala> if(hostsname.length>0) println(s"i find $input") else println(s"i unfind $input")
i unfind hadoop
```



### Scala的基本运算

内置运算符

- 算术运算符

- 关系运算符

- 逻辑运算符

- 位运算符

- 赋值运算符

•Scala 的算术运算本质

- +相当于调用 对应类型的 +方法
- -相当于调用 对应类型的 -方法
- *相当于调用 对应类型的 *方法
- / 相当于调用 对应类型的 /方法
- % 相当于调用 对应类型的 %方法

举例写出前缀、中缀和后缀操作符对应的方法调用。(77)

```scala
scala> 1+2
res2: Int = 3

scala> 1.+(2)
res3: Int = 3

scala> 4/2
res4: Int = 2

scala> 4./(2)
res5: Int = 2

scala> val s = "hello,scala"
s: String = hello,scala

scala> val words=s.split
split   splitAt

scala> val words=s.split(",")
words: Array[String] = Array(hello, scala)

scala> for(word<-words)println(word)
hello
scala

scala> val words = s split
split   splitAt

scala> val words = s split ","
words: Array[String] = Array(hello, scala)

scala> for(word<-words)println(word)
hello
scala

scala> -2
res8: Int = -2

scala> val a = -2
a: Int = -2

scala> 2.unary_
unary_+   unary_-   unary_~

scala> 2.unary_-
res9: Int = -2

scala> 2.unary_+
res10: Int = 2

scala> 2.unary_
unary_+   unary_-   unary_~

scala> 2.unary_~
res11: Int = -3

scala> :paste
// Entering paste mode (ctrl-D to finish)

class operator {def getName(){println("scala")}}

new operator().getName()

// Exiting paste mode, now interpreting.

scala
defined class operator

scala> :paste
// Entering paste mode (ctrl-D to finish)

class operator {def getName(){println("scala")}}
new operator() getName()

// Exiting paste mode, now interpreting.

scala
defined class operator
```



### Scala的数据类型和运算的应用

Scala的相等性

- Scala的“==”用来判断比较双方的值是否相等，与Java不同。
- Scala判断相等性的null不会抛异常

#### 课程练习(88页)

```scala
scala> :paste
// Entering paste mode (ctrl-D to finish)

val s1="hello"
val s2="'he"+"llo"
val s3="he"
val s4="llo"
val s5=s2+s3
val s6=new String("hello")
println(s1==s2) ; println(s1==s5)
println(s1==s6) ; println(s5==s6)
println(s1 eq s2);  println(s1 eq s5)
println(s1 eq s6);  println(s5 eq s6)

// Exiting paste mode, now interpreting.

false
false
true
false
false
false
false
false
s1: String = hello
s2: String = 'hello
s3: String = he
s4: String = llo
s5: String = 'hellohe
s6: String = hello
```

#### Scala的++和--

Scala没有++和--这样的操作符，可用如下操作符代替。

- ++：Scala用赋值符号+=代替++
- --：Scala用赋值符号-=代替--

#### Scala的浮点数精度解决

•比较两个浮点数的值，和其他语言一样，由于浮点数精度的问题

 两个应该相等的浮点数实际可能不相等。

- 设置一定精度
- 利用BigDecimal

```scala
scala> 0.1+0.2 == 0.3
res18: Boolean = false

scala> 0.1+0.2
res19: Double = 0.30000000000000004
```

```scala
scala> BigDecimal
res20: math.BigDecimal.type = scala.math.BigDecimal$@a520a55

scala> BigDecimal(0.1)+BigDecimal(0.2) == BigDecimal(0.3)
res21: Boolean = true
```

```scala
def compare(x:Double,y:Double,p:Double)={
     if((x-y).abs<p) true else false
}
```

```scala
scala> val a=0.3
a: Double = 0.3

scala> val b=0.1+0.2
b: Double = 0.30000000000000004

scala> def compare(x:Double,y:Double,p:Double)={
     |      if((x-y).abs<p) true else false
     | }
compare: (x: Double, y: Double, p: Double)Boolean

scala> compare(a,b,0.00001)
res0: Boolean = true

scala> compare(a,b,0.00000000000000000000000000001)
res1: Boolean = false
```



#### Scala处理大数。(93)

- BigDecimal 
- **BigInt****：**Int如果超过范围，会报错，而BigInt解决这类问题。

```scala
scala> Int.MaxValue
res14: Int = 2147483647

scala> Long.MaxValue
res15: Long = 9223372036854775807

scala> val bigint=BigInt("234939297372372382838732734238237823234")
bigint: scala.math.BigInt = 234939297372372382838732734238237823234

scala> val bigint=BigInt("234939297372372382838732734238237823234") * BigInt(2)
bigint: scala.math.BigInt = 469878594744744765677465468476475646468

scala> BigDecimal(12.1).toInt
res16: Int = 12
```



####  Scala生成随机数

Scala可以生成随机数和随机字符

- 生成一个Radndom对象：scala.util.Random

  - 随机整数

  - 随机小数

  - 随机字符

- 随机种子：产生伪随机序列

#### 课程练习(95页)

1. 生成0-100的伪随机序列，序列含三个元素。
2. 创建一个随机长度的集合(由数字组成，元素最多5个)
3. 创建一个随机长度的集合(由字符组成，元素最多10个)
4. 创建一个长度为8的序列，要求里面的字符是随机的

```scala
//生成0-100的伪随机序列，序列含三个元素。
scala> val r = scala.util.Random
r: util.Random.type = scala.util.Random$@7d6a0a50

scala> r.setSeed(10)

scala> r.nextInt(101)
res26: Int = 48

scala> r.nextFloat
res28: Float = 0.25780278

scala> r.nextDouble
res29: Double = 0.4129126974821382

scala> val r1=scala.util.R
Random   Right

scala> val r1=scala.util.Random
r1: util.Random.type = scala.util.Random$@7d6a0a50

scala> r1.setSeed(10)

scala> r1.nextInt(101)
res31: Int = 48

scala> r1.nextFloat
res33: Float = 0.25780278

scala> r1.nextDouble
res34: Double = 0.4129126974821382
```

```scala
//创建一个随机长度的集合(由数字组成，元素最多5个)
scala> for(i<-1 to r.nextInt(6)) yield r.nextInt(30)
res35: scala.collection.immutable.IndexedSeq[Int] = Vector(7, 28, 21, 4)
```

```scala
//创建一个随机长度的集合(由字符组成，元素最多10个)
scala> for(i <- 1 to r.nextInt(11)) yield r.nextPrintableChar
res41: scala.collection.immutable.IndexedSeq[Char] = Vector(I, m)
```

```scala
//创建一个长度为8的序列，要求里面的字符是随机的
scala> for(i <- 1 to 8) yield r.nextPrintableChar
res44: scala.collection.immutable.IndexedSeq[Char] = Vector(4, K, =, S, 8, g, W, z)
```



# 三 Scala内建控制、类和对象

### Scala的idea环境搭建

Idea+Scala的环境

​	JDK1.8+

​	Scala2.12.x

​	Scala插件

安装步骤

​	安装JDK1.8+

​	安装Scala2.12.x

​	Scala插件

​		在线安装

​		离线安装: http://plugins.jetbrains.com/plugin/1347-scala/versions

​	Idea配置

### Scala的内建控制

Scala的常见内建控制结构

​	顺序结构：程序的执行顺序

​	分支结构：if

​	循环结构:for和while

### Scala的类和构造器

 Scala类的定义

类分类

​	普通类

​	匿名类

​	内部类

​	抽象类 

类成员

构造器/辅助构造器

属性

方法

类

对象 

### Scala的伴生类和对象

 Scala的单例对象

Scala的单例对象声明    

​	object identifier{ 

​	

​	}

Scala的单例对象

​	不是一个类型

​	不能new

​	不能传递参数

# 四 Scala自适应类型和函数

Scala的自适应类型

 Scala的特殊类型

Nothing

​	所有类型的子类

​	抽象类

​	没有任何值

Nothing的作用

​	帮助Scala的类型推断

###  Scala的元组类型

Scala字面量：Scala的特殊类型，它是不同类型值的集合。

元组的表示

​	(元素1, 元素2, ...元素N)  

​	new TupleN(元素1, 元素2, ...元素N)  

元组的访问

​	Tuple_INDEX

元组的遍历 

​	Tuple.productIterator() 

### Scala的函数基础

### Scala的函数进阶

Scala的函数字面量语法

​	（参数列表）=>{方法体}

Scala的函数字面量作用

​	变量

​	参数

Scala的函数字面的简化

​	_

​	只有一个表达式，可省略括号

Scala的函数字面量的懒加载

​	lazy

### Scala的高阶函数

Scala的高阶函数定义

高阶函数是指使用其他函数作为参数、或者返回一个函数作为结果的函数。在Scala中函数是“一等公民”，所以允许定义高阶函数。这里的术语可能有点让人困惑，我们约定，使用函数值作为参数，或者返回值为函数值的“函数”和“方法。  

Scala的常见高阶函数   

​	map

​	flatten

​	flat

​	map

​	foreach

​	reduce

​	filter

​	fold

# 五 Scala继承和多态

### Scala的继承

继承定义在原有类基础上定义一个新类，原有类父类，新类子类。

继承的好处

​	复用代码

​	实现多态

继承的语法

​	extends

调用父类构造器语法

```
class Dog(name:String,age:Int) extends Animal(name,age)
```

辅助构造器调用

父类的辅助构造器可以被子类的主构造器调用

父类的辅助构造器不能子类的辅助构造器调用

#### Scala的多态

多态

​	在执行期间而非编译期间确定所引用对象的类型，根据实际类型调用其方法。

多态的作用

​	当子类继承父类，不同子类需要实现自己的行为。

多态的实现手段

​	重写

#### Scala的继承

方法的继承

​	子类继承父类的行为

方法的重写

​	当子类继承父类，从父类继承的方法不能满足要求时，子类需要有自己的行为。

方法重写语法

​	override

### Scala的继承关系

Scala继承的层级关系

![image-20250120012020395](/Users/zhangwei/Library/Application Support/typora-user-images/image-20250120012020395.png)

### Scala的抽象类

Scala的抽象类定义

​	抽象类是一个不能被实例化的类。

Scala的抽象类的语法

​	abstract

Scala的抽象类成员

​	成员属性

​	方法

Scala何时使用抽象类

​	基类构造器参数Java的调用

基类定义属性的重写

​	非抽象val非抽象var抽象val和var

### Scala的trait

Scala的特质

Scala的特质定义

```
Trait identified {

}
```

Scala的特质作用

​	封装成员和方法抽象类接口

Scala的特质语法

​	`extends  A with B`

trait的几种用法  

​	只有抽象方法的trait

​	只有抽象成员和方法的trait

​	具体成员的变量和方法

​	对象继承特质

# 六  Scala权限和集合

## 1 Scala的访问权限

- Scala的访问权限
  - 属性成员
  - 方法
  - 构造器
- Scala的属性和构造函数访问权限
  - 默认访问权限
  - protected访问权限
  - private访问权限
  - private[this]访问权限

### 2 Scala的包和导入

#### Scala的包

- Scala的包定义
  - 解决类的命名冲突和类的文件管理
- Scala包的语法
  - package name
  - package name{   }
- Scala包的作用域
  - Private[包名]
  - protected[包名]

#### Scala的包的导入

- Scala的导入语法
  - import
- 导入成员重命名
  - Import {A=>a}
- 导入成员隐藏类
  - Import {A=>_,_}

### 3 Scala的集合

Scala的集合继承关系

![92a9c8a443d35ace3cb252282b7b504](http://img.rmb520.com/test/92a9c8a443d35ace3cb252282b7b504.png)

scala.collection

![image-20250120014009577](http://img.rmb520.com/test/image-20250120014009577.png)

scala.collection.mutable

![image-20250120014032567](http://img.rmb520.com/test/image-20250120014032567.png)

scala.collection.immutable

![image-20250120014043340](http://img.rmb520.com/test/image-20250120014043340.png)

- Scala的集合的一致性
- Traversable(1, 2, 3)
-  Iterable("x", "y", "z") 
- map("x" -> 24, "y" -> 25, "z" -> 26) 
- Set(Color.red, Color.green, Color.blue) 
- SortedSet("hello", "world") 
- Buffer(x, y, z) 
- IndexedSeq(1.0, 2.0)
- LinearSeq(a, b, c)



### 4 Scala的迭代器

- 迭代器
  - Scala Iterator（迭代器）不是一个集合，它是一种用于访问集合的方法
- 迭代器使用
  - while (it.hasNext) 
  - println(it.next())

迭代器常用方法

| **序号** | **功能** | **主要方法**                    |
| -------- | -------- | ------------------------------- |
| 1        | 抽象方法 | it.next()/it.hasNext            |
| 2        | 复制     | it.duplicate                    |
| 3        | 转换     | it.toXX（List、Set等）          |
| 4        | 拷贝     | it copyToArray/it copyToBuffer  |
| 5        | 拉链方法 | it zip jt等                     |
| 6        | 子迭代器 | it dropWhile p/it slice (m,n)等 |
| 7        | maps     | map/flatmap等                   |

# 七 Scala的Seq 

Scala的seq

Scala的集合

- Scala的Traversable
  - 集合的顶端特质
  - 只有一个抽象方法foreach
- Scala的Iterable
  - 方法是用iterator来定义的，作用是交出集合的每个元素

Scala的集合常见操作

- Scala的集合元素的获取
  - head
  - last
  - find 
- Scala的集合遍历
  - For
  - Foreach
  - 迭代器
- Scala的集合视图
  - view

Scala的Seq

Scala的Seq继承关系

![image-20250120014546096](http://img.rmb520.com/test/image-20250120014546096.png)



Scala的List

- Scala的List的构建
  - Nil::
- Scala的List的类型
  - List[T]
- Scala的List的lazy
  - Stream
- Scala的List的可变
  - Listbuffer
- Scala的List的基本操作
  - /：或：\
  - zipped

Scala的Vector

Scala的Vector

​	不可变IndexSeq

# 八 Scala映射和模式匹配

## 1 Scala的Set

Scala的Set继承关系

![image-20250120014826911](http://img.rmb520.com/test/image-20250120014826911.png)

- Scala的Set
  - 无序不重复
- Scala的常用操作

| **分类**     | **描述**                   |
| ------------ | -------------------------- |
| 条件操作     | 判断集合是否包含元素/子集  |
| 加法         | 向集合添加元素             |
| 减法         | 移除集合中的元素           |
| 二元逻辑操作 | 两个集合的交集、并集和差集 |
| 更新         | 更新集合的元素             |

## 2 Scala的map

Scala的map继承关系

![image-20250120014947462](http://img.rmb520.com/test/image-20250120014947462.png)

- Scala的map
  - 键值对的集合
- Scala的map的创建
  - map（k1->v1,k2->v2,…）
  - map（(k1,v1),(k2,v2),…）
- Scala的map分类
  - 可变
  - 不可变
- Scala的可变map常用操作

| **分类** | **描述**          |
| -------- | ----------------- |
| 添加     | M(k)=v,+=,++=,put |
| 更新     | M(k)=v            |
| 删除     | Remove,-=,--=     |
| 查询     | Get（key）,m(key) |
| 遍历     | For/foreach       |

Scala的不可变map常用操作

| **分类** | **描述**          |
| -------- | ----------------- |
| 添加     | +,+=              |
| 更新     | 不能              |
| 删除     | -=,-              |
| 查询     | Get（key）,m(key) |
| 遍历     | For/foreach       |

## 3 Scala的集合性能

## 4 Scala的模式匹配

# 九 Scala隐式转换和Java交互

## 1 Scala的隐式转换

- Scala的隐式转换定义
  - 自动将一种类型转换另一种类型
- Scala的隐式转换声明
  - implicit
- Scala的隐式转换函数
  - Implicit def 函数名
- Scala的隐式转换函数名
  - 隐式转换与函数名无关
  - 与函数签名有关
- Scala的隐式类
  - Implicit class 类名（参数）{  }

## 2 Scala的隐式转换规则

- Scala的隐式规则
  - 显示定义
  - 无歧义规则
  - 定义域规则
  - 不能多次转换原则

## 3 Scala与Java环境搭建

- Scala的环境准备
  - IDEA
  - JDK1.8+
  - Scala2.1x
  - Maven3.3.9

## 4 Scala与Java交互

- Scala的调用Java集合
  - 只要符合Scala，可直接调用
- Java调用Scala集合
  - 只要符合Java，可直接调用

| **Scala**             | **符号** | **Java**                           |
| --------------------- | -------- | ---------------------------------- |
| Iterator              | <=>      | java.util.Iterator                 |
| Iterator              | <=>      | java.util.Enumeration              |
| Iterator              | <=>      | java.util.Collection               |
| Iterator              | <=>      | java.lang.Iterable                 |
| mutable.Buffer        | <=>      | java.util.List                     |
| mutable.Set           | <=>      | java.util.Set                      |
| mutable.map           | <=>      | java.util.map                      |
| mutable.Concurrentmap | <=>      | java.util.concurrent.Concurrentmap |

# 十 Scala类型参数

## Scala的泛型

- 泛型定义
  - 参数化类型：所有操作的数据类型被指定为一个参数
- 类与类型
  - 一 一对应
  - 泛型导致一个类对应多个类型
- Scala泛型应用
  - 类
  - 特质 
  - 函数
- Scala泛型语法
  - []
- Scala泛型类
  - class 类名[T](参数)
  - class 类名[S,T…](参数)
- Scala泛型Trait
  - trait 类名[T]
  - trait 类名[S,T…]
- 泛型类和特质
- Scala泛型函数
  - def 方法名[S,T](参数列表){ }
- Scala函数泛型使用
  - 方法名[S,T](参数列表)
  - 方法名(参数列表)泛型类和特质
- Scala泛型函数
  - def 方法名[S,T](参数列表){ }
- Scala函数泛型使用
  - 方法名[S,T](参数列表)
  - 方法名(参数列表)定义一个方法，将一个数组的元素拷贝到一个List集合

## Scala的泛型界定

- Scala的界定
- 上下界界定
- 视图界定
- 上下文界定
- 多重界定

## Scala的型变

- Scala的型变
  - 不变协变逆变
- Scala的不变定义
  - 当类型S是类型T的子类型时，则A[S]与A[T]不存在子类关系。
- Scala的协变语法
  - A[T]
- Scala的逆变定义
  - 当类型S是类型T的子类型时，则A[T]可以认为是A[S]的子类型。也就是被参数化类型的泛化方向与参数类型的方向是相反的。
- Scala的逆变语法
  - A[-T]

## Scala的高级类型

自学
