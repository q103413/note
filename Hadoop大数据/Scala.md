<img src="http://img.an520.com/test/mywechat.jpg" width="200px"><img src="http://img.an520.com/test/mypublic.jpg" width="240px">

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

```scala
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

![image-20250225011133649](http://img.an520.com/test/image-20250225011133649.png)

###  Scala程序的入口

​	•定义object，并实现main方法

​	•定义object，继承App特质

###  Scala编译和运行

**课程案例-编译与运行**

案例名称：HelloWorld案例的编译与运行（21页）

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



```scala
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

课程案例-REPL命令交互编程

​	案例名称：使用REPL命令交互编程（30页）

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

```scala
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

![image-20250201235311045](http://img.an520.com/test/image-20250201235311045.png)

Scala代码中注释

- 和java一样
- `//` 单行注释
- `/* */` 多行注释
- `/** */` 文档注释，方法或者类前面，便于`scaladoc`生成文档。

注释作用:解释说明程序，提高程序的可读性。

### Scala分号

分号是表达式的分隔符，Scala自动推断分号。

**课程示例**（42）

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

**课程案例**（45页）

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

<img src="http://img.an520.com/test/image-20250225013907683.png" width="600px">



**课程示例**（47页）

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

**课程案例**（49页）

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

编程题：（51页）

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

```scala
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

对比Scala和Java：

Java实现：

```java
package scala01;

public class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

Person p=new Person("scala",10)
p.getName() //scala
p.setName("java")
p.getName() //java
```

Scala实现：

```scala
scala> class Person(var name:String,var age:Int)
defined class Person

scala> val person=new Person("scala",10)
person: Person = Person@1722011b

scala> person.name
res0: String = scala

scala> person.age
res1: Int = 10

scala> person.name="java"
person.name: String = java

scala> person.name
res2: String = java
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

Scala的基本类型与**Java**的基本类型对应的取值区间完全相同，使得Scala编译器可以在产生的字节码中将Scala的值类型转成Java的基本类型。

<img src="http://img.an520.com/test/image-20250129181622273.png" width="500px">



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
  | \\ t         | \u0009            | 水平制表（HT），跳到下一个Tab位置    |
  | \\ n         | \u000a            | 换行（LF），将当前位置移到下一行开头 |
  | \ r          | \u000d            | 回车（CR），将当前位置移到本行开头   |
  | \\\"         | \u0022            | 代表一个双引号（"）字符              |
  | \\'          | \u0027            | 代表一个单引号（'）字符              |
  | \\           | \u005c            | 代表一个反斜线字符 '\'               |

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

**课程案例（60页）**

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

#### 课程示例（课后）

按要求操作字符串“his basic salary is 10000，and bonus is 20000 ”

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
//第二种方法
scala> val regex = """\d{5}""".r
regex: scala.util.matching.Regex = \d{5}

scala> regex.replaceFirstIn(s,"----")
res4: String = his basic salary is ----，and bonus is 20000

scala> regex.replaceAllIn(s,"____")
res5: String = his basic salary is ____，and bonus is ____
```

####  Scala的字符串的遍历

for循环

​	 for(x <- String ) {do something}

foreach 

​	 String.foreach（c => do something ）

map

​	 String.map（c=> do something ）

#### Scala返回新的字符串

for循环/yield

​	for(x <- String ) { do something } [ yield x ]

foreach

​	String.foreach（c => do something ）

map

​	String.map（c => do something ）

课程案例（67页）

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

课程案例（68页）

使用三种方式将字符串scala的每一个字符转成大写。

```scala
C:\Users\Administrator>scala
Welcome to Scala 2.12.20 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201).
Type in expressions for evaluation. Or try :help.

scala> val name = "scala"
name: String = scala

scala> name.map( x => x.toUpper)
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



案例名称：字符替换（70页）

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

```scala
scala> :paste
// Entering paste mode (ctrl-D to finish)

val sb = new StringBuilder()
val indexs = for(i<-iden.length-4 to iden.length) yield i
for(i<-0 to iden.length-1){ if(indexs.contains(i)) sb.append("*") else sb.append(iden.charAt(i))}

// Exiting paste mode, now interpreting.

sb: StringBuilder = 2156868666****
indexs: scala.collection.immutable.IndexedSeq[Int] = Vector(10, 11, 12, 13, 14)
```



#### 课后作业（课后）

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
//第二种方法
scala> for( x <- s; if(x%2 == 0) ) yield x

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

scala> val x = for(x<-a) yield x.toString.toInt+1;x.mkString
x: scala.collection.immutable.IndexedSeq[Int] = Vector(2, 3, 4, 5, 6, 7)
res3: String = 234567
```

####  Scala的字符串插值

Java拼接字符串

- ​	String name=“scala”
- ​	 “his name is” + name


Scala字符串的插值

- ​	S插值: 表示s" " 例子: s“his name is $name” 

- ​	f插值: 表示 f" "例子: f“his name is $name” 

- ​	raw插值:表示 raw" "例子: raw“his name is $name” 

**课程案例（72页）**

假设已经定义好了姓名、年龄和体重的三个变量（name=jason,age=10,weight =180），并且这些变量是不能改变的，现要求分别输出以下四项字符串：

1.  name is Jason, 10 years old and weighs is 180 kg

2.  name is Jason, 10 years old and weighs is 180.00 kg

3.  name is Jason, 10 years old and weighs is 180.00 kg\n1000g

4.  are you 10 ?true/false（年龄是10岁就输出true，否则输出false）

```scala
//Java的拼接方式

```



**案例名称：主机名匹配（74）**

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



## Scala的基本运算

- 和Java基本相同。
- scala中所有运算符本质都是对象的方法调用，拥有比C++更灵活的运算符重载。

内置运算符

- 算术运算符

- 关系运算符

- 逻辑运算符

- 位运算符

- 赋值运算符

#### Scala 的算术运算本质

- +相当于调用 对应类型的 +方法
- -相当于调用 对应类型的 -方法
- *相当于调用 对应类型的 *方法
- / 相当于调用 对应类型的 /方法
- % 相当于调用 对应类型的 %方法

**课程案例(77)**

举例写出前缀、中缀和后缀操作符对应的方法调用。

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

####  Scala的赋值运算

课程练习(83)

1. var a=2 ; var b=3;var c=4

   a+=b;b-=c ;c*=a 求 a b c的值

2. var a=2 ; var b=3;var c=4

   a=b=c 求 a b c的值

3. var a=2 ; var b=3 交换a和b的值

```scala
scala> var a=2
a: Int = 2

scala> var b=3
b: Int = 3

scala> var c=4
c: Int = 4

scala> a+=b

scala> a
res1: Int = 5

scala> b-=c

scala> b
res3: Int = -1

scala> c*=a

scala> c
res5: Int = 20
```

```scala
scala> var a=2
a: Int = 2

scala> var b=3
b: Int = 3

scala> var c=4
c: Int = 4

scala> a=b=c
<console>:14: error: type mismatch;
 found   : Unit
 required: Int
       a=b=c
          ^
```

```scala
scala> var a=2
a: Int = 2

scala> var b=3
b: Int = 3

scala> var tmp=0
tmp: Int = 0

scala> tmp=a
tmp: Int = 2

scala> a=b
a: Int = 3

scala> b=tmp
b: Int = 2

scala> a
res6: Int = 3

scala> b
res7: Int = 2

