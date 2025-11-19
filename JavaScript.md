<img src="http://img.an520.com/test/mywechat.jpg" width="200px"><img src="http://img.an520.com/test/mypublic.jpg" width="240px">

# 一、初识JavaScript

## 	1 什么是JavaScript

JavaScript是一种**基于对象和事件驱动**的**客户端脚本语言**

​		编程语言，一般用于开发交互式页面。

​		功能强大，作用：表单动态校验、网页特效、前端开发（web+APP+小程序）、服务端开发(Node.js)、桌面程序(Electron)、App(Cordova)、控制硬件-物联网(Ruff)、游戏开发(cocos2d-js)、动画（animate.js）、数据库(MongoDb)。

**网页组成：**

- ​		HTML
- ​		CSS
- ​		JavaScript 

JS内嵌在网页中，通过浏览器内置的JS引擎解释并执行（主要运行在浏览器中）
		
浏览器分类：  
		浏览器内核（Rendering Engine）组成：

- ​			渲染引擎（排版引擎）：解析HTML与CSS，比如Chrome浏览器的Blink
- ​			JS引擎：是JavaScript的解释器。比如Chrome浏览器的V8引擎。

JS代码的执行特点：逐行执行
		
常用的JS框架： React.js  Angular.js  Vue.js(尤雨溪) 
		
JS的特点：

-   解释性脚本语言    

  - 不需要编译，比如JavaScript、 Python、 PHP 
  - 编译语言(JAVA、 C++、Go)  

-   跨平台（不依赖操作系统，只需要浏览器的支持）  

-   支持面向对象（C语言不支持面向对象，函数式编程）  

-   简单性 ：  

-   弱类型：  

  var name;//弱类型  
  var string name;//强类型

**JS的组成：**

- ​	ECMAScript：基本语法，是JS的核心。
- ​	DOM（Document Object Model）: 文档对象模型，操作网页元素。
- ​	BOM: 浏览器对象模型，操作浏览器窗口。

## 2 常用开发工具

​		VS code、 Hbuilder、 Sublime text、 DreamWeaver、 WebStorm等

​		vs code下载安装：  
​		官网 https://code.visualstudio.com/  
​		安装插件：  
​			chinese, open in browser

## 3 JavaScript入门

JS代码的3种书写位置  
	行内式：写HTML标签事件属性中（onclick oninput onmousemove）

```javascript
	<input onmousemove="console.log('这是鼠标抚摸事件！')" oninput="alert('你的输入错误！')" type="text" />用户名
	<br />
	<input onclick="alert('你提交成功！！')" type="buttion" value="提交" />
```

​	内嵌式（嵌入式）：将JS代码写在`\<script>`标签中,`<script>`放在\<head>或者\<body>里面

```javascript
<script>
		var a = 11;
		var b = 22;
		var c = a+b;
		console.log(c)
		// alert(c)
</script>
```

​	外部式(外链式):将JS代码写在单独的文件中,扩展名".js"。通过script标签引入

```javascript
	<script src="js/test.js"> </script>
```

语法规则：

- ​			js严格区分大小写
- ​			对空格、换行、缩进（tab）不敏感
- ​			每行结束的英文分号";"可以省略, 但是推荐加上


注释：

- ​			单行注释：//   	快捷键：ctrl+/
- ​			多行注释：/* */ 	快捷键：ctrl+shift+/

```javascript
	// var a = 1;
	// alert(1)
```
```javascript
/* var a = 2;
	alert(a) */
```
输入输出语句：

- ​			alert('自定义信息')  //弹出警告框
- ​			console.log('自定义信息') //控制台输出信息
- ​			prompt('自定义信息') //弹出输入框

```javascript
	alert('这是警告框');
	console.log('每一个星球都有一个驱动核心，每一种思想都有影响力的种子。感受世界的温度，年轻的你也能成为改变世界的动力，百度珍惜你所有的潜力。你的潜力是改变世界的动力！');
	prompt('请你输入年龄！');
```
```javascript
	<script>
		var a = document.getElementById('box');
		a.innerHTML = '哈哈哈哈';
	</script>
```

控制台的使用：F12 - console/控制台

## 4 JavaScript变量

变量是内存中的一块空间。
​			**声明:** 

```javascript
var age;
```

​			赋值: 

```javascript
age = 18;	
```

声明同时赋值:

```javascript
				var age = 18;
```

注意：可以不声明直接赋值，但是不标准。
​	
变量命名规范：

1. ​			由字母 数字 下划线 美元符号$组成。（中文不推荐）
2. ​			严格区分大小写。
3. ​			不能以数字开头
4. ​			不能是关键字，保留字。

​				关键字比如 break if console  
​					在js中已经被使用了的单词。js本身已经赋予其功能  
​				保留字  
​					在未来js标准中可能被用来作为关键字的单词  

5. ​			合理命名，“见其名知其意”  
6. ​			三种命名法：

- ​				小驼峰命名法  
- ​				大驼峰命名法 
- ​				下划线命名法 

​				

​	1 小驼峰命名法

```javascript
//小驼峰 第一个单词首字母小写，后面的单词首字母大写
var mySchoolAddress = '重庆涪陵';
```

​	2 大驼峰命名法

```javascript
//大驼峰 第一个单词首字母大写，后面的单词首字母大写
var MySchoolAddress = '重庆涪陵';
```

​	3 下划线命名法

```javascript
//下划线 用下划线分割
var my_school_address = '重庆涪陵';
```

# 二、JS基础语法

## 	1 数据类型

​		JS是**弱类型**语言，不用提前声明变量的数据类型

​		弱类型语言： JavaScript PHP ...   
​		强类型语言：Python  Java C C++ GO ...

```javascript
	var name;
	var age ;
```
​	分类：  
​	**基本**数据类型和**复杂**数据类型（**引用**数据类型）  
​		基本数据类型(5种)：Boolean（布尔型） String字符型  Number数字类型  Null空  Undefined未定义      

​		引用数据类型(复杂数据类型)：Object（对象）			  
​

​		基本数据类型（5种）：  
​			1）Number 数值型、数字类型  
​				包括整数和浮点数（小数）、NaN 非数值、isNaN 判断变量是否为非数字类型，结果为true非数字，false数字  

```javascript
	//整数
	var age = 18;
	//浮点数（小数）
	var hotpotPrice = 99.99;
	//最大值
	var max = Number.MAX_VALUE;
	//最小值
	var min = Number.MIN_VALUE;
	//无穷大
	var c = Infinity;
	//无穷小
	var d = -Infinity;
```
```javascript
	// NaN 非数值
	// isNaN 判断非数值，true非数字，false数字
	console.log( isNaN("abcdefg") )
```
​			2）String 字符类型  
​				用单引号''或者双引号""来包裹  
​					单引号里面可以加双引号，但是不能加单引号（要转义）  
​					双引号里面可以加单引号，但是不能加双引号（要转义）  
​				常见的转义符：\n换行 \'单引号 \"双引号  \\反斜杠  
​				字符串长度：length属性  

```javascript
		var str1 = '这是一个字符串';
		var str2 = "这也是一个字符串";
```
​				常见的转义符：\n换行 \'单引号 \"双引号  \\反斜杠  。。。  
​				字符串长度：length属性 

```javascript
var test="                ";
var long = test.length;
```
​			访问字符串中的字符：[index]，如果超过最大值，返回undefined  
​					
​			拼接字符串: 加号"+" 

```javascript
	var str2 = '这是一个字符串';
	var index = str2.length - 1;
	alert(str2[index])
```
```javascript
		var str1 = '明天是\'星期六\'!!';
		console.log('字符串长度：'+str1.length)
		console.log('字符串索引：'+str1[6])
		var first = '520';
		var second = '10';
		var name = first + second;
```
​			3）Boolean 布尔类型 ：true 和false    

​			4）null   空型    

​			5）undefined 未定义型

```javascript
//null  空型	
var a = null;
//判断是否null
if (a === null) {
  alert('这是null型')
}
```
```javascript
	//	undefined 未定义型
	var test;
	//声明但未赋值
	alert(test)
```
​		复杂数据类型（引用数据类型）：Object(对象)  
​
​		检测变量的数据类型: typeof 

```javascript
var result = true;
console.log(typeof result)
```

## 2 数据类型转换

​	转化为字符串类型：  

- ​				"+" 拼接字符串
- ​				toString() 
- ​				String() 方法

```javascript
	var result = undefined;
	console.log(typeof result)
	// result = result + ""
	// result = result.toString();
	result = String(result)	
	console.log(typeof result)
```
​	转化为数字类型：

- ​		parseInt()  转整数
- ​		parseFloat()  转浮点数（小数）
- ​		Number() 
- ​		算术运算符隐式转换(-、*、/)

```javascript
	var result = "111.000";
	console.log(typeof result)	
	// result = (result) - 1 ;
	result = parseInt(result)
	result = parseFloat(result)
	console.log(result)
	console.log(typeof result)
```
​	转化为布尔型: Boolean()  
​		没有意义的值会转为false，比如0 '' null undefined NaN  
​		其他的转为true

## 3 运算符

算术运算符：+ - * /  %(取模，取余数)  

递增（自增）、递减（自减）运算符：++ 、--  
	i++ 等同于 i = i + 1，变量+1
	i-- 等同于 i = i - 1，变量-1
	x++和++x 
				相同点：结果加1， x = x + 1;
				不同点：x++返回值不变，++x返回值+1
	i++和++i的区别：
			i++返回计算前的结果
			++i返回计算后的结果

​	优先级高于算术运算符

比较运算符：结果是布尔值，true或者false
	常见的： >  < >= <=  ==等于  !=不等于  ===全等 !==不全等

```javascript
	console.log('' == 0);
	console.log('' === 0);
```

逻辑运算符： 返回布尔值，，true或者false
	&&，与，和
		a&&b，a和b都是true，结果才是true
	||, 或
		a||b，a或者b有一个是true，结果就是true
	!, 非，否定
		 !a，a是false，结果就是true

位运算符：

赋值运算符：将运算符右边的值赋给左边的变量
	常用的：=  += -= /= *=  %/
	= 
	+= 
		x += y; 等同于 x = x +y
	-=  
		x -= y; 等同于 x = x - y
	*=
	/=
	%=

三元运算符： 条件表达式 ? 表达式1 : 表达式2

```javascript
'100'=="ok" ? alert('吃火锅') : alert('吃小面');
```

运算符优先级：小括号>算术运算符>比较运算符>逻辑运算符>赋值运算符

## 4 流程控制

顺序结构：默认，逐行执行

分支结构：根据条件 控制执行  
	单分支：单个条件表达式  
		if(条件表达式){  
			//代码段  
		}

```javascript
	if ( true ) {
		alert('吃火锅')
	}
```
双分支：  
​		if(条件表达式){  
​			//代码段1  
​		} else {  
​			//代码段2  
​		}  

```javascript
	var a = prompt("你喜欢我吗？yes or no ?")
	if ( a == 'yes' ) {
		alert('我也喜欢你！')
	}else {
		alert('你是好人！')
	}
```
多分支：多个条件表达式  
​		switch能写的，一定能写。反之则不然。  
​		if(条件表达式1){  
​			//代码段1  
​		} else if(条件表达式2) {  
​			//代码段2  
​		}else if(条件表达式3) {  
​			//代码段3  
​		}else{  
​			//代码段x  
​		}  
​	
​	switch语句：也是多分支，功能与if..else if类似。  
​			只有一个表达式。**break不能少**。  

​		switch(表达式) {  
​			case '值1':  
​				//代码段1  
​				break;  
​			case '值2':  
​				//代码段2  
​				break;  
​			default:  
​				//代码段n  
​		}

- 循环结构：重复执行
	for循环：适合循环次数已知。
```
	for(初始化变量; 条件表达式（循环条件）; 操作表达式（每次循环后的操作） ){
		//循环体
	}
```
​	断点调试：    

数组：  

​	循环结构：重复执行  
​		for循环：适合循环次数已知。

```
	for(初始化变量; 条件表达式（循环条件）; 操作表达式（每次循环后的操作） ){
		//循环体
	}
```

断点调试

while循环：先判断条件再执行。for循环可以改成while循环
	适合循环次数未知。可以和for循环互相改

```
	while(条件表达式){
		//循环体
	}
```
​	do...while循环：无条件执行一次循环体，再判断条件

​	断点调试：
​	
​	continue(继续):跳过后面的循环代码，继续下一次循环
​		如果是多层循环，只能跳过最近的循环体。
​		如果要跳过外层循环，需要加标签：continue 标签名；
​		
​	break(打断)：跳过整个循环体，终止循环了
​		如果是多层循环，打断最近的循环体。
​		如果要打断外层循环，需要加标签：break 标签名；

数据结构			

## 数组

- ​	数组是值的**有序**集合

- ​	JavaScript是弱类型，在同一个数组中可以存放**多种类型**的元素

- ​	长度可**动态调整**


​	**创建数组**：[] 或者 new Array()

```javascript
	var arr1 = [];
	var arr2 = new Array();
	var color = ['red','green','yellow','purple','pink','white',1,true,null]
```
​	**访问数组元素**： 数字索引,**从0开始**

```javascript
	console.log(color[6]);
```
​	**数组长度**：.length

​	**数组遍历**：将数组元素全部访问一遍	
​		for循环，循环次数.length-1
​		for...in
​		for...of

​	修改数组长度：arr.length = 长度值

​	新增或者修改数组元素：通过索引

​	二维数组：
​		创建二维数组：[]或者new Array()
​		遍历二维数组：双层for循环

函数(function 方法)

函数的使用
	声明函数:
		function 函数名(){
			//代码
		}
	**调用函数**:
		函数名()

```javascript
	function sayHi(){
		console.log('hi')
	}

	sayHi()
```

## 函数

什么是函数：代码复用

```javascript
//函数，计算累加和
function getSum(number1, number2) {
	var sum = 0;
	for (var i = number1; i <= number2; i++) {
		sum += i;
	}
	console.log(sum)
}

getSum(1,200)
getSum(100,200)
```

函数参数：
	形参：函数声明时的参数
		function 函数名(参数1，参数2。。。){
			//代码
		}
	实参：函数调用时的参数
		函数名(参数1,参数2...)

函数参数的数量：		
	形参个数小于实参：undefined
	形参个数大于实参：忽略多余的参数
		
返回值：推荐必须加上返回值，**终止并且返回**
	function 函数名(参数1，参数2。。。){
		//代码
		return 返回值;//终止并且返回
	}

​	如果一个函数没有指定返回值，它默认返回`undefined`

return 可以提前终止函数：