scala>
```

#### Scala 的位运算符

var a = 00000000

var b = 00000001

| **运算符** | **描述**       |
| ---------- | -------------- |
| &          | 按位与运算符   |
| \|         | 按位或运算符   |
| ^          | 按位异或运算符 |
| ~          | 按位取反运算符 |
| <<         | 左移动运算符   |
| >>         | 右移动运算符   |
| >>>        | 无符号右移     |

•Scala 的位运算法则

| **p** | **q** | **p  & q** | **p  \| q** | **p  ^ q** |
| ----- | ----- | ---------- | ----------- | ---------- |
| 0     | 0     | 0          | 0           | 0          |
| 0     | 1     | 0          | 1           | 1          |
| 1     | 1     | 1          | 1           | 0          |
| 1     | 0     | 0          | 1           | 1          |

运算符的优先级(86)

| **类别** | **运算符** | **关联性** |
| -------- | ---------- | ---------- |
| 1        | () []      | 左到右     |
| 2        | ! ~        | 右到左     |
| 3        | * / %      | 左到右     |
| 4        | + -        | 左到右     |
| 5        | >> >>> <<  | 左到右     |
| 6        | > >= < <=  | 左到右     |
| 7        | == !=      | 左到右     |

| 8    | &                                  | 左到右 |
| ---- | ---------------------------------- | ------ |
| 9    | ^                                  | 左到右 |
| 10   | \|                                 | 左到右 |
| 11   | &&                                 | 左到右 |
| 12   | \|\|                               | 左到右 |
| 13   | = += -= *= /= %= >>= <<= &= ^= \|= | 右到左 |
| 14   | ,                                  | 左到右 |

课程练习(87)

•5 ==5.0 

•97=='a’

•5>3 &&'6'＞１０

•4>=5 || 'C'>'a'

•4>=5 ^ 'c'>'a'

### Scala的数据类型和运算的应用

Scala的相等性

- Scala的“==”用来判断比较双方的值是否相等，与Java不同。
- Scala判断相等性的null不会抛异常

**课程练习(88页)**

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

Scala**没有**++和--这样的操作符，可用如下操作符代替。

- ++：Scala用赋值符号+=代替++
- --：Scala用赋值符号-=代替--

#### Scala的浮点数精度解决

•比较两个浮点数的值，和其他语言一样，由于浮点数精度的问题

 两个应该相等的浮点数实际可能不相等。

- 设置一定精度
- 利用BigDecimal

```scala
//91页
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
def compare(x:Double, y:Double, p:Double)={
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



**Scala处理大数。(93)**

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

**课程练习(95页)**

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

## Scala的idea环境搭建


安装步骤

- ​	安装JDK1.8+

- ​	安装Scala2.12.x

- ​        安装idea (https://www.jetbrains.com.cn/idea/)

- ​	Scala插件

  - 在线安装
  - 离线安装: http://plugins.jetbrains.com/plugin/1347-scala/versions


- ​	Idea配置

  - 项目结构->JDK+SDK

**Idea格式化代码的快捷键：**

- ‌**Mac系统**‌：按下`Cmd + Option + L`。
- ‌**Windows/Linux系统**‌：按下`Ctrl + Alt + L`。


## Scala的内建控制

- ​	顺序结构：程序的执行顺序

- ​	分支结构：if

- ​	循环结构:for和while

### Scala的顺序结构

```scala
 def main(args: Array[String]): Unit = {
  val name="scala"
  val age=10
  println("hello scala")
  println(name+"has been "+age)
｝
```

### Scala的分支结构

- **if**语句
- 模式匹配:match

**Scala的if语句有返回值，而Java语句if没有返回值**

据不同年龄，对人群进行分类，并返回实际年龄段字符串。

- 12岁以下，输出童年
- 12-20岁，输出青年
- 30-40，输出中年
- 40-50，输出壮年
- 50以上，输出老年

```scala
package scala03

object ClassifyPerson {
  def main(args: Array[String]): Unit = {
    val c = matchAge(20)
    println(c)
  }

  def matchAge(age:Int) = {
    var classify = if (age<12){
      "童年"
    }else if (age>=12 && age<30) {
      "青年"
    }else if (age>=30 && age<40) {
      "中年"
    }else if (age>=40 && age<50) {
      "壮年"
    }else {
      "老年"
    }
    classify
  }

}
```

### Scala的循环结构

- for
- while
- do while

**Scala的循环具有返回值，返回值都是空，也就是`Unit`实例`()`。**

`while`和`do while`：

- 为了兼容java，不推荐使用，结果类型是`Unit`。
- 不可避免需要声明变量在循环外部，等同于循环内部对外部变量造成了影响，所以不推荐使用。

```scala
var i = 1;
val result = do {
    println(s"i=$i")
    i += 1
} while (i < 1)
println(result==（）)
```

### for循环的表示

```scala
for( var x <- Range;表达式1;；表达式2 ){

  statement(s);

}
```

for循环实例

```scala
val fruits = List("apple", "banana", "origane", "strawberry")
for (fruit <- fruits) {
	println(fruit + " is " + ftype)
}
```

### 卫语句for循环的表示

循环守卫：即循环保护式，或者叫条件判断式，循环守卫为`true`则进入循环体内部，为`fasle`则跳过，类似于`continue`。

```scala
for( var x <- List
	if condition1; if condition2...
){
	statement(s);
｝
```

卫语句for循环实例

```scala
val fruits = List("apple", "banana", "origane", "strawberry")
for (fruit <- fruits;
	if fruit.startsWith("b");
) {
	println(fruit + " is " + color)
}
```

### 带返回值的for循环表示

```scala
for{ var x <- List
	if condition1; if condition2... 
}yield x
```

带返回值for循环实例

```scala
val fruits = List("apple", "banana", "origane", "strawberry")
val upfruit= for (fruit <- fruits; if fruit.startsWith("b");) yield 
fruit.toUpperCase
println("upfruit =" +upfruit)
```

## 函数式编程

不同范式对比：

- 面向过程：按照步骤解决问题。
- 面向对象：分解对象、行为、属性，通过对象关系以及行为调用解决问题。耦合低，复用性高，可维护性强。
- 函数式编程：面向对象和面向过程都是命令式编程，但是函数式编程不关心具体运行过程，而是关心数据之间的映射。纯粹的函数式编程语言中没有变量，所有量都是常量，计算过程就是不停的表达式求值的过程，每一段程序都有返回值。不关心底层实现，对人来说更好理解，相对地编译器处理就比较复杂。
- 函数式编程优点：编程效率高，函数式编程的不可变性，对于函数特定输入输出是特定的，与环境上下文等无关。函数式编程无副作用，利于并行处理，所以Scala特别利于应用于大数据处理，比如Spark，Kafka框架。

函数定义：

```scala
def func(arg1: TypeOfArg1, arg2: ...): RetType = {
    ...
}
```

- 函数式编程语言中，函数是一等公民（可以像对象一样赋值、作为参数返回值），可以在任何代码块中定义函数。
- 一般将定义在类或对象中（最外层）的函数称为方法，而定义在方法中（内层）的称为函数。广义上都是函数。
- 返回值用`return`返回，不写的话会使用最后一行代码作为返回值。
- 无返回值`Unit`时可以用`return`可以用`return ()`可以不返回。
- 其他时候只需要返回值是返回值类型的子类对象就行。

术语说明：

- java中不提函数的说法，而是说类或者实例方法，不涉及一般化的函数。
- 函数式编程中的函数二字来源于数学上的函数，也就是映射，集合和集合之间的关系，强调数据之间的映射关系。
- 而编程语言中的函数，也包括scala中的函数定义都是指的一个完成特定功能的子程序（subroutine），并不等同于数学意义上的函数。

函数参数：

- 可变参数，类似于Java，使用数组包装。

  - `def f4(str:String*): Unit = {}`。
  - 如果除了可变参数还有其他参数，需要将可变参数放在末尾。
  - 可变参数当做数组来使用。

- 参数默认值:

  - `def f5(name: String = "alice"): Unit = {}`
  - 和C++一样，默认参数可以不传，默认参数必须全部放在末尾。

- 带名称传参：

  - 调用时带名称。

  ```scala
  def f6(name: String, age: Int = 20, loc: String = "BeiJing"): Unit = {
      println(s"name ${name}, age ${age}, location ${loc}")
  }
  
  f6("Bob")
  f6("Alice", loc = "Xi'An")
  f6("Michael", 30)
  ```

  

  - 不给名称的就是按顺序赋值。
  - 调用时带名参数必须位于实参列表末尾。
  - 和默认参数一起使用会很方便，比如有多个默认参数，但只想覆盖其中一个。

函数至简原则：

- 能省则省。

- 最后一行代码会作为返回值，可以省略`return`。

- 函数体只有一行代码的话，可以省略花括号。

- 如果返回值类型能够自动推断那么可以省略。

- 如果函数体中用`return`做返回，那么返回值类型必须指定。

- 如果声明返回`Unit`，那么函数体中使用`return`返回的值也不起作用。

- 如果期望是无返回值类型，那么可以省略`=`。这时候没有返回值，函数也可以叫做过程。【2.13.0已废弃，能编过不过会提示。】

- 无参函数如果声明时没有加`()`，调用时可以省略`()`。【如果声明时有`()`调用也可以省略，不过2.13.3废弃了。】

- 不关心函数名称时，函数名称和def也可以省略，去掉返回值类型，将=修改为=>定义为匿名函数。

  ```scala
  val fun = (name: String) => { println("name") }
  ```



## Scala的类和构造器

 Scala类的定义

#### 类分类

- ​	普通类

- ​	匿名类

- ​	内部类

- ​	抽象类 


#### 类成员

- 构造器/辅助构造器

- 属性

- 方法

- 类

- 对象 

#### 定义一个的无参普通类

定义一个类Socket类，要求有sourceip、port和detinationIP三个属性，要求

- Sourceip不能修改
- Port和deIP可修改且可访问
- sourceip=127.0.0.1和port=22,detinationIP赋予默认属性
- 打印sourceip、port和detinationIP三个属性
- 修改port=50070，detinationIP=192.168.12.10

```scala
package scala04

class Socket {
  val sourceIp = "127.0.0.1" //val 不可变属性
  var port = 22 //var 可变属性
  var delIp = "8.8.8.8" //var 可变属性
}

//程序入口
object RunSocket {
  def main(args:Array[String]): Unit = {
    val sk = new Socket() //创建对象
    println(s"sourceIp = ${sk.sourceIp},port = ${sk.port},delIp = ${sk.delIp}")
//    sk.sourceIp = "8.8" //报错
    sk.port = 80 //修改属性
    sk.delIp = "192.168.0.0"
    println(s"sourceIp = ${sk.sourceIp},port = ${sk.port},delIp = ${sk.delIp}")
  }
}
```



定义一个类Pig类，要求有name、age、sex和color四个属性，要求

- name和age即可访问也可修改
- color访问
- sex不可访问和修改

```scala
class Pig {
  var name = "peiqi"
  var age = 90
  val color = "red" //val 不可修改
  private val sex = true //私有化，外部不可访问也不可修改

  println(s"sex=${sex}") //内部访问sex属性
}

//程序入口
object RunPig {
  def main(args:Array[String]):Unit = {
    val pig = new Pig() //创建对象
    println(s"name=${pig.name},age=${pig.age},color=${pig.color}") //输出结果

    pig.age = 100 //修改age
    println(s"name=${pig.name},age=${pig.age},color=${pig.color}")
  }
}

```

#### 定义一个有参的类

使用带参数构造器，定义Rational类，参数分别是要操作的三个个有理数。

- 参数是Int
- 定义一个方法对参数求和
- 使用已经定义Rational类，实现对指定的一个参数加10和20。

```scala
//Scala的有参类（114页）
class Rational(val x:Int = 10, var y:Int, z:Int = 20) {
//  定义一个方法对参数求和
  def sum():Int = {
    x+y+z
  }
}

object RunRational {
  def main(args:Array[String]):Unit = {
    var r = new Rational(1,2,3)
    println(s"sum=${r.sum()}")

    var r1 = new Rational(y=1)
    println(s"sum=${r1.sum()}")

    var r2 = new Rational(5,y=1,10)
    println(s"sum=${r2.sum()}")
  }
}
```

#### Scala的主构造器

class 类名 （[parameter1，parameter2......]）{

 }

#### Scala的辅助构造器定义

this（[parameter1，parameter2......]）{

 }



定义一个注册类，提供多种不同的创建对象方法

- 必填属性：name、手机号、密码和邮箱
- 可选属性:公司和职位
- name是不可修改
- 其他属性可读可修改

```scala
package scala

class Register(val name:String,var tel:String,var psword:String,var email:String) {
var company=""
  var position=""
  println("enter into Register contruction")

  def this(name:String,tel:String, psword:String, email:String,company:String){
    this(name,tel,psword,email)
    this.company=company
  }
  def this(name:String,tel:String, psword:String, email:String,company:String,position:String){
    this(name:String,tel:String, psword:String, email:String,company:String)
    this.position=position
}
  override def toString = s"Register($company, $position, $name, $tel, $psword, $email)"
}
object RunRegister{
  def main(args: Array[String]): Unit = {
   var r= new Register("xiaoxin","13301922222","123","abc@163.com")
    println(r.toString)
    var r1= new Register("xiaoxin","13301922222","124","abc@163.com","beijingal")
    println(r1.toString)
    var r2= new Register("xiaoxin","13301922222","124","abc@163.com","beijingal","manager")
    println(r2.toString)
  }
}

```



#### 案例名称：创建汽车类

- 需求描述：定义一个Car类，提供四组构造器
- 只读属性制造商、型号名称和年份
- 可读写属性车牌号
- 每一组构造器制造商和型号名称必填
- 型号年份和车牌号可选，如果未设置年份为-1，车牌为空字符串

```scala
package scala03

class Car(val producerName: String, val productType: String, val carYear: Int, var carNum: String) {
  def this(producerName: String, productType: String) {
    this(producerName, productType, -1, "空字符串")
  }

  def this(producerName: String, productType: String, carYear: Int) {
    this(producerName, productType, carYear, "空字符串")
  }

  def this(producerName: String, productType: String, carNum: String) {
    this(producerName, productType, -1, carNum)
  }

  override def toString = s"Car($producerName, $productType, $carYear, $carNum)"
}

object Car {
  def main(args: Array[String]): Unit = {
    val car1 = new Car("audi", "Q5", 2008, "888888")
    val car2 = new Car("audi", "A4")
    val car3 = new Car("audi", "A6", 2008)
    val car4 = new Car("audi", "Q3", "666666")
    println(s"car1=$car1")
    println(s"car2=$car2")
    println(s"car3=$car3")
    println(s"car4=$car4")
  }
}
```



### Scala的伴生类和对象

####  Scala的单例对象

Scala的单例对象声明    

```scala
object identifier{ 

}
```

Scala的单例对象

- ​	不是一个类型

- ​	不能new

- ​	不能传递参数

分别使用Java和Scala创建Single单例对象。

```java
package javacode;

public class Single {
    /**
     * 1.private contruction
     * 2.public method
     * 3.one
     */
    private static  Single instance;
    private Single(){

    }
    public static Single getInstance(){
        if(instance==null){
            instance=new Single();
        }
        return instance;
    }

    public static void main(String[] args) {

        Single instance1 = Single.getInstance();
        Single instance2 = Single.getInstance();
        System.out.println(instance1 ==instance2);
    }
}
```

```scala
package scala

object Single {
  var name="scala single"
  def printName()={
    println(s"name=$name")
  }

  def main(args: Array[String]): Unit = {
    Single.printName()
  }
}
```

Scala的单例对象场景

- 资源共享的情况
- 控制资源的情况

#### Scala的伴生对象与伴生类

- 同名
- 同一个源码文件

Scala的伴生对象与伴生类解决什么问题

- 生成静态成员
- 伴生对象和类之间的相互访问
- 构建单例对象



- 创建一个Student类和它的伴生对象
- 分别用Java和Scala创建静态属性，并访问
- 为Student类和它的伴生对象分别创建私有属性，并相互访问

```scala
package scala

object Student {
private val secrect1="i am secrect1 *****"
  def accessCompanionClass(s:Student)={
    println(s" access Companion Class private field = ${s.secrect2}")
  }
}
class Student{
  private val secrect2="i am secrect2 *****"
  def accessCompanionObject()={
    println(s" access Companion Object private field = ${Student.secrect1}")
  }
}

object Run1{
  //extra class/objec access student class field
 // new Student().secrect2
 // Student.secrect1
 //object access Companion Class private field
 def main(args: Array[String]): Unit = {
   //object access Companion Class private field
  // Student.accessCompanionClass(new Student())
   //Class  access Companion object private field
  new Student().accessCompanionObject()
 }
}
```

#### Scala的对象创建

- new：使用new关键字创建类的对象。
- 伴生对象：使用object关键字创建一个单例对象。
- apply：apply是一个方法，需要在伴生对象中实现这个方法。

使用三种方式创建Person对象

```scala
package scala

class Person {
var name ="person"
  println("enter into person construction ")
}
object Person {
  println("enter into person object construction ")

  def apply(): Person = new Person()

  def apply(name: String): Person = {
    var p = new Person()
    p.name = name
    p
  }
}
object RunPerson{
  def main(args: Array[String]): Unit = {
    // 1.new
    //new Person
    //2.object
    //Person
    //3.apply
    /**
     * 1.companion class and object
     * 2.overwrite apply on companion object
     * 3.apply return Person object
     */
   val p1= Person("apply person")
    println(s"create object by apply p1 = $p1")
    println(s"create object by apply p1 = ${p1.name}")
    val p2 =Person.apply("apply person")
    println(s"create object by apply p2 = $p2")
    println(s"create object by apply p2 = ${p2.name}")
  }
}
```

#### Scala对象的所属类

- getClass
- isInstanceof

```scala
//使用反射机制判断Scala对象所属的类
A.getClass==B.getClass
//A表示对象，B表示类型。如果返回true，则表示A是B的子对象
A.isInStanceof[B]
```

#### Scala的对象相等性判断

- equal方法：相当于Java中的equals方法。
- ==与！=：相当于Java中的equals方法。
- eq与ne：相当于Java中的引用（使用==判断引用）。

**覆写equals方法**

**Scala的自定义对象相等性**

在重写equals方法时，需要满足以下几个条件：

- 方法的名字不可以改变。
- 参数列表一定要相同，参数类型是Any类型。
- 重写方法时需要使用override关键字。

重写equals方法的语法格式：

```scala
override def equals(other: Any): Boolean = {
   true/false
}
```

**覆写原则**

- 反射性
- 对称性
- 过渡性
- 非空性

案例名称：判断Student对象相等

- 需求描述：定义一个Student类，有名字、性别、年龄和身份证号属性，覆写equals方法
- 身份证号相等，则认为两个对象相等。
- 所有属性相等，则认为两个对象相等。

```scala
package scala

object RunJudgeObject {
  def main(args: Array[String]): Unit = {
    val p1=new Person2()
    val p2=new Person2()
    val s=new Student2()
    val t=new Teacher2()
    //1.getClass
    println(s"p1==p2 ? ${p1.getClass==p2.getClass}")
    println(s"p1==p1 ? ${p1.getClass==p1.getClass}")
    println(s"p1==s ? ${p1.getClass==s.getClass}")
    println(s"p1==t ? ${p1.getClass==t.getClass}")
    println(s"s==t ? ${s.getClass==t.getClass}")
    println(s"p1 = ${p1.getClass},p2=${p2.getClass},s=${s.getClass},t=${t.getClass}")
    //isInstanceOF[]
    println(s"p1 isInstanceOF person2 ? ${p1.isInstanceOf[Person2]}")
    println(s"p2 isInstanceOF person2 ? ${p2.isInstanceOf[Person2]}")
    println(s"s isInstanceOF person2 ? ${s.isInstanceOf[Person2]}")
    println(s"t isInstanceOF person2 ? ${s.isInstanceOf[Person2]}")
    println(s"s isInstanceOF Student2 ? ${s.isInstanceOf[Student2]}")
  }
}
class Person2{
  var name="person1"

}
class Student2 extends Person2{

}
class Teacher2 extends Person2{

}
```



# 四 Scala自适应类型和函数

## 1）Scala的自适应类型

Scala可以自行进行类型推算

####  Scala的特殊类型

#### Nothing

- ​	所有类型的子类

- ​	抽象类

- ​	没有任何值


Nothing的作用

- ​	帮助Scala的类型推断

定义一个方法，对两个整数相除，如果除数是0，则抛出 “can not divide by zero”异常

```scala
package scala04

object RumNothing {
  def main(args: Array[String]): Unit = {
    val result1=divide(4,2)
    println(s"result1=$result1")
    val result2=divide(4,0)
    println(s"result2=$result2")
  }
  //can not divide by zero
  def error(msg:String)={
    throw new RuntimeException(msg)
  }
  def divide(x:Int,y:Int)={
    if(y!=0){
      x/y
    }else{
      error("can not divide by zero")
    }
  }
}
```

#### Option[T]

- Option[T]
  - Some(T)
  - None
- Option[T]的作用
  - 避免引用类型调用出现空指针异常
- Option[T]的常用方法
  - get
  - getOrElse(default)
  - isEmpty()

**定义一个map集合，并获取里面的值输出打印**

```scala
package scala04

object RunOption {
  def main(args: Array[String]): Unit = {
    OptionTest()
  }
  def OptionTest(): Unit ={
    val map:Map[String,String]=Map("1"->"java","2"->"scala")
    val v1= map.get("1")
    val v2=map.get("3")
    println(s"v1=$v1,v2=$v2")
    //get value by get
    println(s"v1=${v1.get},v2=${v2}")
    //1.isEMploy
    if(v2.isEmpty){
      println(s"v2=$v2")
    }else{
      println(s"v2=${v2.get}")
    }
 //2getorelse
    println(s"v1=${v1.getOrElse("v1_default")},v2=${v2.getOrElse("v2_default")}")
  }
}
```



#### Scala的元组类型

不同类型值的集合，即元组可以用于存放不同类型的元素。元组最多支持 22 个元素

元组的表示

- ​	(元素1, 元素2, ...元素N)  

- ​	new TupleN(元素1, 元素2, ...元素N)  


元组的访问

​	Tuple_INDEX

元组的遍历 

​	Tuple.productIterator() 

1. 访问元组
2. 遍历元组
3. 交换元组
4. 元组所有元素求和

```scala
package scala04

object RunTuple {
  def main(args: Array[String]): Unit = {
    //1.define tuple
    val t1=("java",4)
    var t2=new Tuple2[String,Int]("python",6)
    //2.access Tuple
    println(s"t1_1=${t1._1},t1_2=${t1._2}")
    println(s"t2_1=${t2._1},t2_2=${t2._2}")
    //error,Error:(12, 12) too many elements for tuple: 30, allowed: 22
//    val t3=(1,2,3,4,5,6,1,2,3,4,5,6,1,2,3,4,5,6,1,2,3,4,5,6,1,2,3,4,5,6)
//    println(t3)
    //4 .loop through tuple
    val t4=(1,2,3,4)
   // t4.productIterator.foreach(i=>println(s"i =${i+1.toString}"))
    t4.productIterator.foreach(i=>println(s"i =${i.asInstanceOf[Int]+1}"))
    //Sum
    var sum =0
    t4.productIterator.foreach(i=>
    sum=sum+i.asInstanceOf[Int]

    )
    println(s"sum=$sum")
    //swap
   // val t1=("java",4)
    println(t1.swap)

  }
}
```



## 2）Scala的函数基础

### **Scala的函数的定义**

![image-20250401223304843](http://img.an520.com/test/image-20250401223304843.png)

### Scala的函数的规则

- 只有一行可省略{}
- 最后一条语句为函数返回值
- 函数返回值可省略

- Scala的函数的类型推导的限制
  - return必须显示指定返回值
  - 递归调用必须使用返回值
- Scala的函数的调用
  - 对象.函数名（参数列表）



- 定义一个Rational类
- 定义一个求两个整数的和方法。
- 定义一个求两个数的最大公约数方法。

```scala
package scala04

object RunFunction {
  def main(args: Array[String]): Unit = {
     val a=sum1(4,5)
     println(s"a=$a")
    val a2=sum2(4,5)
    println(s"a2=$a2")
    println(s"gcd=${gcd(0,4)}")
  }
  //1.
  def sum1(x:Int,y:Int):Int={
    return x+y
  }
  def sum2(x:Int,y:Int):Int= return x+y
  //2.
  def gcd(x:Int,y:Int):Int ={
    if(x==0) y
    else gcd(y%x,x)
  }
}
```

### Scala的函数的默认值

- 函数使用默认值可以不传递参数
- 可以用参数名指定传递参数

- Scala的函数的返回多个值
  - 利用tuples



- 定义一个Connection类，定义一个createConnect方法，有timeout和protocol两个参数，默认值分别是5000和Http。
- 使用默认值打印timeout和protocol值
- timeout=600，protocol使用默认值
- timeout=默认值，protocol=“https”
- timeout=700，protocol=“https”
- 定义一个getconnectInfo方法，返回timeout和protocol两个值

```scala
package scala04

object RunConnection {
  def main(args: Array[String]): Unit = {
    var c=new Connection()
    //1.default
    c.createConn()
    //2.
    c.createConn(700)
    //3
    c.createConn(600,"https")
    //4
    c.createConn(protocol="https")
    //
    c.isboolean(true,true)
    //
    c.isboolean(isman=true,isStudent=true)
    c.createConn(protocol="https",timeout=100)

    //
    val (a,b)=c.createConn(protocol="ftp",timeout=200)
    println(s"a=${a},b=$b")

  }
}
class Connection{
  def createConn(timeout:Long=5000,protocol:String="http") ={
    println(s"timeout=${timeout},protocol=$protocol")
    (timeout,protocol)
  }
  def isboolean(isman:Boolean,isStudent:Boolean): Unit ={
    println(s"isman=${isman},isStudent=$isStudent")
  }
}

```

### 不带()的方法

对于无参数的方法，调用时可以省略圆括号。

- 创建不带()的方法

   def 方法名:[返回类型]={}

```scala
class Person(val name: String) {
  def getName: String = name
}

val person = new Person("Alice")
println(person.getName) // 使用圆括号
println(person.getName()) // 也可以省略圆括号
```



### 变参函数

在 Scala 里，函数变参允许你向函数传递不定数量的参数。这一特性在你不清楚会传入多少参数时特别有用。

- 创建接受变参的方法

  - 参数类型*

- 变参传值

  ​	调用变参函数时，可以直接传入多个参数，也可以传入一个 `Seq` 集合，但需要使用 `:_*` 展开。

  - 参数类型对应值
  - _*

```scala
def printNames(names: String*): Unit = {
  for (name <- names) {
    println(name)
  }
}

// 直接传入多个参数
printNames("Alice", "Bob", "Charlie")

// 传入一个 Seq 集合
val nameList = Seq("David", "Eve", "Frank")
printNames(nameList: _*)
```

变参和其他参数的组合

- 变参必须是函数的最后一个参数。

```scala
//greet 函数有一个普通参数 prefix 和一个变参 names，调用时先传入普通参数，再传入多个变参。
def greet(prefix: String, names: String*): Unit = {
  for (name <- names) {
    println(s"$prefix $name")
  }
}

greet("Hello", "Alice", "Bob", "Charlie")
```

**定义一个Util类，包含一个printlnall方法，参数列表分别接受以下参数：**

- 接受不定字符串
- 接受集合
- 接受一个整形和一个不定字符串
- 接受不传递任何参数

```scala
package scala04

class Utils {
def printNames(names:String*): Unit ={
  names.foreach(x=>println(x))
}
  def printClass(names:String*): Unit ={
    println(names.getClass)
  }
  //
  def printNamesandClass(i:String,j:String,names:String*): Unit ={
    println(s"i=$i,j=$j")
    names.foreach(x=>println(x))
  }
}

object RunVarible{
  def main(args: Array[String]): Unit = {
    val u=new Utils()
    //1.par
    println("---------------1---------------")
    u.printNames("java")
    println("---------------2---------------")
    u.printNames("java","scala")
    println("---------------3---------------")
    u.printNames("java","scala","python")
    //list
    println("---------------4---------------")
    val fruits=List("apple","banana","cherry")
    u.printNames(fruits:_*)
    //3.
    println("---------------5--------------")
    u.printNamesandClass("go","c","java")
    u.printNamesandClass("go","c")
    println("---------------6--------------")
    u.printNames()
    println("---------------7--------------")
    u.printClass()
    println("---------------8--------------")
    u.printClass("go","c","java")
  }
}
```



###  Scala的函数的链式风格

链式风格的核心在于每个函数调用都会返回一个对象，这个对象又可以继续调用其他函数，从而形成一个连续的调用链。

- 链式风格通过让函数调用返回对象，使得多个函数调用可以串联起来，提高代码的可读性和简洁性。
- Scala 内置的集合类和字符串类都支持链式调用，常用于集合操作和字符串处理。
- 你可以在自定义类中实现链式调用，让每个方法返回当前对象的引用。

```scala
object ChainExample extends App {
  val numbers = List(1, 2, 3, 4, 5)

  val result = numbers
    .filter(_ % 2 == 0) // 过滤出偶数
    .map(_ * 2) // 将每个偶数乘以 2
    .sum // 计算总和

  println(result) 
}
```

```scala
object StringChainExample extends App {
  val str = " Hello, World! "

  val processedStr = str
    .trim() // 去除字符串首尾的空格
    .toUpperCase() // 将字符串转换为大写
    .replace("WORLD", "SCALA") // 替换特定的字符串

  println(processedStr) 
}
```



- 链式风格 
  -  person.setName(“scala”).setCity(“beijing”) 
- 链式风格语法
  - this.type
  - this

  
  
  `this.type` 的作用
  
  `this.type` 是一个单例类型，表示当前对象的精确类型。使用 `this.type` 可以确保方法返回当前对象的引用，而不是其父类或接口的引用。这在链式调用中非常重要，因为它允许后续方法继续在同一个对象上调用。
  
  
  
- 定义一个Person类，包含name、age、city属性，使用链式风格为他们赋值。
- 定义一个Student类继承Person，包含name、age、city和sex属性，使用链式风格为他们赋值。

```scala
package scala04

object RunChainMode {
  def main(args: Array[String]): Unit = {
   val person= new Person().setName("suyoupeng").setAge(45).setCity("shanghai").toString
    println(s"person=$person")
    val student= new Student().setName("linzhiying").setAge(48).setCity("hangzhou").setSex("man").toString
    println(s"student=$student")
  }
}
class Person{
  var name=""
  var age=0
  var city="beijing"
  
  def setName(name:String):this.type ={
    this.name=name
    this
  }
  
  def setAge(age:Int):this.type ={
    this.age=age
    this
  }
  
  def setCity(city:String):this.type ={
    this.city=city
    this
  }

  override def toString = s"Person($name, $age, $city)"
}

class Student extends Person{
  var sex=""
  
  def setSex(sex:String):this.type ={
    this.sex=sex
    this
  }
  
  override def toString = s"Student($name, $age, $city,$sex)"
}
```



## 3）Scala的函数进阶

### Scala的函数字面量

函数字面量是一种匿名函数，它没有名称，但可以像普通函数一样被调用。函数字面量通常用于定义简单的操作，尤其是在需要将函数作为参数传递时。

Scala的函数字面量语法

​	（参数列表）=>{方法体}

Scala的函数字面量作用

- ​	变量

- ​	参数

```scala
val addOne = (x: Int) => x + 1
println(addOne(5)) // 输出：6

val sayHello = () => "Hello, Scala!"
println(sayHello()) // 输出：Hello, Scala!

val multiply = (x: Int, y: Int) => x * y
println(multiply(3, 4)) // 输出：12
```


Scala的函数字面的简化

- ​	_

- ​	只有一个表达式，可省略括号

```scala
//占位符语法：当函数字面量的参数在函数体中只出现一次时，可以使用占位符 _ 来简化表达。示例如下：

//在这个例子中，_ 是一个占位符，表示当前参数。
val numbers = List(1, 2, 3, 4, 5)
val doubled = numbers.map(_ * 2)
println(doubled) // 输出：List(2, 4, 6, 8, 10)

//在这个例子中，_ + _ 是 (x, y) => x + y 的简化形式，_ 依次代表函数的参数。
val numbers = List(1, 2, 3, 4, 5)
// 使用占位符语法
//// 使用 reduce 方法计算元素总和
val sum = numbers.reduce(_ + _)
println(sum) //15

//math.pow(_, 2).toInt 是一个方法引用，表示对每个元素调用 math.pow 方法。
val numbers = List(1, 2, 3, 4, 5)
val squared = numbers.map(math.pow(_, 2).toInt)
println(squared) // 输出：List(1, 4, 9, 16, 25)
```

Scala的函数字面量的懒加载

懒加载的核心是延迟执行函数字面量，直至真正需要其结果时才进行计算，这有助于提升性能，避免不必要的计算。

​	lazy

```scala

```

定义一个字面量sum函数，返回两个数的和，并赋予一个变量。

- 简化上述函数
- 懒加载sum函数

```scala
package scala04

object RunLiteralFuntion {
  def main(args: Array[String]): Unit = {
    //
    val sum1=(x:Int,y:Int)=>{x+y}
    println(s"sum1=${sum1(3,4)}")
    //
    val sum2=(x:Int,y:Int)=>x+y
    println(s"sum2=${sum2(1,4)}")
    //
    val sum3=(_:Int)+(_:Int)
    println(s"sum3=${sum3(7,4)}")
    //
    val sum4:(Int,Int)=>Int=_+_
    println(s"sum4=${sum4(6,4)}")
    //
    lazy val sum5=(x:Int,y:Int)=>{x+y}
    println(sum5(8,2))
  }

}
```

### Scala的函数作为参数

当一个函数接收另一个函数作为参数时，这个接收函数参数的函数被称作高阶函数。高阶函数在函数式编程中非常关键，它能让代码更具灵活性和可复用性。

- 简单函数作为参数
- 除函数外的其他参数

```scala
// 定义一个高阶函数，接受一个整数和一个函数
def operateOnNumber(num: Int, func: Int => Int): Int = {
  func(num)
}

// 定义一个简单的函数，用于将输入的数乘以 2
def multiplyByTwo(x: Int): Int = x * 2

// 调用高阶函数
val result = operateOnNumber(5, multiplyByTwo)
println(result) 
```

```scala
//除了传递已定义的函数，还可以使用函数字面量（匿名函数）作为参数：
val numbers = List(1, 2, 3, 4, 5)
// 使用 map 方法，传入一个函数字面量
val squaredNumbers = numbers.map(x => x * x)
println(squaredNumbers) 
```

•定义一个exeFunction函数，接受一个无参数的sayHello函数。

•定义一个exeAdd函数，接受一个带有整形参数的函数，对整数加10。

•定义一个exeAndPrint方法，要是接受一个带两个参数的函数和两个整形，将整形参数赋予函数，计算打印结果。(使用两种方式)

```scala
package scala04

object RunWithParFuntion {
  def main(args: Array[String]): Unit = {
    //1.withoutPar
    val sayhello=()=>{println("hello scala function")}
    exeFuctionWithOutPar(sayhello)
    //2.withpar
    val plusTen=(i:Int)=>{i+10}
    val result= exeAdd(plusTen)
    println(s"r=$result")
    //3
    val sum=(x:Int,y:Int)=>x+y
    exeAndPrint(sum,2,3)
    val multi=(x:Int,y:Int)=>x*y
    exeAndPrint(multi,2,3)
  }
  
  def exeFuctionWithOutPar(callback:()=>Unit): Unit ={
    callback()
  }
  
  def exeAdd(callback:Int=>Int): Int ={
    callback(8)
  }
  
  def exeAndPrint(callback:(Int,Int)=>Int,x:Int,y:Int): Unit ={
    val result=callback(x,y)
    println(s"callback=$result")

  }
}

```



###  Scala函数的闭包

闭包：如果一个函数，访问到了它的外部（局部）变量的值，那么这个函数和他所处的环境，称为闭包。

Closure in ruby 闭包的条件

- 代码块当作值传递
- 可以被任何拥有该值的对象按需执行
- 可以引用上下文已经创建的变量

演示闭包。

```scala
package scala04

object RunClosure {
  def main(args: Array[String]): Unit = {
    //
    val isage1=(age:Int) => age>18
    println(isage1(10),  isage1(20))

    var voteage=18
    val isage2=(age:Int) => age>voteage
    println(isage2(10),  isage2(20))
    
    new Clouse().printResult(isage2,20)
    
    voteage=21
    new Clouse().printResult(isage2,20)

  }
}

class Clouse{
  def printResult(f:Int=>Boolean,x:Int): Unit ={
    println(f(x))
  }

}
```

###  Scala函数的柯里化

函数柯里化（Currying）指的是将一个多参数函数转换为一系列单参数函数的过程。

#### 柯里化的定义

def 函数名（参数列表1）（参数列表2）...（参数列表n）:type={

​                   方法体

}

#### 柯里化的注意要点

- 不能传递部分参数
- 可以利用隐式参数传递部分值
- 不能返回新的函数

定义一个两个整数乘法的柯里化函数。

```scala
package scala04

class RunK {
  def multi(x: Int)(y: Int): Int = {
    x * y
  }
}

object RunK {
  def main(args: Array[String]): Unit = {
    val r = new RunK().multi(10)(3)
    println(r)
  }
}
```

###  Scala部分应用函数

部分应用函数是指在调用一个多参数函数时，只传递部分参数，从而得到一个新的函数。

#### 部分应用函数的定义

只传递部分参数

def 函数名（参数列表X，Y..）:type={

​                   f(Y)

}

#### 部分应用函数作用

​	返回新的函数

```scala
class RunPartialFunction {
  def warpHTMl(pref: String, context: String, suffix: String): String = {
    pref + context + suffix
  }

  def mutlti(x: Int, y: Int, z: Int) = x * y * z
}

object RunPartialFunction {
  def main(args: Array[String]): Unit = {
    val p = new RunPartialFunction()
    val htmlwithp = p.warpHTMl("<p>", _: String, "</p>")
    println("p= " + htmlwithp("i am p"))
    val htmlwithdiv = p.warpHTMl("<div>", _: String, "</div>")
    println("div= " + htmlwithdiv("i am div"))
    //2.
    val f1 = p.mutlti(_: Int, 2, _: Int)
    println(f1(4, 5))
    val f2 = p.mutlti(_: Int, 2, 3)
    println(f2(5))
    val f3 = p.mutlti(_: Int, _: Int, _: Int)
    println(f3(5, 1, 2))
    //a(x)(y) a(2)(3)=====>a(x) _
  }
}
```



- 定义一个函数为HTML，添加前后缀(如`<div>和</div>`)
- 定义一个接受三个参数的函数，实现三个数相乘，传递部分参数，打印结果

```scala
package scala04

class RunPartialFunction {
  def warpHTMl(pref: String, context: String, suffix: String): String = {
    pref + context + suffix
  }

  def mutlti(x: Int, y: Int, z: Int) = x * y * z
}

object RunPartialFunction {
  def main(args: Array[String]): Unit = {
    val p = new RunPartialFunction()
    val htmlwithp = p.warpHTMl("<p>", _: String, "</p>")
    println("p= " + htmlwithp("i am p"))
    val htmlwithdiv = p.warpHTMl("<div>", _: String, "</div>")
    println("div= " + htmlwithdiv("i am div"))
    //2.
    val f1 = p.mutlti(_: Int, 2, _: Int)
    println(f1(4, 5))
    val f2 = p.mutlti(_: Int, 2, 3)
    println(f2(5))
    val f3 = p.mutlti(_: Int, _: Int, _: Int)
    println(f3(5, 1, 2))
    //a(x)(y) a(2)(3)=====>a(x) _
  }
}
```



## 4）Scala的高阶函数

#### Scala的高阶函数定义

高阶函数是指使用其他函数作为参数、或者返回一个函数作为结果的函数。在Scala中函数是“一等公民”，所以允许定义高阶函数。这里的术语可能有点让人困惑，我们约定，使用函数值作为参数，或者返回值为函数值的“函数”和“方法。  

#### Scala的常见高阶函数   

- ​	map

- ​	flatten

- ​	flat

- ​	map

- ​	foreach

- ​	reduce

- ​	filter

- ​	fold



1.打印如下图形

  `*`

  `**`

  `***`

  `****`

  `*****`

   ..................

2.过滤1-10偶数

3.字符串数组，将其转成大写，过滤掉以s开头的字符串

•1.利用reduceleft实现数组中最大的元素

•2.计算整型数组所有数乘积

•案例名称：实现字符串的求和

•需求描述：字符串数组中的数字个数，如Array（“1,2”“3,4”）求和

•使用技能:高阶函数

•1.用to和reduceLeft实现阶乘函数,不得使用循环或递归

•2. 前一个实现需要处理一个特殊情况，即n<1的情况。展示如何  用foldLeft来避免这个需要。

```scala
package scala04

object RunHighFun {
  def main(args: Array[String]): Unit = {
    val array = Array(1, 2, 3, 4, 5)
    //"a"*3 =aaa
    val s = array.map(x => "*" * x)
    //  s.foreach(x=>println(x))
    //
    // array.map(x=>"*"*x).foreach(x=>println(x))
    array.map("*" * _).foreach(println(_))
    //filter
    val array1 = Array(1, 2, 3, 4, 5)
    array1.filter(x => x % 2 != 0).foreach(e => println(e))
    val s2 = Array("java", "scala", "go")
    //  s2.map(x=>x.toUpperCase).foreach(e=>println(e))
    s2.map(x => x.toUpperCase).filter(s => (!s.startsWith("S"))).foreach(e => println(e))
    //1.multi,array.reduce(_*_)
    val r2 = array.reduce((x, y) => x * y)
    println(s"r2=$r2")
    //2.find max value by reduceleft
    val maxarray = Array(1, 20, 38, 400, 666, 0, 999)
    val max = maxarray.reduceLeft { (x, y) =>
      if (x > y)
        x
      else
        y
    }
    println(s"max=$max")
    //
    val sumarray = Array("1,2","3,4")
    val sum=sumarray.flatMap(x=>x.split((","))).map(_.toInt).reduce(_+_)
    println(s"sum=$sum")
  }
}

```

# 五 Scala继承和多态

## Scala的继承

继承定义

在原有类基础上定义一个新类，原有类父类，新类子类。

继承的好处

- ​	复用代码

- ​	实现多态


继承的语法

​	extends

调用父类构造器语法

```
class Dog(name:String,age:Int) extends Animal(name,age)
```

辅助构造器调用

- 父类的辅助构造器可以被子类的主构造器调用

- 父类的辅助构造器不能子类的辅助构造器调用


### Scala的多态

多态

​	在执行期间而非编译期间确定所引用对象的类型，根据实际类型调用其方法。

多态的作用

​	当子类继承父类，不同子类需要实现自己的行为。

多态的实现手段

​	重写

### Scala的继承

方法的继承

​	子类继承父类的行为

方法的重写

​	当子类继承父类，从父类继承的方法不能满足要求时，子类需要有自己的行为。

方法重写语法

​	override



定义一个Animal类和他的一个子类Dog/Cat。

- •父类声明speak和run两个方法
- •子类实现重写speak方法，继承run方法。

```scala
package scala05

object RunInheritPerson {
  def main(args: Array[String]): Unit = {
    // new employee("scala",5,"amc")
    println("-------Dog-----------")
    val d = new InheritDog()
    d.run
    d.speak
    println("-------cat-----------")
    val c = new InheritCat()
    c.run
    c.speak
  }
}

class InheritPerson(val name: String, var age: Int) {
  def this() = {
    this("java", 30)
  }

  println(s"parent=>name=$name,age=$age")
}

//class employee(name:String,age:Int,var addr:String) extends InheritPerson(name,age){
////  println(s"sub=>name=$name,age=$age,addr=-$addr")
////}
class employee(name: String, age: Int, var addr: String) extends InheritPerson() {
  println(s"sub=>name=$name,age=$age,addr=-$addr")
}

class InheritAnimal {
  def speak = {
    println("animal speak ")
  }

  def run: Unit = {
    println("run by leg ")
  }
}

class InheritDog extends InheritAnimal {
  override def speak = {
    println("dog wangwang  speak ")
  }
}

class InheritCat extends InheritAnimal {
  override def speak = {
    println("cat miaomiao  speak ")
  }
}
```



## Scala的继承关系

Scala继承的层级关系

![image-20250315020810960](http://img.an520.com/test/image-20250315020810960.png)

### Scala的抽象类

Scala的抽象类定义

​	抽象类是一个不能被实例化的类。

Scala的抽象类的语法

​	abstract

Scala的抽象类成员

​	成员属性

​	方法



定义一个抽象类，并调用使用它们

- 成员属性
- 成员方法
- 具体方法和成员

```scala
package scala05

object RunAbstract {
  def main(args: Array[String]): Unit = {
    val m = new mysql()
    println(m.ip, m.port)
    m.connect
    m.print()
  }
}

abstract class DataBase {
  val ip = "127.0.0.1"
  var port: Int

  def connect

  def print() = {
    println("connect failed")
  }
}

class mysql extends DataBase {
  override var port: Int = 22

  override def connect: Unit = {
    println("connect mysql")
  }
}
```

Scala何时使用抽象类

- 基类构造器参数
- Java的调用

基类定义属性的重写

- 非抽象val
- 非抽象var
- 抽象val和var

定义一个抽象类Animal，定义子类Dog和Cat，分别实现以下情况Animal成员属性的调用

- 非抽象val
- 非抽象var
- 抽象val和var

```scala
package scala05

object RunAOver {
  def main(args: Array[String]): Unit = {
    val d = new DogOverride()
    val c = new CatOverride()
    d.run()
    c.run()
    d.sayHello
    c.sayHello
  }
}

abstract class AnimalOverride {
  val name: String
  val color = "none"
  var age = 0

  def sayHello

  def run() = {
    println("run")
  }
}

class DogOverride extends AnimalOverride {
  override val color = "black"
  age = 2
  val name = "dog"

  override def sayHello: Unit = {
    println(color + " " + age + " dog wangwang " + name)
  }

  override def run() = {
    println("dog run")
  }
}

class CatOverride extends AnimalOverride {
  override val color = "white"
  age = 3
  val name = "cat"

  override def sayHello: Unit = {
    println(color + " " + age + " cat miaomiao " + name)
  }

  override def run() = {
    println("cat run")
  }
}
```



### Scala的内部类

Scala的内部类

​	•定义在类或对象内部的类

•Scala的内部对象

​	定义在类或对象内部的对象

•Scala的匿名类

​	没有名字的类



## Scala的trait

Scala的特质

Scala的特质定义

```
Trait identified {

}
```

Scala的特质作用

- 封装成员和方法
- 抽象类
- 接口

Scala的特质语法

​	`extends  A with B`

trait的几种用法  

- ​	只有抽象方法的trait

- ​	只有抽象成员和方法的trait

- ​	具体成员的变量和方法

- ​	对象继承特质

•定义一个person特质演示trait的用法

```


```

trait的mix

- 抽象成员
- 具体成员

定义一个Pet特质演示trait的继承用法

```scala
package scala05

object RunInherit {
  def main(args: Array[String]): Unit = {
    val d = new Dog()
    d.getName
    d.getColor
    println(d.size)
  }
}

trait Pet {
  val name: String
  val size = 5
  var age: Int
  var color = "black"

  def getName

  def getColor = {
    println(s"i am $color")
  }

  println(s"Pet($name,$age,$color,$size)")
}

class Dog extends Pet {
  override val size = 1
  val name = "dog"
  var age = 2
  color = "yellow"

  def getName = {
    println(s"Dog=$name")
  }

  override def getColor = {
    println(s"dog am $color")
  }

  println(s"Dog($name,$age,$color,$size)")
}
```

•trait的加载顺序

- 超类
- 如果混入的trai有父类，会按照继承关系先调用父类
- 如果多个父类，按照左到右
- 本类构造器

•定义一个多个父类和子类演示构造器执行顺序

```

```

•trait的抽象成员父类使用问题

- 空指针异常

•解决

- 提前定义
- 懒加载

定义一个Logger演示构造器执行顺序造成空指针问题

```scala
package scala05

import java.io.PrintWriter

object RunFile {
  def main(args: Array[String]): Unit = {
    //val p=  new Person051()
    val p = new {
      override val filename = "p052.log"
    } with Person051
    p.log("Person052 create log")
  }
}

trait Logger {
  def log(msg: String)
}

trait FileLogger extends Logger {
  val filename: String
  //lazy val fileout= new PrintWriter(filename)
  val fileout = new PrintWriter(filename)

  //fileout.println("###########")
  def log(msg: String) = {
    fileout.println(msg)
    fileout.flush()
  }
}

class Person051 extends FileLogger {
  override val filename = "p051.log"
}
```

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

定义类，分别实现成员属性和构造器的不同访问权限

- 默认访问权限
- protected访问权限
- private访问权限
- private[this]访问权限

```scala
package scala06

class Person0602(protected val name: String, private val age: Int, val city: String, private[this] val weighs: Int) {

}

class p0602 extends Person0602("yangmi", 30, "shanghai", 120) {
  println(s"protected name=${this.name}")
}

object Person0602 {
  def main(args: Array[String]): Unit = {
    val p = new Person0602("suyoupeng", 20, "beijing", 150)
    println(s"privte age=${p.age}")
    // println(s"private weighs=${p.weighs}")
    new p0602()
  }
}
```

定义类，实现方法作用域的控制

- 默认访问权限
- protected访问权限
- private访问权限
- private[package]
- private[this]访问权限

```scala

```



## 2 Scala的包和导入

#### Scala的包

- Scala的包定义
  - 解决类的命名冲突和类的文件管理
- Scala包的语法
  - package name
  - package name{   }
- Scala包的作用域
  - Private[包名]
  - protected[包名]

## Scala的包的导入

- Scala的导入语法
  - import
- 导入成员重命名
  - Import {A=>a}
- 导入成员隐藏类
  - Import {A=>_,_}

•导入一个包的多个类

•导入一个包的所有类

•在一个类中，导入Java的list和Scala的list

•在一个类中导入除了Random都所有类

```scala
import java.util.{Date, Calendar}

import java.util._

import java.util.{List => JavaList}
//除了 java.util 包中的 Random 类，同时导入了该包中的其他所有类。
import java.util.{Random => _, _}
```



## 3 Scala的集合

Scala的集合继承关系

![92a9c8a443d35ace3cb252282b7b504](http://img.an520.com/test/92a9c8a443d35ace3cb252282b7b504.png)



Scala的可变集合和不可变集合  

- Scala.collection.immutable
- Scala.collection.mutable
- Scala.collection

课程示例

可变集合与不可集合

```scala
object RunColletion {
  def main(args: Array[String]): Unit = {
    //1.immutable
    val c1=Set(1)
    val c2=c1.+(3)//c1 +3
    println(s"c1=${c1},c2=${c2}")
    var cr1=Set(9)
    cr1=Set(5)
    println(cr1)
    var v1=Vector("v1")
    //v1(0)="v2"
    
    //2.MUTABLE
    val mutableset=scala.collection.mutable.Set(5)
    mutableset.add(3)
    println(s"mutableset=${mutableset}")
    
    //3.dog
    val reslut=dig(1234576311)
    println(reslut)
  }
  
}

```

定义一个方法求一个整形的阿拉伯数字，并且放到一个集合中(不能有重复)

```scala
//n=12341,=set(1,2,3,4)
def dig(n: Int): Set[Int] = {
    // 处理负数情况，将负数转换为正数后递归调用函数
    if (n < 0) dig(-n)
    // 如果 n 是个位数，直接将其放入 Set 集合中返回
    else if (n < 10) Set(n)
    // 对于多位数，递归调用 dig 函数处理除最后一位外的数字，然后将最后一位数字添加到结果集合中
    else dig(n / 10) + (n % 10)
}
```

scala.collection

![image-20250120014009577](http://img.an520.com/test/image-20250120014009577.png)

scala.collection.mutable

![image-20250120014032567](http://img.an520.com/test/image-20250120014032567.png)

scala.collection.immutable

![image-20250120014043340](http://img.an520.com/test/image-20250120014043340.png)

Scala的集合的一致性

- Traversable(1, 2, 3)
- Iterable("x", "y", "z") 
- map("x" -> 24, "y" -> 25, "z" -> 26) 
- Set(Color.red, Color.green, Color.blue) 
- SortedSet("hello", "world") 
- Buffer(x, y, z) 
- IndexedSeq(1.0, 2.0)
- LinearSeq(a, b, c)



## 4 Scala的迭代器

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

迭代器的操作

```scala
object RunIterator {
  def main(args: Array[String]): Unit = {
    //1.Range
    val it1 = Iterator(1 to 5)
    println(it1.hasNext, it1.next())
    // println(it1.hasNext,it1.next())
    val it2 = Iterator(1, 2, 3)
    println(it2.hasNext, it2.next())
    println(it2.hasNext, it2.next())
    println(it2.hasNext, it2.next())
    //Iterator(1 ,2,3,4,5,6,7,8,9,10)
    val it3 = Iterator(1 to 5: _*)
    while (it3.hasNext) {
      println(it3.next())
    }
    
    //2.
    val it4 = Iterator(1 to 3: _*)
    //    for(i<-it4){
    ////      println(s"the first i=$i")
    ////    }
    ////    for(i<-it4){
    ////      println(s"the secd i=$i")
    ////    }
    it4.foreach(x => println(x))
    it4.foreach(x => println(x))
    
    //3
    val it5 = Iterator(6 to 8: _*)
    val (it51, it52) = it5.duplicate
    it51.foreach(x => println(x))
    it52.foreach(x => println(x))
    it5.foreach(x => println(x))
    
    //4.
    val it6 = Iterator(9 to 12: _*)
    val it61 = it6.take(2)
    it61.foreach(x => println("it61=" + x))
    it6.foreach(x => println("it6=" + x))
    
    //7
    val it7 = Iterator(13 to 18: _*)
    val it71 = it7.slice(1, 10)
    it71.foreach(x => println("it71=" + x))
    
    //8.zip and zipall
    val it8key1 = Iterator("k1", "k2")
    val it8v1 = Iterator("v1", "v2")
    val it8v2 = Iterator("v1")
    val it8k2 = Iterator("k1")
    //   val k1_v1=it8key1.zip(it8v1)
    //  k1_v1.foreach(x=>println(x))

    //    val k1_v2=it8key1.zip(it8v2)
    //     k1_v2.foreach(x=>println(x))

    //       val k1_v2=it8key1.zipAll(it8v2,"default1","default2")
    //        k1_v2.foreach(x=>println(x))
    val k2_v1 = it8k2.zipAll(it8v1, "default1", "default2")
    k2_v1.foreach(x => println(x))

  }
}
```



# 七 Scala的Seq 

## Scala的seq

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

•Scala的Traversable常用操作

```scala
import scala.collection.mutable.ArrayBuffer

object RunTraserbale {
  def main(args: Array[String]): Unit = {
    //get
    val t1 = Traversable(1, 2, 3, 5, 4)
    println(s"head=${t1.head},last=${t1.last}")
    println(s"tail=${t1.tail},init=${t1.init}")
    val t2 = Traversable()
    //    if(!t2.isEmpty){
    //      println(s"head=${t2.head},last=${t2.last}")
    //    }
    println(s"head=${t1.headOption.getOrElse(0)},last=${t1.lastOption.getOrElse(0)}")
    println(s"======end====")
    val t3 = t1.find(x => x > 3)
    println(s"t3=${t3.get}")

    //2

    val fruits = Traversable("banana", "apple")

    fruits.foreach(println(_))
    for (fruit <- fruits) println(fruit)
    val it = fruits.toIterator
    while (it.hasNext) println(it.next())
    val upeerfruits = for (fruit <- fruits) yield {
      val upper = fruit.toUpperCase
      upper
    }
    println(s"upper=${upeerfruits}")
    //
    val up = fruits.map(x => x.toUpperCase)
    println(s"up=$up")
    //3.view
    val t5 = Traversable(1, 2, 3)
    val initmap = t5.map(_ * 2)
    // val view=  t5.view.map(_*2).force
    val view = t5.view.map(_ * 2).foreach(println(_))
    println(s"initmap=$initmap")

  }
}
```

- 简单操作还是太少了，不足以应对复杂的需求。

集合高级计算函数：

- 大数据的处理核心就是映射（map）和规约（reduce）。

- 映射操作（广义上的map）：

  - 过滤：自定义过滤条件，`filter(Elem => Boolean)`
  - 转化/映射（狭义上的map）：自定义映射函数，`map(Elem => NewElem)`
  - 扁平化（flatten）：将集合中集合元素拆开，去掉里层集合，放到外层中来。`flatten`
  - 扁平化+映射：先映射，再扁平化，`flatMap(Elem => NewElem)`
  - 分组（group）：指定分组规则，`groupBy(Elem => Key)`得到一个Map，key根据传入的函数运用于集合元素得到，value是对应元素的序列。

- 规约操作（广义的reduce）：

  - 简化/规约（狭义的reduce）：对所有数据做一个处理，规约得到一个结果（比如连加连乘操作）。`reduce((CurRes, NextElem) => NextRes)`，传入函数有两个参数，第一个参数是第一个元素（第一次运算）和上一轮结果（后面的计算），第二个是当前元素，得到本轮结果，最后一轮的结果就是最终结果。`reduce`调用`reduceLeft`从左往右，也可以`reduceRight`从右往左（实际上是递归调用，和一般意义上的从右往左有区别，看下面例子）。
  - 折叠（fold）：`fold(InitialVal)((CurRes, Elem) => NextRes)`相对于`reduce`来说其实就是`fold`自己给初值，从第一个开始计算，`reduce`用第一个做初值，从第二个元素开始算。`fold`调用`foldLeft`，从右往左则用`foldRight`（翻转之后再`foldLeft`）。具体逻辑还得还源码。从右往左都有点绕和难以理解，如果要使用需要特别注意。

- 以上：

  ```scala
  object HighLevelCalculations {
      def main(args: Array[String]): Unit = {
          val list = List(1, 10, 100, 3, 5, 111)
          
          // 1. map functions
          // filter
          val evenList = list.filter(_ % 2 == 0)
          println(evenList)
  
          // map
          println(list.map(_ * 2))
          println(list.map(x => x * x))
  
          // flatten
          val nestedList: List[List[Int]] = List(List(1, 2, 3), List(3, 4, 5), List(10, 100))
          val flatList = nestedList(0) ::: nestedList(1) ::: nestedList(2)
          println(flatList)
  
          val flatList2 = nestedList.flatten
          println(flatList2) // equals to flatList
  
          // map and flatten
          // example: change a string list into a word list
          val strings: List[String] = List("hello world", "hello scala", "yes no")
          val splitList: List[Array[String]] = strings.map(_.split(" ")) // divide string to words
          val flattenList = splitList.flatten
          println(flattenList)
  
          // merge two steps above into one
          // first map then flatten
          val flatMapList = strings.flatMap(_.split(" "))
          println(flatMapList)
  
          // divide elements into groups
          val groupMap = list.groupBy(_ % 2) // keys: 0 & 1
          val groupMap2 = list.groupBy(data => if (data % 2 == 0) "even" else "odd") // keys : "even" & "odd"
          println(groupMap)
          println(groupMap2)
  
          val worldList = List("China", "America", "Alice", "Curry", "Bob", "Japan")
          println(worldList.groupBy(_.charAt(0)))
  
          // 2. reduce functions
          // narrowly reduce
          println(List(1, 2, 3, 4).reduce(_ + _)) // 1+2+3+4 = 10
          println(List(1, 2, 3, 4).reduceLeft(_ - _)) // 1-2-3-4 = -8
          println(List(1, 2, 3, 4).reduceRight(_ - _)) // 1-(2-(3-4)) = -2, a little confusing
  
          // fold
          println(List(1, 2, 3, 4).fold(0)(_ + _)) // 0+1+2+3+4 = 10
          println(List(1, 2, 3, 4).fold(10)(_ + _)) // 10+1+2+3+4 = 20
          println(List(1, 2, 3, 4).foldRight(10)(_ - _)) // 1-(2-(3-(4-10))) = 8, a little confusing
      }
  }
  ```

  - 经典案例：单词计数：分词，计数，取排名前三结果。

  ```scala
  // count words in string list, and get 3 highest frequency words
  def wordCount(): Unit = {
      val stringList: List[String] = List(
          "hello",
          "hello world",
          "hello scala",
          "hello spark from scala",
          "hello flink from scala"
      )
  
      // 1. split
      val wordList: List[String] = stringList.flatMap(_.split(" "))
      println(wordList)
  
      // 2. group same words
      val groupMap: Map[String, List[String]] = wordList.groupBy(word => word)
      println(groupMap)
  
      // 3. get length of the every word, to (word, length)
      val countMap: Map[String, Int] = groupMap.map(kv => (kv._1, kv._2.length))
  
      // 4. convert map to list, sort and take first 3
      val countList: List[(String, Int)] = countMap.toList
          .sortWith(_._2 > _._2)
          .take(3)
  
      println(countList) // result
  }
  ```

Scala的Seq继承关系

![image-20250120014546096](http://img.an520.com/test/image-20250120014546096.png)

•Scala的Range

- 填充数据结构

•Scala的Stack

- LIFO

•Scala的queue

- FIFO



•Scala的Array

- New Array[T]（n）
- Array
- Rang填充
- 其他集合转换

•Scala的ArrayBuffer

- ArrayBuffer
- New ArrayBuffer

•Scala的ArrayBuffer

- ofDim
- Array(Array1,Array2…Arrayn)

```scala
import scala.collection.mutable.{ArrayBuffer, ListBuffer}

object RunArray {
  def main(args: Array[String]): Unit = {
    //array
    val arr1 = new Array[Int](3)
    val arr2 = Array(1, 2d, 3l)
    arr2.foreach(println(_))
    val arr3 = Array[Number](1, 2d, 3l)
    arr3.foreach(println(_))
    arr1(0) = 7
    arr1(1) = 8
    arr1(2) = 9
    arr1.foreach(x => print(x + ","))

    val r1 = Array.range(1, 5)
    val r2 = Array.range(1, 5, 2)
    val r3 = Array.fill(2)("scala")
    val r4 = List("a", "b").toArray
    val r5 = Array.tabulate(3)(n => n * n)
    r1.foreach(x => print("r1=" + x + ","))
    println()
    r2.foreach(x => print("r2=" + x + ","))
    println()
    r3.foreach(x => print("r3=" + x + ","))
    println()
    r4.foreach(x => print("r4=" + x + ","))
    println()
    r5.foreach(x => print("r5=" + x + ","))
    println()
    //arraybuffer
    val ab1 = ArrayBuffer(1, 2, 3)
    val ab2 = new ArrayBuffer[String](1)
    ab2 += "a"
    ab2 += "b"
    ab2 += "c"
    ab2 += ("d", "e")
    ab2 ++= Seq("s1", "s2")
    ab2.append("apend1")
    println(s"before=$ab2")

    ab2 -= "b"
    ab2 -= ("d", "e", "b")
    ab2 --= Seq("s1", "s2")
    ab2.remove(0)
    //(a,a1,a4,a2,a3)
    ab2.append("apend4", "apend2", "apend3")
    ab2.remove(1, 3)
    ab2.clear
    println(s"after=$ab2")
    val arr7 = Array[String]("banana", "apple")
    val arr8 = arr7.filter(x => x.startsWith("b"))
    arr8.foreach(x => print("arr7=" + x + ","))
    //
    val marr1 = Array.ofDim[String](2, 2)
    marr1(0)(0) = "a"
    marr1(0)(1) = "b"
    marr1(1)(0) = "c"
    marr1(1)(1) = "d"
    for {
      i <- 0 until 2
      j <- 0 until 2
    }
      println(s"($i,$j)=${marr1(i)(j)}")
    var marr2 = Array(Array(1, 2), Array(3, 4))
    println(marr2(1)(0))
    marr2 ++= Array(Array(5, 6))
    println(marr2(2)(1))

  }
}
```



## Scala的List

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

•Scala的List操作

```scala
import scala.collection.mutable.ListBuffer

object RunList {
  def main(args: Array[String]): Unit = {
    //list（1,2,3）
    var l1 = 1 :: 2 :: 3 :: Nil
    println(s"l1,head=${l1.head},list(2)=${l1(2)}")
    val l2 = List(4, 5, 6)
    val l3 = l2 :: l1
    println(l3)
    //++,concat
    val l4 = l2 ::: l1
    println(l4)

    //
    val lb1 = ListBuffer(7, 8, 9)
    lb1(0) = 99
    println(lb1)

    val s = 1 #:: 2 #:: 3 #:: Stream.empty
    val s2 = s.map(x => x + 1)
    println(s2, s2(2))
    println(s.force)
    //
    val zip1 = (List(1, 2), List(3, 4, 5)).zipped.map(_ * _)
    println(s"zip1=$zip1")
    //list(scala is good)
    val words = List("scala", "is", "good")
    val s3 = (" " /: words)(_ + " " + _)
    println(s3)
    val s4 = (words.head /: words.tail)(_ + " " + _)
    println(s4)
    //l1 ::: l2
    (List[String]() /: List(List[String]("1", "2"), List("3", "4")))(_ ::: _)
    (List(List[String]("1", "2"), List("3", "4")) :\ List[String]())(_ ::: _)

    val v = Vector(1, 2, 2, 3)
    val v1 = v.updated(0, "*")
    println(s"v1=$v1")
    println(s"v=$v")
  }
}
```

案例名称：归并排序

需求描述：利用List实现归并排序

```

```



## Scala的Vector

Scala的Vector

​	不可变IndexSeq

Scala的Seq选取

# 八 Scala映射和模式匹配

## 1 Scala的Set

Scala的Set继承关系

![image-20250120014826911](http://img.an520.com/test/image-20250120014826911.png)

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

Set集合操作

```scala
import scala.collection.immutable.SortedSet
import scala.collection.mutable

object RunSet {
  def main(args: Array[String]): Unit = {
    //== contain
    val s1 = Set(1, 2, 3, 3, 2, 5)
    val s2 = Set(3, 5)
    val s3 = Set(4, 5)
    println(s1)
    //2
    println(s1.contains(1), s1.contains(6))
    println(s1(2), s1(8))
    println(s"s1 sub s2 ${s1.subsetOf(s2)}")
    println(s"s1 sub s3 ${s1.subsetOf(s3)}")
    println(s"s2 sub s1 ${s2.subsetOf(s1)}")
    println(s"s3 sub s1 ${s3.subsetOf(s1)}")
    //++ +=  - -=   immutable +    mutable +=
    var imms = Set(4, 5, 6)
    val imm1 = imms + 3
    val imm2 = imm1 + (22, 33)
    val imm3 = imm2 ++ List(44, 55)
    //imms=imms+99
    //    imms +=99
    //
    println(imm3)
    println(imms)
    var ms = scala.collection.mutable.Set(7, 8, 9)
    ms += 10
    ms += (11, 12, 12)
    ms ++= Set(13, 14)
    println(ms)
    ms.retain(_ > 9)
    ms.remove(12)
    ms.clear
    println(ms)
    //
    val ss1 = mutable.SortedSet(10, 3, 11, 2)
    val ss3 = SortedSet(7, 3, 11)
    println(ss1)
    println(ss3)
    val ss2 = mutable.SortedSet("banana", "apple")
    println(ss2)
    val lhs = mutable.LinkedHashSet(1, 8, 4)
    println(lhs)
    val p1 = new Person0701("scala", 12)
    val p2 = new Person0701("java", 2)
    val p3 = new Person0701("c", 20)
    val p = mutable.SortedSet(p1, p2, p3)
    println(p)
  }
}

class Person0701(var name: String, var age: Int) extends Ordered[Person0701] {

  override def compare(that: Person0701): Int = {
    if (this.age == that.age) {
      0
    } else if (this.age < that.age) 1
    else -1
  }

  override def toString = s"Person0701($name, $age)"
}

```



## 2 Scala的map

Scala的map继承关系

![image-20250120014947462](http://img.an520.com/test/image-20250120014947462.png)

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

映射的增、删、改和查操作

```scala
package scala07

import scala.collection.immutable.ListMap
import scala.collection.mutable

object RunMap {
  def main(args: Array[String]): Unit = {
    //1.immutable
    val m1 = Map("scala1" -> 1, "scala2" -> 2)
    val m2 = m1 + ("scala3" -> 3)
    val m3 = m2 + ("scala4" -> 4, "scala5" -> 5)
    println(s"m3=$m3")
    val m4 = m3 + ("scala3" -> 30)
    println(s"m4=$m4")
    println(s"m3=$m3")
    val m5 = m4 - "scala4"
    println(s"m5=$m5")
    val m6 = m5 - "scala4" - "scala3"
    println(s"m6=$m6")
    val v1 = m1("scala1")
    println(s"v1=$v1")
    //    val v2=m1("scala3")
    //    println(s"v2=$v2")
    //option
    val v3 = m1.get("scala1")
    println(s"v3=$v3")
    val v4 = m1.get("scala4")
    println(s"v4=$v4")
    val v5 = m1.getOrElse("scala5", "default")
    println(s"v5=$v5")
    //mutable +=,++=,-= --=
    val mm1 = mutable.Map("java1" -> 1, "java2" -> 2)
    val r1 = mm1.put("java3", 3)
    val r2 = mm1.put("java1", 10)
    println(s"r1=$r1")
    println(s"r2=$r2")
    println(s"mm1=$mm1")

    val re1 = mm1.remove("java1")
    val re2 = mm1.remove("java8")
    println(s"re1=$re1")
    println(s"re2=$re2")
    println(s"reomve mm1=$mm1")

    //mm1.clear
    println(s"clear mm1=$mm1")
    //
    for ((k, v) <- mm1) println(s" for key=$k,value=$v")
    mm1.foreach(x => println(s" foreach key=${x._1},value=${x._2}"))
    mm1.keySet.foreach(println(_))
    mm1.values.foreach(println(_))

    if (mm1.contains("java2")) println("find " + mm1.get("java2")) else println("un find ")

  }
}

```

Scala的map其它常用操作

| **分类**      | **描述**       |
| ------------- | -------------- |
| 键值存在      | contains       |
| 键值排序/过滤 | retain，filter |
| 键值查找      | max            |

键值对操作

- 查找映射的最大键或值
- 按键或值排序
- 按键或值过滤

```scala
package scala07

import scala.collection.mutable

object RunMapSFM {
  def main(args: Array[String]): Unit = {
    //filter
    val mp = mutable.Map(1 -> "a", 2 -> "b", 3 -> "c")
    mp.retain((k, v) => k > 2)
    println(s"mp=$mp")
    val m = Map(4 -> "d", 5 -> "e", 6 -> "f")
    val m1 = m.filterKeys(_ > 4)
    println(s"m1=$m1")
    val m2 = m.filterKeys(Set(4, 6))
    println(s"m2=$m2")
    val m3 = m.filter(x => x._1 > 5)
    println(s"m3=$m3")

    //max/min
    val mm = Map("ab" -> 12, "e" -> 4, "byyy" -> 99, "muuuuu" -> 17)
    val mm1 = mm.max
    val min1 = mm.min
    println(s"max1=$mm1,min1=$min1")
    val minv = mm.valuesIterator.min
    val maxv = mm.valuesIterator.max
    println(s"minv=$minv,maxv=$maxv")

    val mink = mm.keysIterator.min
    val maxk = mm.keysIterator.max

    println(s"mink=$mink,maxk=$maxk")
    //*****
    val result = mm.keysIterator.reduceLeft((x, y) => if (x.length > y.length) x else y)
    println(s"result=${result}")
    //sort

    val sq1 = mm.toSeq.sortBy(_._1)
    val sq2 = mm.toSeq.sortBy(_._2)
    println(s"sq1=$sq1")
    println(s"sq2=$sq2")
    println(sq1.toMap)
    println(sq2.toMap)
    val sq3 = mm.toSeq.sortWith(_._2 > _._2)
    println(s"sq3=$sq3")
    println(sq3.toMap)

  }
}

```



## 3 Scala的集合性能

## 4 Scala的模式匹配

`match-case`中的模式匹配：

- 用于替代传统C/C++/Java的`switch-case`结构，但补充了更多功能，拥有更强的能力。
- 语法：（Java中现在也支持`=>`的写法了）

```scala
value match {
    case caseVal1 => returnVal1
    case caseVal2 => returnVal2
    ...
    case _ => defaultVal
}
```

- 每一个case条件成立才返回，否则继续往下走。
- `case`匹配中可以添加模式守卫，用条件判断来代替精确匹配。

```scala
def abs(num: Int): Int= {
    num match {
        case i if i >= 0 => i
        case i if i < 0 => -i
    }
}
```



### Scala的模式匹配语法

```scala
X match {

case1

case2

}
```

### Scala的模式数据类型

- String
- 类
- 变量
- 常量
- 其他复杂类型

### Scala的模式匹配

- 常量
- 变量
- 构造器
- 序列
- 元组
- 类型
- 变量绑定

```scala
object RunModel {
  def main(args: Array[String]): Unit = {
    //1.
    for (i <- 1 to 5) {
      i match {
        case 1 => println(1)
        case 3 => println(3)
        case 5 => println(5)
        case _ => println("even")
      }
    }

    def patternShow(x: Any) = x match {
      case Nil => println("empty List")
      case null => println("null")
      case true => println("true")
      case "scala" => println("scala")
      case _ => println("default")
    }

    patternShow(List())
    patternShow(null)
    patternShow(100)

    //2
    def patterVarible(x: Any) = x match {
      case x => println("varible")
      case 1 => println(1)
      case "string" => println("string")
    }

    patterVarible(1)
    for (i <- 1 to 10) {
      i match {
        case x if (x % 2 == 0) => println("even")
        case _ => println("odd")
      }
    }
    //3.tuple
    val t1 = (2, 3)
    val t2 = (4, 5, 6)
    val t3 = (7, 8, 9, 0)
    val t4 = (1, 2, 3, 4, 5)

    //(1,,,,,5)
    def patterTuple(x: Any) = x match {
      case (first, second) => println(s"first=$first,second=$second")
      case (x1, x2, x3, x4) => println(s"first=$x1,second=$x2,x3=$x3,x4=$x4")
      // case (x1,x2,x3,x4,x5)=>println(s"first=$x1,second=$x2,x3=$x3,x4=$x4,x5=$x5")
      case (x1, _, _, _, x5) => println(s"first=$x1,,x5=$x5")
      case _ => println("others")
    }

    patterTuple(t1)
    patterTuple(t2)
    patterTuple(t3)
    patterTuple(t4)
    //Seq
    val arr = Array(1, 3, 6, 7)
    val list = List(2, 9)
    val list1 = List(2, 3, 45, 56, 6, 0, 199)
    val list2 = List(2)

    def patterSeq(x: Any) = x match {
      case Array(first, second) => println(s"first=$first,second=$second")
      case Array(x1, x2, x3, x4) => println(s"first=$x1,second=$x2,x3=$x3,x4=$x4")
      //      case List(x1,x2,x3,x4)=> println(s"first=$x1,second=$x2,x3=$x3,x4=$x4")
      //      case List(x1,x2,x3)=> println(s"first=$x1,second=$x2,x3=$x3")
      case List(fisrt, s, _*) => println(s"*********first=$fisrt,s=$s******")
      case _ => println("others")
    }

    patterSeq(arr)
    patterSeq(list)
    patterSeq(list1)
    patterSeq(list2)

}

```

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
  
    ​	函数签名（Function Signature） 是指函数的参数类型、返回类型以及参数的位置信息（不包括函数名）。它是函数的核心特征，用于类型检查、重载解析和隐式转换匹配等场景。
  
- Scala的隐式类
  - Implicit class 类名（参数）{  }
  
  - 主构造函数必须只有一个参数
  
  - 隐式类的本质是编译器在编译时自动插入转换代码。当你调用一个类型没有定义的方法时，如果存在合适的隐式类，编译器会自动插入转换代码。
  
    ```scala
    // 原始代码
    "abc".increment
    
    // 编译器自动转换为
    new EnhancedString("abc").increment
    ```
  
    
  
- ##### 隐式参数

在方法定义里用 `implicit` 关键字

在调用该方法时，这些参数可以不用显式传递，编译器会自动寻找合适的隐式值来填充。

```scala
// 定义一个接收隐式参数的方法
def greet(implicit name: String): Unit = {
  println(s"Hello, $name!")
}

// 定义一个隐式值
implicit val defaultName: String = "Scala Developer"

// 调用方法时无需传递参数
greet // 输出: Hello, Scala Developer!
```

### 隐式值

用 `implicit` 关键字定义的变量

1. 隐式值的类型必须与隐式参数的类型相匹配。
2. 隐式值必须在当前作用域内，或者在参数类型的伴生对象中。
3. 同一个作用域内不能存在多个相同类型的隐式值，否则会引发歧义错误。

隐式对象



## 2 Scala的隐式转换规则

​	隐式转换是 Scala 中强大但需谨慎使用的特性，它通过自动类型转换增强了代码的灵活性，但也可能降低可读性。建议优先使用显式转换或类型类模式，仅在必要时使用隐式转换。

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

- 一般性原则
- 特殊性原则

Scala 与 Java 的互操作性是 JVM 生态的核心优势之一：

- **Scala 调用 Java**：直接调用，无缝集成，充分复用 Java 类库。
- **Java 调用 Scala**：需注意 Scala 特有语法的编译产物（如trait），但通过标准 JVM 字节码仍可轻松调用。

这种特性使得项目可以灵活选择语言（如用 Scala 编写业务逻辑，用 Java 调用成熟类库），最大化开发效率。

### Scala与Java的集合交互

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



### Scala的Trait在Java调用

Java 虽无原生 Trait，但通过**接口 + 默认方法 + 静态方法**可以模拟其核心功能：

•Java使用Trait

​	•implements

•使用Trait方式

​	•对该trait扩展

​	•直接调用



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
  - class 类名\[T](参数)
  - class 类名\[S,T…](参数)
- Scala泛型Trait
  - trait 类名[T]
  - trait 类名[S,T…]
- 泛型类和特质

```scala
package Scala10

class RunCTrait {

}

object RunCTrait {
  def main(args: Array[String]): Unit = {
    val animal = new Animal[String, Int]("wangwang", 5)
   // val animal1:Animal[String, Int]=new Animal("abc",19)
    println(s" age =${animal.getAge()},type=${animal.getAge().getClass.getSimpleName}")
    println(s" name =${animal.getName()},type=${animal.getName().getClass.getSimpleName}")
    animal.setAge(9)
    animal.setName("laipigou")
    println(s" age =${animal.getAge()},type=${animal.getAge().getClass.getSimpleName}")
    println(s" name =${animal.getName()},type=${animal.getName().getClass.getSimpleName}")
  val d=  new Dog("dog1",100)
    println(s" dog age =${d.getAge()},type=${d.getAge().getClass.getSimpleName}")
    println(s"dog  name =${d.getName()},type=${d.getName().getClass.getSimpleName}")
    val language=new BigData()
   println(language.getLanguage("hadoop"))
  }
}

class Animal[T1, T2](var name: T1, var age: T2) {
  def getName(): T1 = {
    name
  }

  def getAge(): T2 = {
    age
  }

  def setName(name: T1): Unit = {
    this.name = name
  }

  def setAge(age: T2): Unit = {
    this.age = age
  }
}
class Dog(name:String,age:Int)extends Animal[String,String]("aninmal","99"){
  override def getAge(): String = "88"
}
trait LanguageMap[A,B]{
  def getLanguage(key:A):B
}
class BigData extends LanguageMap[String,String]{
  val map=Map("spark"->"scala","hadoop"->"java","kafka"->"scala")
  override def getLanguage(key: String): String = map.getOrElse(key,"c")
}
```



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

定义一个方法，将一个数组的元素拷贝到一个List集合

```scala
package Scala10

import scala.collection.mutable.ListBuffer

object RunFunction {
  def main(args: Array[String]): Unit = {
    add(2, "scala")
    add("java", "hadoop")
    add[String, Int]("flume", 3)
    //
    val c = copy(Array("123", "java"), ListBuffer[String]())
    println(c)
  }

  def add[S, T](x: S, y: T): Unit = {
    println(s"x=$x,type=${x.getClass.getSimpleName},y=$y,type=${y.getClass.getSimpleName}")
  }

  def copy[T](arr: Array[T], lb: ListBuffer[T]): ListBuffer[T] = {
    arr.foreach(x => lb += x)
    lb
  }
}

```

•Scala单参数通配符

```scala
def 方法名 (类型[_]){

}

def 方法名 (类型[T] forSome {type T}){

}
```

•Scala多参数通配符

```scala
def 方法名 (类型[_,_...]){

}

def 方法名 (类型[T,U…] forSome {type T；type U；…}){

}
```



在List集合使用通配符

```scala
package Scala10

object RunSymbol {
  def main(args: Array[String]): Unit = {
    printAll(List[String]("spark", "flink"))
    printAll(List[Int](2, 3))
    printAllsimple(List[String]("hadoop", "hbase"))
    printMap(Map[String, String]("spark" -> "Scala", "flink" -> "java"))
    printMap(Map[String, Int]("spark" -> 2, "flink" -> 1))
  }

  def printAll(list: List[T] forSome {type T}): Unit = {
    list.foreach(x => print(s"x=$x,type=${x.getClass.getSimpleName} ,"))
    println()
  }

  def printAllsimple(list: List[_]): Unit = {
    list.foreach(x => print(s"x=$x,type=${x.getClass.getSimpleName} ,"))
    println()
  }

  def printMap(map: Map[_, _]) = {
    map.foreach(x => println(s"key=${x._1},keyType=${x._1.getClass.getSimpleName},value=${x._2},valueType=${x._2.getClass.getSimpleName}"))
  }
}

```



## Scala的泛型界定

Scala的界定

- 上下界界定
- 视图界定
- 上下文界定
- 多重界定



•定义一个能比较任意对象大小的方法

```scala
package Scala10

object RunCompare {
  val t1 = new Teacher("lilei", 90)

  def main(args: Array[String]): Unit = {
    val r1 = compare("1", "2")
    println(s"r1=$r1")
    val r2 = compareWithInt(4, 5)
    println(s"r2=$r2")
    val bigperson = compare(Person("java", 30), Person("scala", 5))
    println(s"bigperson=$bigperson")
  }

  def compare[T <: Comparable[T]](x: T, y: T): T = {
    if (x.compareTo(y) > 0) {
      x
    } else {
      y
    }
  }

  def compareWithInt[T <% Comparable[T]](x: T, y: T): T = {
    if (x.compareTo(y) > 0) {
      x
    } else {
      y
    }
  }

  case class Teacher[T1, T2 <: AnyVal](var name: T1, age: T2)
  //  val t2=new Teacher("lilei","90")
}

case class Person(var name: String, var age: Int) extends Comparable[Person] {
  override def compareTo(o: Person): Int = {
    if (this.age > o.age) 1
    else if (this.age == o.age) 0
    else -1
  }
}
```



## Scala的型变

### Scala的型变

- 不变
- 协变
- 逆变

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

课堂案例

- •自定义Container演示不变性。
- •自定义Printer演示逆变
- •利用集合演示协变

```scala
package Scala10

import Scala10.RunTypeVarible.Person10

object RunTypeVarible extends App {
  val s1: Person10 = new Student10("s101")
  val s2: Container[Student10] = new Container[Student10](Student10("stu02"))
  val students = List[Student10](Student10("stu05"), Student10("Stu06"))
  val teachers = List[Teacher10](Teacher10("tea05"), Teacher10("tea06"))
  val stuprinter = new StudentPrinter
  val perprinter = new PersonPrinter

  //val c2:Container[Person10]=s2
  //2
  def printAll(persons: List[Person10]): Unit = {
    persons.foreach(person => println(person.name))
  }

  def printStudent(value: Printer[Student10]): Unit = {
    value.printName(Student10("studentprinter"))
  }

  abstract class Person10 {
    def name: String
  }

  println(students)
  println(teachers)
  printAll(students)
  printAll(teachers)

  //3
  abstract class Printer[-T] {
    def printName(value: T)
  }

  //1
  class Container[T](value: T) {
    private var _value = value

    def getValue() = {
      _value
    }

    def setValue(value: T): Unit = {
      _value = value
    }
  }

  case class Student10(name: String) extends Person10

  case class Teacher10(name: String) extends Person10

  class PersonPrinter extends Printer[Person10] {
    override def printName(value: Person10): Unit = {
      println(s"person name is ${value.name}")
    }
  }

  class StudentPrinter extends Printer[Student10] {
    override def printName(value: Student10): Unit = {
      println(s"student name is ${value.name}")
    }
  }
  printStudent(stuprinter)
  printStudent(perprinter)
}

```



## Scala的高级类型





# 补充：

# Scala IO

## Scala 文件 I/O

```java
import java.io._

object Test {
   def main(args: Array[String]) {
      val writer = new PrintWriter(new File("test.txt" ))

      writer.write("菜鸟教程")
      writer.close()
   }
}
```



## 从屏幕上读取用户输入

```scala
import scala.io._
object Test {
   def main(args: Array[String]) {
      print("请输入菜鸟教程官网 : " )
      val line = StdIn.readLine()

      println("谢谢，你输入的是: " + line)
   }
}
```



## 从文件上读取内容

```scala
import scala.io.Source

object Test {
   def main(args: Array[String]) {
      println("文件内容为:" )

      Source.fromFile("test.txt" ).foreach{ 
         print 
      }
   }
}
```



# 案例类

案例类（Case Class）是一种特殊的类，专为不可变数据建模而设计。它们自动生成大量样板代码，简化了数据处理和模式匹配，是函数式编程的核心工具之一。

## 定义案例类

在类名前加上 `case` 关键字

```scala
case class Person(name: String, age: Int)
```

这个定义会自动为 `Person` 类生成以下内容：

1. **构造函数**：可以直接通过类名调用，例如 `Person("Alice", 30)`。
2. **不可变字段**：所有参数默认是不可变的（`val`），因此不能修改。
3. **`equals` 和 `hashCode` 方法**：自动重写，使得两个案例类实例可以通过值比较。
4. **`toString` 方法**：自动重写，返回类名和参数列表，例如 `Person(Alice,30)`。
5. **`copy` 方法**：用于创建类的副本，可以修改某些字段。
6. **`unapply` 方法**：用于模式匹配。

## 使用案例类

```scala
//定义
case class Person(name: String, age: Int)

// 使用 apply 方法创建实例（无需 new）
val alice = Person("Alice", 30)
val bob = Person("Bob", 25)

println(person.name) // 输出 Alice
println(person.age)  // 输出 30

// 自动生成的方法
println(alice.toString)   // 输出: Person(Alice,30)
println(alice == bob)     // 输出: false
println(alice.copy(age = 31))  // 输出: Person(Alice,31)

//模式匹配
person match {
  case Person(name, age) => println(s"Name: $name, Age: $age")
}

```

### 默认参数与可选参数

```scala
case class Person(name: String, age: Int = 30)
val person = Person("Alice") // 使用默认的 age 值
```

### 与特质（Trait）的区别

- **案例类**：可实例化，用于表示数据。
- **特质（Trait）**：不可实例化，用于定义行为（类似 Java 接口 + 默认方法）。

```scala
trait Printable {
  def print: Unit
}

case class Person(name: String) extends Printable {
  def print: Unit = println(s"Person: $name")
}
```

## 案例类与普通类的对比

| 特性                | 案例类（Case Class） | 普通类（Class）           |
| ------------------- | -------------------- | ------------------------- |
| 构造无需 `new`      | ✅                    | ❌（除非手动实现 `apply`） |
| 自动生成 `equals`   | ✅                    | ❌（需手动实现）           |
| 自动生成 `hashCode` | ✅                    | ❌（需手动实现）           |
| 自动生成 `toString` | ✅                    | ❌（需手动实现）           |
| 自动生成 `copy`     | ✅                    | ❌（需手动实现）           |
| 默认不可变          | ✅（参数为 `val`）    | ❌（参数默认私有）         |
| 模式匹配支持        | ✅                    | ❌（需手动实现 `unapply`） |

# 并发与异步

1. ## Future 异步编程

   ```scala
   import scala.concurrent._
   import ExecutionContext.Implicits.global
   
   val future: Future[Int] = Future {
     Thread.sleep(1000)
     42
   }
   
   future.map(_ * 2).foreach(println)
   ```

   

2. ## Actor 模型（Akka）

   ```scala
   import akka.actor._
   
   class HelloActor extends Actor {
     def receive = {
       case "hello" => sender() ! "world"
     }
   }
   ```

   

# 高频面试题

1. **Scala 与 Java 的区别**
   - Scala 更函数式，支持不可变数据、高阶函数等。
   - Scala 类型系统更强大（泛型、协变 / 逆变、隐式转换）。
   - Scala 语法更简洁（案例类、模式匹配、特质）。
2. **为什么使用 Option 而非 null**
   - 避免空指针异常（NullPointerException），强制处理可能缺失的值。
3. **模式匹配 vs switch 语句**
   - 模式匹配更强大，支持类型匹配、集合解构、守卫条件等。