arguments :接收所有的实参, arguments是一个对象


函数进阶：			

函数进阶：
	匿名函数：没有函数名称

```
	function(参数1,参数2...){
		//代码
		return 结果;
	}
```
```
		//调用匿名函数
		(function(参数1，参数2。。。){
			//代码
			return 返回值;//终止并且返回
		})()
```

函数表达式：

1. ​		将声明的匿名函数赋值给一个变量，通过变量调用函数。
2. ​		函数表达式必须写在调用前

​		语法：  
​		var 变量名 = function(参数1，参数2。。。){  
​			//代码  
​			return 返回值;//终止并且返回  
​		}  
​		变量名() //调用

```javascript
	var sayHi = function(){
		console.log('hello world')
	}
	sayHi()
```

回调函数： 将函数作为参数传递给另外一个函数

```javascript
	//参数fn是一个匿名函数, 叫做回调函数
	function cal(num1, num2, fn) {
		return fn(num1, num2)
	}
```

递归调用：函数自己调用自己

作用域：  
	全局变量：在整个页面生效  
		不在函数内声明的变量，或者函数内省略var声明的变量  
		在浏览器页面关闭的时候，才会销毁，比较占用内存  
	局部变量：函数内用var声明的变量  
		只能在当前函数内使用。不能在函数外面使用。  
		在函数执行完就会销毁，比较节省内存  
	块级变量：let关键字, 通过let声明, 仅在{}里面有效，比如if、for、while  

作用域链：由内向外查找变量（函数里面可以用外面的，但是函数外面不能用函数里面的）  
	首先在当前函数内查找，如果找不到，则向上一级函数继续查找，直到全局变量（全局作用域）。
	
闭包函数：有权访问另一函数作用域内变量(局部变量)的函数  
	1 函数外部读取函数内部的变量  
	2 让变量常驻内存

# 三、对象编程

对象（object）：万物皆可对象、面向对象编程OOP  
	对象是一种数据类型，由属性和方法组成。  
	属性：事物的特征，通过"对象.属性"访问  
	方法：事物的行为，通过"对象.方法名()"访问  

## 自定义对象

创建对象：

1 利用**字面量**创建对象：  
	1 用大括号"{}"包裹  
	2 每个成员通过键值对（key:value）形式保存，key是属性名或者方法名，value是对应的值  
	3 每个成员之间用逗号,分隔

```javascript
	var car = { };
```
访问对象的属性和方法：  

​	访问对象的属性：对象.属性名 或者 对象['属性名']  
​	
​	访问对象的方法：对象.方法名() 或者 对象['方法名']()  

​	当对象成员包含特殊字符，可以用字符串表示。  
​			
​	手动赋值属性或者方法：  
​		对象.属性名 或者 对象.方法名  

​	this关键字：代表当前对象

2 用**new Object**创建对象：

```javascript
	var car = new Object();
```

3 用**构造函数(模板)**创建对象：
构造函数名一般首字母大写
//编写构造函数
function 构造函数名(){
	this.属性名 = 属性;
	this.方法名 = function(){
		//方法体
	}
}

//使用构造函数创建对象
var obj = new 构造函数名();

静态成员：不需要创建实例对象就能使用。
	静态属性和静态方法

遍历对象的属性和方法： for...in

判断对象成员是否存在： in运算符

```javascript
	for (var k in shuaige) {
		console.log(k)	//k是属性名或者方法名
		console.log(shuaige[k])
	} 
```

什么是JSON
	JSON：JavaScript Object Notation,即JavaScript对象标记
	JSON 独立于语言，适用多种语言
	JSON是一种便于阅读和书写的数据交换格式

​	主要作用： JSON 是用于存储和传输数据的格式

	JSON对象格式：{"key":"value","key":"value",....} 
	键和值使用冒号分隔，key必须使用双引号，value如果没有使用双引号表示变量

## 内置对象

​	---不用编写，直接使用的对象
​	通过查阅文档熟悉内置对象: mdn
​		官方文档：https://developer.mozilla.org/zh-CN/docs/Web/JavaScript

### Math对象：

​	数学相关的运算, 不需要实例化,不是构造函数
​		Math.round(x)    四舍五入
​		Math.floor(x)      向下取整
​		Math.ceil(x)	向上取整
​		Math.abs(x)	绝对值

​	Math.random()  获取大于等于0.0 小于1.0的随机数

```javascript
	//大于等于min,小于max的随机值
	Math.random() * (max - min) + min
	//获取min-max之间的随机整数
	Math.floor( Math.random() * (max - min + 1) + min )
	
	//1-任意数之间,可以等于1
	Math.floor( Math.random() * (max +1) + 1)		
//获取基数的指数次幂
	console.log( Math.pow(10,2) )  //10的平方
	//开根号
	console.log(Math.sqrt(9)) 
```
生成指定范围的随机数: Math.random()

```javascript
	//min-max 之间的随机整数
	Math.floor(Math.random() * (max - min + 1) + min)
```

### 日期对象：

需要实例化 new Date()  
	日期对象Date的使用  
		首先使用new Date()实例化  
	日期对象Date的常用方法:
			获取日期
			设置日期
			

时间戳： 当前时间，单位毫秒，  默认从1970-01-01 00:00:00到当前时间的毫秒数

1秒= 1000毫秒

```javascript
		var date = new Date();
		//获取 时间戳
		var time1 = date.getTime()
		var time2 = date.valueOf()
```

### 数组对象:

​	数组类型检测：instanceof Array或者 Array.isArray()

```javascript
	//第一种方法
	var res = c instanceof Array //true
	//第二种方法
	var res = Array.isArray(a) //false
```
添加或者删除数组元素：在数组的开头或者结尾，添加或者删除元素  
	添加： 结尾push(参数)   	开头unshift(参数)   
	删除： 结尾pop()  		头部shift()

修改数组元素：通过索引  

数组排序：   
	顺序（从小到大） ： sort()
	颠倒顺序： reverse()

数组索引：通过元素查找索引  
	indexOf() 返回给定值的第一个索引，如果不存在则返回-1
	lastIndexOf()	返回给定值的最后一个索引，如果不存在则返回-1

数组转为字符串：  
		toString()	用逗号连接数组元素
		join('分隔符')	用分隔符连接数组元素

其它方法：  
	fill()	填充数组元素  
		方法用一个固定值填充一个数组中从起始索引到终止索引内的全部元素。不包括终止索引。

​	splice(第几个开始，要删除的个数)	删除数组元素
​		
​	slice(begin,end) 	截取数组元素  
​		方法返回一个新的数组对象，这一对象是一个由 begin 和 end 决定的原数组的浅拷贝（包括 begin，不包括end）。原始数组不会被改变。
​	
​	concat()	合并多个数组

### 遍历数组   

​	forEach，map，filter，reduce，some，every这6种遍历方法。    

​	forEach 遍历数组中的元素，对每个元素执行相应的操作。

```javascript
//foreach 语法：
[ ].forEach(function(value,index,array){
　　//code something
});
```



### 字符串对象：

​	1 String对象的创建:  
​		语法：  
​		new String(参数);  
​		或者  直接使用双引号（单引号）定义字符串

​	new String('字符串')

```javascript
var str1= new String('hello world')

var str2= 'hello world'
```

2 String对象常用属性和方法:  
属性，返回数组长度： length
	
根据字符返回位置(索引)：通过字符查找索引  
	indexOf(searchValue, fromIndex): 找到value首次出现的位置，不存在则返回-1
		searchValue要被查找的字符串值
		fromIndex 开始查找的位置，默认0
	lastIndexOf(value): 找到value最后出现的位置，不存在则返回-1

根据位置（索引）返回字符：  
	str[索引]		通过索引查找字符
	charAt(index) 根据位置(索引)查找字符
	charCodeAt(index)	根据位置(索引)获取字符的ASCII码
	char[index]	获取指定位置的字符

其他方法：  
	str.concat(str2, [, ...strN])  			连接多个字符串  
	str.slice(beginIndex[, endIndex])		截取字符串
	str.substring(indexStart[, indexEnd]) 	截取字符串，但是不接收负值
	str.substr(start[, length])				截取字符串，接收长度
	str.toLowerCase() 						转小写
	str.toUpperCase()  						转大写
	str.split([separator[, limit]])			将字符串分割成数组
	str.replace(substr, newSubStr)			替换（修改）字符串中的字符
	str.trim() 删除字符串前后空白
	str.trimStart() str.trimEnd()

​	值类型和引用类型  
​		值类型：基本数据类型(5种)：Boolean（布尔型） String字符型 Number数字类型 Null空 Undefined未定义  
​	
​		引用类型：引用数据类型(复杂数据类型)：Object（对象）  
​		
​		值类型是赋值传值：不会改变原来的变量值，因为赋值是单独复制一份  
​			赋值传值：将变量复制一份
​		引用类型是引用传值：会改变原来的变量值，因为赋值的是内存地址
​			引用传值：传递的是变量地址  
​	
​	垃圾回收机制  
​		js垃圾回收机制自动释放：

### 正则表达式

什么是正则表达式：（匹配字符串中的字符）  
	是一种描述字符串结构的语法规则  
	用于匹配字符串中字符组合的模式  
	也是对象
		RegExp对象是Regular Expression（正则表达式）的缩写  
		正则表达式是一个描述字符模式的对象，
		组成的字符模式用来匹配各种表达式。

**创建正则表达式**  
	字面量方式（普通方式）：
		var reg = /表达式/附加参数
	RegExp构造函数的方式
		var reg = new RegExp(“表达式”,”附加参数”)；
		​或者
		var reg = new RegExp(/表达式/)  
		​或者 
		var reg = RegExp(/表达式/)

正则表达式的操作方法  
	compile()方法 
	exec()方法，用于检索
		返回一个结果数组，或者返回 null
	test()方法，用于检测是否匹配
		返回 true 或者 false

正则表达式的模式  
	简单模式：普通字符的组合

```javascript
var reg=/abc0d/;
```

​	复合模式：含有通配符

```javascript
var reg=/a+b?\w/;
```

​		复合模式-**方括号、常用字符含义、量词**

```javascript
   //创建正则表达式， 用户名由英文字母和数字组成的4-16位字符，以字母开头
    var reg = /^[a-zA-Z][a-zA-Z0-9]{3,15}$/
    if (reg.test(user) == false) 
        return false //结束验证
    }
    return true //验证通过

	/*验证邮箱*/
 	var reg=/^\w+@\w+\.(com)$|(cn)$/;
    if(reg.test(email)==false){
		return false;
	}
	return true;
```

| **表达式** | **描述****(****表示****“或”****，和****\|****符号等价****)** |
| ---------- | ------------------------------------------------------------ |
| [abc]      | 匹配方括号之间的任意**1****个**字符。等价于a\|b\|c           |
| [^abc]     | 查找任何不在方括号之间的任意**1****个**字符。                |
| [0-9]      | 查找任何从  0 至  9 的任意1个数字。注意范围可以改变，例如**[2-8]**表示查找2至8的任意1个数字 |
| [a-z]      | 查找任何从小写  a 到小写  z 的任意1个字符。                  |
| [A-Z]      | 查找任何从大写  A 到大写  Z 的任意1个字符。                  |

| **符号** | **描述**                          | **说明**                   |
| -------- | --------------------------------- | -------------------------- |
| *        | *前的一个字符出现0次或多次        | /a*b/可匹配b,aab,aaaab……   |
| **+**    | +前的一个字符出现1次或多次        | /a+b/可匹配ab,aaab,aaaab…… |
| ？       | ?前的一个字符出现0次或1次         | /a[cd]?/可匹配a,ac,ad      |
| **{n}**  | {n}前的一个字符连续出现n次        | /a{3}/相当于aaa            |
| {n,}     | {n,}前的一个字符连续出现n次或多次 | /a{3,}/可匹配aaa,aaaa,……   |
| {n,m}    | {n,m}前的一个字符连续出n次到m次   | /ba{1,3}/可匹配ba,baa,baaa |

| **符号** | **描述**                                           |
| -------- | -------------------------------------------------- |
| /…/      | 代表一个模式的开始和结束                           |
| **^**    | 匹配字符串的开始                                   |
| **$**    | 匹配字符串的结束                                   |
| \s       | 任何空白字符                                       |
| \S       | 任何非空白字符                                     |
| **\d**   | 匹配一个数字字符，等价于[0-9]                      |
| \D       | 除了数字之外的任何字符，等价于[^0-9]               |
| **\w**   | 匹配一个数字、下划线或字母字符，等价于[A-Za-z0-9_] |
| \W       | 任何非单字字符，等价于[^a-zA-z0-9_]                |
| **.**    | 除了换行符之外的任意字符                           |



# 四、BOM与DOM

了解:  
	API   
		Application Programming Interface 应用程序接口, 简称 接口  
		实现某种功能，开发人员无须访问源码，无须理解内部实现机制，只需要知道使用即可。  
		例如：打卡摄像头，打开相册	（juhe.cn）  

## DOM

Web API  

​	操作浏览器和网页的接口。  
​	DOM（Document Object Model）: 文档对象模型，操作网页元素。  
​	BOM: 浏览器对象模型，操作浏览器窗口。  
​	比如：console对象、document对象、window对象

DOM  

​	操作网页的接口。操作网页的元素。  
​	DOM（Document Object Model）: 文档对象模型，操作网页元素。  
​	获取网页元素、获取属性、操作样式等。比如调整div大小，切换标签，做交互效果。

DOM树  

将HTML文档看成树结构，称为文档树模型。  
	把文档映射成树结构，通过节点对象对其处理。  
	专有名词：  
		文档 (document)  
		元素 (element)  
		节点 (node): 网页中的所有内容，在DOM树中都是节点。（比如：元素节点、属性节点、文本节点、注释节点）  

**事件:**  

可以被js检测到的行为，是一种“触发-响应”机制。比如：页面加载，鼠标单击，悬浮，滑动等。  
	三要素：  
		事件源：触发事件的元素（谁触发了事件）  
		事件类型：比如click事件（触发了什么事件）  
			点击事件onclick  
			获取文本框焦点onfocus, 失去文本框焦点onblur  
			鼠标指针经过事件onmouseover, 鼠标指针离开事件onmouseout  
		事件处理程序：触发事件以后要执行的代码（触发事件以后要做什么）

掌握

### 获取元素的方式

​	通过ID获取元素：document.getElementById('id名')

```javascript
var box = document.getElementById('box')
console.log(cai)
```
根据标签获取元素: document.getElementsByTagName('标签名')
	因为相同的标签可以有多个，结果是集合，称为伪数组，可以用数组索引来访问元素。

```javascript
	var li = document.getElementsByTagName('li')
	//通过数组索引访问伪数组li
	console.log(li[0])
	console.log(li[2])
	//修改css样式
	li[0].style.color = 'red'
```
根据name获取元素： document.getElementsByName('name名')
	因为相同的name可以有多个，结果是集合，称为伪数组，可以用数组索引。

```javascript
	var fruit = document.getElementsByName('fruit')
	console.log(fruit)
	console.log(fruit[0])
	//将第一个元素的checked属性设置为true
	fruit[0].checked = 'true'
```

HTML5新增的获取方式:
	根据类名获取：getElementsByClassName('类名')
		document.getElementsByClassName('class名')
		因为相同的class可以有多个，结果是集合，称为伪数组，可以用数组索引。

```javascript
	var one = document.getElementsByClassName('one')
```
​	document.querySelector('css选择器')
​		返回指定css选择器的第一个元素
​	
​	document.querySelectorAll('css选择器')
​		返回指定css选择器的所有元素集合
​		结果是伪数组，通过数组索引来访问元素。

```javascript
	 document.querySelector('#box')
	 document.querySelector('li')
	 document.querySelector('.ci')
	document.querySelectorAll('.fa')
```

document对象的属性

```java
	document.title
	document.body
	document.documentElement
	document.forms
	document.images
```



### 操作元素的方式

#### 1 操作元素的内容

​	获取、修改元素内容  
​	获取内容  
​		element.innerHTML 		保留标签、空格、换行
​		element.innerText 		去掉标签、空格、换行
​		element.textContent 	去掉标签，保留空格、换行	
​	修改内容  
​		element.innerHTML 	= '内容'
​		element.innerText 	= '内容'
​		element.textContent = '内容'
​	

#### 2 操作元素的属性

获取、修改元素的属性  
	获取元素的属性
		element.属性名
	修改元素的属性
		element.属性名 = '属性值'

```javascript
	document.title = '懒猫'
	img.src = '2.jpg'
	img.title = '这是一只懒猫'
```

#### 3 操作元素的样式(CSS、style)

​	1 操作style属性
​		元素.style.样式名

```javascript
//隐藏元素 
document.querySelector('#middle').style.display = 'none'

var box = document.getElementById('box')
box.style.backgroundColor = 'red'
box.style.fontSize = '20px'
```

​	2 操作className属性
​		`元素.className =` 

了解  
排他思想：排除掉其他的(包括自己),然后给自己设置实现的效果.  
	事件类型（触发了什么事件）,  
		点击事件onclick  
		获取文本框焦点onfocus, 失去文本框焦点onblur  
		鼠标指针经过事件onmouseover, 鼠标指针离开事件onmouseout  
		事件：  
			click 点击事件  
			focus 获取文本框焦点
			blur	失去文本框焦点
			mouseover	鼠标指针经过事件
			mouseout 	鼠标指针离开事件

节点基础

​	什么是节点  
​	节点层级（节点之间的关系）  

- ​		根节点
- ​		父节点
- ​		子节点
- ​		兄弟节点

掌握  

元素的属性和dom节点操作

### 属性操作

#### 获取属性

​	任意属性通用(推荐)：element.getAttribute('属性')
​		内置属性： element.属性，比如id、style等

#### 设置属性

​	H5规定用 “data-属性名”的方式设置自定义属性名。
​		通用(推荐): element.setAttribute('属性名','属性值')
​			 element.dataset.属性名 = 属性值 （属性值会加上data-）
​		内置属性: element.属性名 = '属性值'

#### 移除属性

​	`element.removeAttribute('属性名')`

#### 自定义属性

data-属性名  
	设置： 

```javascript
element.setAttribute('data-属性','值')  
element.dataset.属性	= '值'  
```

​	获取：  

```javascript
element.getAttribute('data-属性')  
element.dataset.属性	= '值'
```

### DOM节点基础

​	什么是节点：
​		常见的节点类型：元素节点，属性节点，文本节点，注释节点等

节点层级：节点之间的层级关系
	根节点、父节点、子节点、兄弟节点

#### 获取父节点

​	`element.parentNode` 

#### 获取子节点

​	推荐使用： `element.children` 
​		结果是伪数组，通过索引访问  

​	获取子元素的节点： element.children[索引]  
​		获取子元素的第一个节点：element.children[0]  
​		获取子元素的最后一个节点：`element.children[element.length-1]` 
​		获取第一个子元素  
​			`element.children[0]` 
​		获取最后一个子元素  
​			`element.children[element.children.length - 1]`

#### 获取兄弟节点

获取兄弟元素   
	下一个兄弟元素 
`element.nextElementSibling` 
	上一个兄弟元素 
`element.previousElementSibling`  

事件的绑定和事件对象的使用    

常用的鼠标事件、键盘事件    

获取/编辑输入框内容
	`element.value`

#### 获取/编辑元素内容

​	`element.innerHTML` 

节点操作  

#### 创建节点

（创建元素节点）  
	`document.createElement('tagName')` 
动态创建节点：

```javascript
document.write()
element.innerHTML = ''
document.createElement('tagName')
```

#### 添加子节点

```javascript
element.appendChild(child)   	//在最后一个子节点后面添加子节点  
element.insertBefore(子节点, 指定节点)		//在指定元素之前添加子元素节点	
```

#### 删除节点

```javascript
element.removeChild(child)  //删除子节点
//删除node: node.parentNode.removeChild(node)
```

#### 复制节点

​	`element.cloneNode(true/false)`  

### 事件进阶

事件的绑定和事件对象的使用  
注册事件（绑定事件）  
	传统方式：on+事件类型，比如onclick、onmouseover等  
		特点：同一个元素同一个事件只能设置一个处理函数（如果有多个，后一个覆盖前一个）  
	事件监听：addEventListener ('事件类型',执行函数)  
		element.addEventListener(type,callback), type参数：事件类型，callback:处理函数  
		同一个元素，同一个事件可以监听多次  

删除事件  
	传统方式：on事件类型 = null  
	事件监听：element.removeEventListener(type,callback)  
	element.onclick = null  
	elemnt.removeEventListener ('事件类型',执行函数)  

DOM事件流  
	事件捕获：从父到子（从外向内）  
	事件冒泡：从子到父（从内向外）  

事件对象  
	什么是事件对象：与触发事件相关的所有信息  
		参数event就是事件对象  
		element.事件 = function(event){}  

e.target  触发事件的对象  
this		绑定事件的对象

![image-20241215212526454](http://img.an520.com/test/image-20241215212526454.png)

阻止事件冒泡：e.stopPropagation()

阻止默认行为：e.preventDefault()

事件委托：把事件绑定在父节点，不给每个子节点单独设置
	不给子元素注册事件，给父元素注册事件。

```javascript
element.value //获取文本框的内容

element.innerHTML //获取元素的内容
```

常用的**鼠标事件**

```javascript
onclick	//点击事件
onfocus	获取焦点	onblur 失去焦点
onmouseover 鼠标经过  onmouseout鼠标离开
onmousemove  //鼠标指针移动
```

鼠标事件对象：跟鼠标事件相关的所有信息

常用的**键盘事件**
	keypress	按键按下触发(不识别功能键)
	keydown  按键按下触发
	keyup	 按键松开触发
（执行顺序 keydown -> keypress -> keyup）

```javascript
	document.addEventListener('keydown', function(event) {
		console.log('您已按下键盘'); 
		console.log(event.keyCode)
	})
```
keyCode（keypress）
	区分大写状态（65~90）和小写状态（97~122）
keyCode（keydown）
	字母键都以大写状态显示键值（65~90）
keyCode（keyup）
	字母键都以大写状态显示键值（65~90）	

键盘事件对象：跟键盘事件相关的所有信息
	keyBoardEvent

onchange 当对象或选中区的内容改变时触发。

selectedIndex 属性设置或返回下拉列表中被选定的选项的索引（下标）。
索引从 0 开始。

**常用事件**

| **事件名称**    | **事件触发时机**                       |
| --------------- | -------------------------------------- |
| **onclick**     | 单击鼠标左键时触发                     |
| **onfocus**     | 获得焦点时触发                         |
| **onblur**      | 失去焦点时触发                         |
| **onmousedown** | 按下任意鼠标按键时触发                 |
| **onmousemove** | 在元素内当鼠标移动时触发               |
| **onmouseout**  | 鼠标离开时触发                         |
| **onmouseover** | 鼠标经过时触发                         |
| **onkeydown**   | 某个键盘按键被按下时触发               |
| **onkeypress**  | 某个键盘按键被按下时触发，不识别功能键 |
| **onkeyup**     | 某个键盘按键被松开时触发               |
| **onload**      | 页面加载时触发                         |
| **onchange**    | 域（元素）的内容被改变时触发           |
| **onselect**    | 文本被选中时触发                       |
| **onsubmit**    | 表单提交时触发                         |

**事件对象**

| **事件对象属性和方法**  | **说明**                                   |
| ----------------------- | ------------------------------------------ |
| **e.target**            | 返回触发事件对象  标准浏览器               |
| **e.srcElement**        | 返回触发事件对象  IE6-IE8浏览器            |
| **e.type**              | 返回事件类型  如click mouseover 不带on     |
| **e.keyCode**           | 返回键码                                   |
| **e.stopPropagation()** | 阻止事件冒泡  标准浏览器                   |
| **e.cancleBubble**      | 阻止事件冒泡 IE6-IE8浏览器                 |
| **e.preventDefault()**  | 阻止默认行为  标准浏览器 例如阻止链接跳转  |
| **e.pageX**             | 鼠标位于文档的水平坐标                     |
| **e.pageY**             | 鼠标位于文档的垂直坐标                     |
| **e.clientX**           | 鼠标位于浏览器页面当前窗口可视区的水平坐标 |
| **e.clientY**           | 鼠标位于浏览器页面当前窗口可视区的垂直坐标 |

了解

## BOM

​	Brower Object Model 浏览器对象模型
​	与浏览器进行交互的对象
​	核心对象（顶级对象）是window
​		document、location、navigator、history对象等

### window对象

window的常见属性
	innerheight	返回窗口的文档显示区的高度
	innerwidth	返回窗口的文档显示区的宽度
	opener	返回打开当前窗口的父窗口对象，是一个window对象
	parent	返回父窗口对象，是一个window对象
	self	返回当前窗口对象，是一个window对象

掌握
window对象的常见事件
	窗口加载事件:load
		window.onload 整个页面加载时触发

调整窗口大小事件:resize
	window.onresize 调整窗口大小时触发

window的常用方法
打开新窗口 window.open()
	window.open(URL,[name],[features],[replace])
		参数说明：
		URL：打开指定页面的URL地址，若没有指定，则打开一个新的空白窗口。
		name：窗口名称。指定target属性或窗口的名称。
			_blank	URL加载到一个新的窗口，也是默认值
			_parent	URL加载到父框架
			_self	URL替换当前页面
			_top	URL替换任何可加载的框架集
			name	窗口名称
		features：用于设置浏览器窗口的特征（如大小、位置、滚动条等），多个特征之间使用逗号分隔。
			width：窗口的宽度，最小值为100
			height：窗口的高度，最小值为100
			top：窗口距离屏幕顶部的距离，默认0；
			left：窗口距离屏幕左侧的距离，默认0；
			menubar：是否显示菜单栏，yes\no；
			toolbar：是否显示工具栏，yes\no；
			location：是否显示地址栏，yes\no；
			status：是否显示状态栏，yes\no；
			resizable：是否允许用户调整窗口大小，yes\no；
			scrollbars：是否显示滚动条，yes\no。
			要启用该特性，将其设置为 yes|1 ，反之为 no|0。
		replace：设置为true，表示替换浏览历史中的当前条目，设置false（默认值），表示在浏览历史中创建新的条目
			
...
//打开http://www.imooc.com网站，大小为300px * 200px，无菜单，无工具栏，无状态栏，有滚动条窗口：

window.open('http://www.imooc.com','_blank','width=300,height=200,menubar=no,toolbar=no, status=no,scrollbars=yes')
...

关闭窗口 window.close()

模态对话框
	alert()：弹出警告框。
	confirm()：弹出确认框。
	prompt()：弹出提示输入框。

两组定时器的使用
	设置定时器

```javascript
setTimeout(函数,毫秒)	//在指定的毫秒后调用函数，只执行一次
setInterval(函数,毫秒)	//在指定的周期调用函数，可以执行无数次
```

清除定时器

```javascript
clearTimeout(定时器ID)
clearInterval(定时器ID)
```

JavaScript执行机制
	单线程：JS的特点、同一时间只能做一件事。
	
同步和异步：
	同步：前一个任务结束后再执行后一个任务。
	异步：做一件事的同时，可以做其他事情。
		同步做饭： 烧水煮饭，等水开了，再去切菜、炒菜
		异步做饭： 烧水煮饭的同时去切菜炒菜。	
		比如click、setTimeout、setInterval等
了解：进程、线程、协程、纤程、同步和异步 

### Location对象

​	URL的组成：
​		http://10.24.0.2:80
​		https://www.baidu.com:443
​		https://www.bilibili.com/v/douga/?spm_id_from=333.1007.0.0	
​	常用属性：
​		search  返回查询部分（？之后的）
​		host 返回主机加端口
​		hostname 返回URL的主机名
​		href 	返回完整的URL
​		pathname	返回URL的路径名
​		port	返回一个URL服务器使用的端口号
​		hash	返回一个URL的锚部分
​		protocol	返回一个URL协议

常用的方法：
		assign() 	载入一个新的文档
		reload()	重新加载当前文档(刷新)
		replace()	用新的文档替换当前文档

navigator对象
	常用属性：appCodeName appName appVersion platform
	常用方法：javaEnabled()

### history对象

​	常用属性：length	返回历史列表中的网址数  
​	常用方法：  
​		back() 回退  
​		forward() 前进  
​		go()	加载history列表中的某个具体页面  

### webStorage

webstorage 是 HTML5新增的存储数据的方案，比使用 cookie 更加直观。  

如果是会话存储，则使用sessionStorage，如果是本地存储(硬盘)，则使用localStorage。  

#### sessionStorage
用于**临时保存**同一窗口(或标签页)的数据**（key/value）**，在关闭窗口或标签页之后将会删除这些数据。      

sessionStorage的特点：  
	**只在本地存储**：只会在本地生效，并在关闭标签页后清除数据。  
	**存储方式**：seesionStorage的存储方式采用**key、value**的方式。**value的值必须为字符串类型**。  
	**存储上限**限制：大多数浏览器把上限限制在5MB以下。  

sessionStorage常用方法  

```javascript
sessionStorage.setItem('key','value')	保存或设置数据到sessionStorage  
sessionStorage.getItem('key')	获取某个sessionStorage  
sessionStorage.removeItem('key')	从sessionStorage删除某个保存的数据  
sessionStorage.clear()	从sessionStorage删除所有保存的数据  
```

#### localStorage

​	本地存储，解决了cookie存储空间不足的问题，一般浏览器支持的是5M大小。  
localStorage的特点：  
​	localStorage和sessionStorage一样**都是存储在客户端、且同源的**   
​	**只能存储字符串类型**的对象；  
​	**localStorage生命周期是永久。即使你是将浏览器关闭了，数据也不会消失**。除非用户主动清除localStorage信息。  

localStorage常用方法  

```javascript
localStorage.setItem('key','value')	保存或设置数据到localStorage  
sessionStorage.getItem('key')	获取某个localStorage  
localStorage.removeItem('key')	从localStorage删除某个保存的数据  
localStorage.clear()	从localStorage删除所有保存的数据
```

### localStorage、sessionStorage、Cookie 对比

三者均是浏览器端的**客户端存储方案**，核心用于保存少量键值对数据，但在存储容量、生命周期、作用域、与服务器交互等核心特性上差异显著，下面通过表格和关键说明清晰对比，帮你快速选型：

| **特性**         | **localStorage**                               | **sessionStorage**                        | **Cookie**                                                   |
| ---------------- | ---------------------------------------------- | ----------------------------------------- | ------------------------------------------------------------ |
| **存储容量**     | 较大（通常 **5MB - 10MB**）                    | 较大（通常 **5MB - 10MB**）               | 极小（通常 **4KB**）                                         |
| **持久性**       | **永久**（永不过期）                           | **会话级**（关闭浏览器窗口/标签页即清除） | 可设置**过期时间**（若未设置，则会话结束清除）               |
| **共享范围**     | 同源的所有窗口/标签页**共享**                  | **仅限创建它的当前窗口/标签页**           | 同源的所有窗口/标签页**共享**                                |
| **与服务器通信** | **不会**自动发送到服务器                       | **不会**自动发送到服务器                  | **每次** HTTP 请求都会**自动携带**                           |
| **作用目的**     | 永久保存用户数据（如主题、离线数据、上次状态） | 临时保存会话数据（如购物车、表单进度）    | 用于身份验证和状态跟踪（如 Session ID）                      |
| **访问方式**     | 仅通过 **JavaScript** API 访问                 | 仅通过 **JavaScript** API 访问            | 默认可通过 **JavaScript**（除非设置 `HttpOnly`）和 **服务器** 访问 |
| **操作方式**     | `localStorage.setItem()`                       | `sessionStorage.setItem()`                | 需通过 `document.cookie` 或**服务器端响应头**操作            |

# 五、JS网页特效

了解  
	网页特效的概念  
	
掌握  

## 偏移量offset

​	offsetLeft 	相对有定位的父元素左边框的偏移（如果没有，则相对body）  
​	offsetTop 	相对有定位的父元素上方的偏移（如果没有，则相对body）  
​	offsetWidth  自身的宽度（包含padding、border、内容）  
​	offsetHeight	自身的高度（包含padding、border、内容）  
​	offsetParent 	返回带有定位的父元素（如果没有，则返回body）  

元素偏移量offset
	// 打印盒子的宽度和高度(包含边框、padding、内容)
		offsetWidth //盒子宽度  
		offsetHeight //盒子高度  
	//相对有定位父元素左边框的偏移（如果没有定位，则返回Body）  
		offsetLeft  
	//相对有定位父元素上方的偏移（如果没有定位，则返回Body）  
		offsetTop  
	

offset和style的区别    

## 可视区client

​	clientLeft  	左边框大小  
​	clientTop 	 	上边框大小  
​	clientWidth 	自身内容的宽度/可视的宽度（包含padding，不包含border）  
​	clientHeight 	自身内容的高度/可视的高度（包含padding，不包含border）  

## 滚动scroll  

​	scrollLeft 被卷去的左侧距离，不带单位  
​	scrollTop  被卷去的上方距离，不带单位  
​	scrollWidth	自身的宽度(不包含border)，不带单位  
​	scrollHeight 自身的高度(不包含border)，不带单位    

# 六、ES6新特性

‌ES6（ECMAScript 6）是JavaScript语言的标准，于2015年6月正式发布，也被称为ECMAScript 2015（ES2015）。ES6引入了许多新的语法特性，旨在改进和扩展JavaScript的功能，使得JavaScript更加现代化、易读、易维护，更适合构建复杂的应用程序，特别是针对大规模的企业级开发‌‌

## **let**命令

声明变量，用法类似于var，但是只在代码块内有效(**块级作用域**)

```javascript
{
    let a = 10;
    var b = 1;
}
a // ReferenceError: a is not defined.
b // 1
```

## **const**命令

const用于声明一个**只读的常量**。一旦声明，常量的值就不能改变。

```javascript
const PI = 3.1415;
PI // 3.1415
PI = 3; // 修改值报TypeError: Assignment to constant variable.的错误
```

## **字符串的扩展**

模板字符串（template string）是增强版的字符串，用反引号（`）标识。它可以当作普通字符串使用，也可以用来定义多行字符串，或者在字符串中嵌入变量。

```javascript
let myName = `雪儿`//使用反引号
let age = 18
let str = `${myName}年龄是${age}`  //雪儿年龄是18
```

## **对象的扩展**

•简写的属性初始化

```javascript
const age = 12; 
const name = "Amy"; 
const person = {age, name}; 
person //{age: 12, name: "Amy"}

//等同于 
const person = {age: age, name: name}
```

•简写的方法声明

```javascript
const person = {
  sayHi(){
    console.log("Hi");
  }
}
person.sayHi();  //"Hi"

//等同于
const person = {
  sayHi:function(){
    console.log("Hi");
  }
}
person.sayHi();//"Hi"
```

## 箭头函数

ES6的箭头函数提供了一种更加简洁的函数书写方式

**语法**：参数 **=>** 函数体

```javascript
var fn1 = (a, b) => {
	return a + b
}
```

当函数参数只有一个，括号可以省略；但是没有参数时，括号不可以省略

| 传统定义                               | 箭头函数                          | 描述         |
| -------------------------------------- | --------------------------------- | ------------ |
| var  fn1 = function() {}               | var fn1 = () => {}                | **无参**     |
| var  fn2 = function(a) {}              | var fn2 = a => {}                 | **单个参数** |
| var  fn3 = function(a, b) {}           | var  fn3 = (a, b) => {}           | **多个参数** |
| var  fn4 = function(a, b, ...args)  {} | var  fn4 = (a, b, ...args)  => {} | **可变参数** |

箭头函数相当于匿名函数，并且简化了函数定义。

## js面向对象

了解什么是面向对象编程  
	面向对象的特征：	  
		封装性、多态性、继承性  

掌握类与对象的关系  
  类：抽象的事物    

  对象：具体的事物    

掌握类的继承以及super关键字的使用  

掌握使用class创建类的方法  

### 类基本语法

类实质上就是一个函数，类自身指向的就是构造函数

```javascript
//代码定义了一个‘类’，constructor是构造方法，而this关键字则代表实例对象。
class Point {
    constructor(x, y) {
        this.x = x;
        this.y = y;
        console.log(x, y);
    }
    
    toString() {
    	return '(' + this.x + ', ' + this.y + ')';
    }
}
```

```javascript
//生成类的实例对象
var point = new Point(2, 3);
console.log(point.toString()); // (2, 3)
```

### Class 的继承

可以用extends关键字实现继承。子类继承父类，继承了父类所有的属性和方法。

`super`关键字主要用于在子类中调用父类的构造函数和方法，实现继承和代码复用。

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }
  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name); // 调用父类的构造函数
    this.breed = breed; // 初始化子类的属性
  }
  speak() {
    super.speak(); // 调用父类的方法
    console.log(`${this.name} is a ${this.breed}.`); // 添加额外的功能
  }
}
```

### Class 静态方法

类（class）通过 static 关键字定义静态方法,

静态方法是一种不需要创建对象就能直接调用的方法

```javascript
class Foo {
    static classMethod() {
    	return 'hello';
    }
}

//正常运行
Foo.classMethod() // 'hello'

var foo = new Foo();
```

## 解构赋值

数组的解构赋值

```javascript
//解构赋值 
let [a, b, c] = [1, 2, 3];
```

对象的解构赋值

```javascript
const {name, age} = {name: 'John', age: 20};
```

## 数组的扩展

### 新增的数组方法：数组创建

Array.from：用于将两类对象转为真正的数组    

​	（将伪数组对象或可遍历对象转换为真数组）

```javascript
let arrayLike = {
    '0': 'a',
    '1': 'b',
    '2': 'c',
    length: 3
};
// ES6的写法
let arr2 = Array.from(arrayLike); // ['a', 'b', 'c']
```

Array.of：用于将一组值，转换为数组。

```javascript
Array.of(3, 11, 8) // [3,11,8]
Array.of(3) // [3]
Array.of(3).length // 1
```

### 新增的数组方法：数据筛选

**find(回调函数)**方法：找出**第一个符合条件的成员**。   
findIndex(回调函数)方法：用法和find()类似。返回符合条件成员的位置(从0开始)。若找不到返回-1  
**filter(回调函数)**方法：返回符合条件的**全部成员**(作为新数组返回)  
some(回调函数)方法：判断数组中是否有满足条件的元素。返回true或者false

```javascript
var nums=[2, 6, 22, 55]

nums.find(function(v,index,arr) {
    return v>9
})

nums.filter(function(v) {
    return v>9
})
//回调函数参数：参数名可自定义
//v：当前遍历元素的值
//index：当前遍历元素的位置，此处未使用，可省略
//arr：原数组，此处可省略
//回调函数体：判断是否满足条件，根据判断结果返回true或false
// 此处的回调函数通常可简写为箭头函数
```

### 新增的数组方法：数据填充

fill()方法使用给定值,填充一个数组。用于空数组的初始化。    

基本语法 `arr.fill(value, start?, end?)`

```javascript
// 快速创建长度为5、全为1的数组
const arr2 = new Array(5).fill(1);
console.log(arr2); // 输出 [1, 1, 1, 1, 1]

const arr5 = [1, 2, 3, 4, 5];
arr5.fill(7, 1, 4); // 填充索引1~3（不包含4）
console.log(arr5); // 输出 [1, 7, 7, 7, 5]
```

### 新增的数组方法：数据遍历

ES6 提供三个新的方法——entries()，keys()和values()——用于遍历数组。    

它们都返回一个遍历器对象，可以用for...of循环进行遍历，唯一的区别是keys()是对键名的遍历、values()是对键值的遍历，entries()是对键值对的遍历。

```javascript
let arr = ['小红', '小明', '小芳']
for (let index of arr.keys() ) {
	console.log('index: ', index)
}
/**结果：
    * index:  0
    * index:  1
    * index:  2
*/

for (let value of arr.values() ) {
  console.log('value: ', value)
}
   /**结果：
    * value:  小红
    * value:  小明
    * value:  小芳
    */

for(let [index,value] of arr.entries()){
 console.log(index + ":" + value)
}
  /**结果：
    * 0:小红
    * 1:小明
    * 2:小芳
   */
```

### includes

includes方法返回一个布尔值，表示某个数组是否包含给定的值，与字符串的includes方法类似。

语法：includes(值, 搜索起始位置)。搜索起始位置默认为0，

```javascript
[1, 2, 3].includes(4)
[1, 2, 3].includes(3, 2);  // true
[1, 2, 3].includes(3, 3);  // false
[1, 2, 3].includes(3, -1); // true
```

### flat

flat()用于将嵌套的数组“拉平”，**下降一个维度**。该方法返回一个新数组，对原数据没有影响。

```javascript
[1, 2, [3, [4, 5]]].flat()
// [1, 2, 3, [4, 5]]
[1, 2, [3, [4, 5]]].flat().flat()
//[1,2,3,4,5]
```

## Set数据结构

类似于数组，但是成员的值都是唯一的，没有重复的值。  

通过new Set()可以创建Set，然后通过add方法能够向Set中添加数据项。。

```javascript
const s = new Set();

[2, 3, 5, 4, 5, 2, 2].forEach(x => s.add(x));

for (let i of s) {
  console.log(i);
}     
// 2 3 5 4

const items = new Set([1, 2, 3, 4, 5, 5, 5, 5]);
items.size // 5
```

**Set****结构中常用方法**

| **方法名**          | **描述**                             |
| ------------------- | ------------------------------------ |
| **size**            | 返回Set实例的成员总数                |
| **add(value)**      | 添加值，返回 Set 结构本身            |
| **delete(value)**   | 删除值，返回布尔值，表示删除是否成功 |
| **has(value)**      | 返回布尔值，表示该值是否为Set的成员  |
| **clear()**         | 清除所有成员，没有返回值             |
| **keys()/values()** | 返回键名/键值的遍历器(无差别)        |
| **entries()**       | 返回键值对的遍历器                   |
| **forEach()**       | 使用回调函数遍历每个成员             |

## Map数据结构

Map是一种键值对的对象。相比较对象来说，它的键可以是各种类型的，如果需要在一个地方使用键值对的数据结构，Map比起Object会更合适。

```javascript
const map1 = new Map();

map1.set('a', 1);
map1.set('b', 2);
map1.set('c', 3);
// map取值
console.log(map1.get('a')); // 1
// 可以覆盖
map1.set('a', 97);
console.log(map1.get('a')); // 97
// 类似 数组的 length
console.log(map1.size); // 3
// map 删除
map1.delete('b');
console.log(map1.size); // 2
```

**Map** **结构** **中常用方法**

| **方法**             | **描述**                                             |
| -------------------- | ---------------------------------------------------- |
| **size**             | 返回 Map 结构的成员总数                              |
| **set(key,  value)** | 设置key对应的值为value,返回整个结构,可以使用链式写法 |
| **get(key)**         | 读取key对应的值，找不到则返回undefined               |
| **has(key)**         | 返回布尔值，表示键是否在  Map 对象中                 |
| **delete(key)**      | 返回布尔值，表示键是否删除成功                       |
| **clear()**          | 清除所有成员，没有返回值                             |
| **keys()**           | 返回键名的遍历器                                     |
| **values()**         | 返回键值的遍历器                                     |
| **entries()**        | 返回所有成员的遍历器                                 |
| **forEach()**        | 遍历 Map 的所有成员                                  |