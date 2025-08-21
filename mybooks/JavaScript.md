初识JavaScript 
	1 什么是JavaScript
		编程语言，一般用于开发交互式页面。
		作用：表单动态校验、网页特效、服务端开发(Node.js)、桌面程序(Electron)、App(Cordova)、控制硬件-物联网(Ruff)、游戏开发(cocos2d-js)、动画（animate.js）、数据库(MongoDb)。功能强大,前端开发(web、APP、小程序、后台管理系统)
		

		网页组成：
			HTML
			CSS
			JavaScript 
		
		JS内嵌在网页中，通过浏览器内置的JS引擎解释并执行（主要运行在浏览器中）
		
		浏览器分类：
		浏览器内核：
			渲染引擎（排版引擎）：解析HTML与CSS，比如Chrome浏览器的Blink
			JS引擎：是JavaScript的解释器。比如Chrome浏览器的V8引擎。
			
		JS代码的执行特点：逐行执行
		
		常用的JS框架： React.js  Angular.js  Vue.js(尤雨溪) 
		
		JS的特点：
			解释性语言（脚本语言不需要编译，比如JavaScript、 Python、 PHP） 编译语言(JAVA、 C++、Go)
			跨平台（不依赖操作系统，只需要浏览器的支持）
			支持面向对象（C语言不支持面向对象）
			弱类型：
				var name;//弱类型
				var string name;//强类型
			
		JS的组成：
			ECMAScript：基本语法，是JS的核心。
			DOM：文档对象模型。操作页面的元素。
			BOM：浏览器对象模型。操作浏览器窗口。
		
	常用开发工具
		VS code、 Hbuilder、 Sublime text、 DreamWeaver、 WebStorm等
	
		vs code下载安装：
			官网 https://code.visualstudio.com/
			安装插件：
				chinese, open in browser


​	
​	JS代码的3种书写位置
​		行内式：写HTML标签事件中（onclick oninput onmousemove）

```
	<input onmousemove="console.log('这是鼠标抚摸事件！')" oninput="alert('你的输入错误！')" type="text" />用户名
	<br />
	<input onclick="alert('你提交成功！！')" type="submit" />
```

		内嵌式（嵌入式）：将JS代码写在<script>标签中,<script>放在<head>或者<body>里面

```
	<script>
		var age = prompt('请你输入年龄！')
		
		if(age>50) {
			alert('老男人')
		}else if(age >20 ) {
			alert('年轻人')
		}else{
			alert('小学生')
		}
	</script>
```

		外部式(外链式):将JS代码写在单独的文件中,扩展名".js"。通过script标签引入

```
	<script src="js/test.js"> </script>
```

		语法规则：
			js严格区分大小写
			对空格、换行、缩进（tab）不敏感
			每行的英文分号";"可以省略,推荐加上
		
		注释：
			单行注释：//   	快捷键：ctrl+/
			多行注释：/* */ 	快捷键：ctrl+shift+/
		
		输入输出语句：
			alert('自定义信息')  弹出警告框
			console.log('自定义信息') 控制台输出信息
			prompt('自定义信息') 弹出输入框
		
		控制台的使用：F12 - console/控制台
		
		变量：是内存中的一块空间。
			声明: var age;
			赋值: age = 18;
			
			声明同时赋值:
				var age = 18;
		
		变量命名规范：
			1 由字母 数字 下划线 美元符号$组成。（中文也可以，不推荐）
			2 严格区分大小写。
			3 不能以数字开头
			4 不能是关键字，保留字。
				关键字比如 break if console
					就是在js中已经被使用了的单词。js本身已经赋予其功能
				保留字
					在未来js标准中可能被用来作为关键字的单词
			5 合理命名，“见其名知其意”
			6 三种命名法：
				1 小驼峰命名法

```
var mySchoolAddress = '重庆涪陵';
```

				2 大驼峰命名法

```
var MySchoolAddress = '重庆涪陵';
```

				3 下划线命名法

```
var my_school_address = '重庆涪陵';
```

	3 JavaScript入门
	4 JavaScript变量
	
JS基础（上）
	1 数据类型
		弱类型：不用提前声明数据类型； JS  php 
```
	var name;
	var age ;
```
		强类型：Python JAVA C C++ GO 
```
	var name String;
	var age Int;
```
		分类：
			基本数据类型（5种）：
				Number 数字型
```
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
					NaN 非数值
					isNaN 判断非数值，true非数字，false数字
					
				String 字符类型
					用单引号''或者双引号""来包裹
						单引号里面可以加双引号，但是不能加单引号（要转义）
						双引号里面可以加单引号，但是不能加双引号（要转义）
```
		var str1 = '这是一个字符串';
		var str2 = "这也是一个字符串";
```
					转义符号：\'  \"   换行\n  \\  。。。
					字符串长度：length属性 
```
	var str2 = '这是一个字符串';
	var index = str2.length - 1;
	alert(str2[index])
```
				Boolean 布尔型 ：true 和false 
					
				null   空型
```
	var a = null;
	//判断是否null
	if (a === null) {
		alert('这是null型')
	}
```
				undefined 未定义型
```
	var test;
	alert(test)
```
			复杂数据类型（引用数据类型）：Object(对象)
			
			检测数据类型: typeof 
	2 数据类型转换
	3 运算符


转布尔类型: Boolean()
	没有意义的值会转为false，比如0 '' null undefined NaN

运算符:
	算术运算符：+ - * /  %(取模，取余数)
	
	递增递减（自增自减）运算符：++ 、--
		i++ 等同于 i = i + 1，变量+1
		i-- 等同于 i = i  1，变量-1
		
		i++和++i的区别：
				i++返回计算前的结果
				++i返回计算后的结果
				
	比较运算符：结果是布尔值，true或者false
		常见的： >  < >= <=  ==等于  !=不等于  ===全等 !==不全等
```
	console.log('' == 0);
	console.log('' === 0);
```
	
	逻辑运算符： 返回布尔值，，true或者false
		&&，与，a&&b，a和b都是true，结果才是true
		||，或，a||b，a或者b有一个是true，结果就是true
		!，非， !a，a是false，结果就是true
	
	位运算符：
	
	赋值运算符：将运算符右边的值赋给左边的变量
		= 
		+= 
			x += y; 等同于 x = x +y
		-=  
			x -= y; 等同于 x = x - y
		*=
		/=
		%=
	
	三元运算符： 条件表达式 ? 表达式1 : 表达式2
	
	运算符优先级：
	
流程控制：
	顺序结构：默认，逐行执行
	
	分支结构：根据条件控制
		单分支：
			if(条件表达式){
				//代码段
			}
```
	if ( true ) {
		alert('吃火锅')
	}
```
		双分支：
			if(条件表达式){
				//代码段1
			} else {
				//代码段2
			}
```
	var a = prompt("你喜欢我吗？yes or no ?")
	if ( a == 'yes' ) {
		alert('我也喜欢你！')
	}else {
		alert('你是好人！')
	}
```
		多分支：多个条件表达式
			if(条件表达式1){
				//代码段1
			} else if(条件表达式2) {
				//代码段2
			}else if(条件表达式3) {
				//代码段3
			}else{
				//代码段x
			}
		
		switch语句：也是多分支，只有一个表达式（break不能少）
			switch(条件表达式) {
				case 值1:
				代码段1;
				break;
				case 值2:
				代码段2;
				break;
				default:
				代码段n;
			}
		
		
	循环结构：重复执行
		for循环:
```
	for(初始化变量; 条件表达式（循环条件）; 操作表达式（每次循环后的操作） ){
		//循环体
	}
```  
		断点调试：
	
	数组：
	
	
	循环结构：重复执行
		for循环:
```
	for(初始化变量; 条件表达式（循环条件）; 操作表达式（每次循环后的操作） ){
		//循环体
	}
```  
		while循环：先判断条件再执行。for循环可以改成while循环
```
	while(条件表达式){
		//循环体
	}
```
		do...while循环：无条件执行一次循环体，再判断条件
		断点调试：
		
		continue(继续):跳出本次循环,直接下一次循环
			如果是多层循环，只能跳过最近的循环体。如果要跳过外层循环，需要加标签：continue 标签名；
			
		break(打断)：跳出整个循环，结束循环。
			如果是多层循环，打断最近的循环体。如果要打断外层循环，需要加标签：break 标签名；
	

数据结构：			
	数组Array：
		创建数组：[] 或者 new Array()
		访问数组元素： 数字索引,从0开始
		数组长度：.length
		数组遍历：将数组元素全部访问一遍	
			for循环
		修改数组长度：star.length = 长度数字
		新增或者修改数组元素：通过索引
		二维数组：

函数(function 方法)

函数的使用
	声明函数:
		function 函数名(){
			//代码
		}
	调用函数:
		函数名()
```
	function sayHi(){
		console.log('hi')
	}

	sayHi()
```
	
什么是函数：代码复用

函数参数：
	形参：函数声明时的参数
		function 函数名(参数1，参数2。。。){
			//代码
		}
	实参：函数调用时的参数
		函数名(参数1,参数2...)

函数参数的数量：		
	形参个数小于实参：undefined
	形参个数大于实参：忽略

返回值：推荐必须加上返回值，终止并且返回
	function 函数名(参数1，参数2。。。){
		//代码
		return 返回值;//终止并且返回
	}

return 可以终止函数

arguments :接收所有的实参,arguments是一个对象


函数进阶：
	匿名函数：
		
	函数表达式：将声明的匿名函数赋值给一个变量，通过变量调用函数。
		必须写在调用前。
		var 变量名 = function(参数1，参数2。。。){
			//代码
			return 返回值;//终止并且返回
		}
		变量名() //调用
```
	var sayHi = function(){
		console.log('hello world')
	}
	sayHi()
```
	
	回调函数： 将函数作为参数传递给另外一个函数
```
	//参数fn是一个匿名函数, 叫做回调函数
	function cal(num1, num2, fn) {
		return fn(num1, num2)
	}
```
	递归调用：函数自己调用自己
	

函数进阶：
	匿名函数：
```
		//调用匿名函数
		(function(参数1，参数2。。。){
			//代码
			return 返回值;//终止并且返回
		})()
```	
	函数表达式：将声明的匿名函数赋值给一个变量，通过变量调用函数。
		必须写在调用前。
		var 变量名 = function(参数1，参数2。。。){
			//代码
			return 返回值;//终止并且返回
		}
		变量名() //调用
```
	var sayHi = function(){
		console.log('hello world')
	}
	sayHi()
```
	
	回调函数： 将函数作为参数传递给另外一个函数
```
	//参数fn是一个匿名函数, 叫做回调函数
	function cal(num1, num2, fn) {
		return fn(num1, num2)
	}
```

	递归调用：函数自己调用自己
	
	作用域：
		全局变量：不在函数内声明的变量，或者函数内省略var声明的变量
			在浏览器页面关闭的时候，才会销毁，比较占用内存
		局部变量：函数内用var声明的变量
			在函数执行完就会销毁，比较节省内存
			只能在当前函数内使用。不能在函数外面使用。
		块级变量：通过let声明
		
	作用域链：由内向外查找变量
		首先在当前函数内查找，如果找不到，则向上一级函数继续查找，直到全局变量（全局作用域）。
		
	闭包函数：有权访问另一函数作用域内变量(局部变量)的函数
		1 函数外部读取函数内部的变量
		2 让变量常驻内存


对象（object）：万物皆对象、面向对象编程OOP
	对象是一种数据类型，由属性和方法组成。
	属性：事物的特征，通过"对象.属性"访问
	方法：事物的行为，通过"对象.方法名()"访问

创建对象：

利用字面量创建对象：
	1 用大括号"{}"包裹
	2 每个成员用 键值对"key:value"保存，key表示属性名或者方法名，value表示对应的值
	3 每个成员之间用逗号,隔开

	访问对象的属性：对象.属性名 或者 对象['属性名']
	
	访问对象的方法：对象.方法名() 或者 对象['方法名']()

	当对象成员包含特殊字符，可以用字符串表示。
	
	this关键字：代表当前对象
	
	手动赋值属性或者方法

用new Object创建对象：
```
	var car = new Object();
```

用构造函数(模板)创建对象：
	//构造函数名首字母一般大写
	function 构造函数名(){
		this.属性名 = 属性;
		this.方法名 = function(){
			//方法体
		}
	}
	
	//使用构造函数创建对象
	var obj = new 构造函数名();
	
	静态成员：不需要创建实例对象就能使用。
		静态属性
		静态方法
	
	遍历对象的属性和方法： for...in
		使用in判断对象中某个成员是否存在.
```
	for (var k in shuaige) {
		console.log(k)	//k是属性名或者方法名
		console.log(shuaige[k])
	} 
```

		

内置对象：（不用编写，直接使用的对象）
	通过查阅文档熟悉内置对象: mdn
	Math对象：数学相关的运算, 不需要实例化,不是构造函数
```
	//获取基数的指数次幂
	console.log( Math.pow(10,2) )  //10的平方
	//开根号
	console.log(Math.sqrt(9)) 
```
	生成指定范围的随机数: Math.random()
```
	//min-max 之间的随机整数
	Math.floor(Math.random() * (max - min + 1) + min)
```


日期对象：需要实例化 new Date()
	日期对象的使用
	
	时间戳：当前时间，单位毫秒，1970-01-01 00:00:00到当前时间的毫秒数
		1秒= 1000毫秒
		
		
数组对象:
	数组类型检测	instanceof 或者 Array.isArray()
```
	//第一种方法
	var res = c instanceof Array //true
	//第二种方法
	var res = Array.isArray(a) //false
```
	添加或者删除数组元素：在数组的开头或者结尾，添加或者删除元素
		添加： 结尾push(参数)   	开头unshift(参数) 
		删除： 结尾pop()  		开头shift()
	
	修改数组元素：通过索引
	
	数组排序： 
		顺序排序（从小到大） ： sort()
		颠倒顺序： reverse()
	
	数组索引：通过元素查找索引
		indexOf: 找到给定值到第一个索引，不存在则返回-1
		lastIndexOf: 找到给定值到最后一个索引，不存在则返回-1
	
	数组转为字符串：
			toString()	用逗号连接数组元素
			join('分隔符')	用分隔符连接数组元素
	
	其它方法：
		fill()	填充数组元素
			方法用一个固定值填充一个数组中从起始索引到终止索引内的全部元素。不包括终止索引。
		splice(第几个开始，要删除的歌手)	删除数组元素
			
		slice(begin,end) 	截取数组元素
			方法返回一个新的数组对象，这一对象是一个由 begin 和 end 决定的原数组的浅拷贝（包括 begin，不包括end）。原始数组不会被改变。
		
		concat()	合并多个数组


字符串对象：
	字符串对象的使用：
		var str1= new String('hello world')
		var str2= 'hello world'
	
	根据字符返回位置(索引)：通过字符查找索引
		indexOf(searchValue, fromIndex): 找到value首次出现的位置，不存在则返回-1
			searchValue要被查找的字符串值
			fromIndex 开始查找的位置，默认0
		lastIndexOf(value): 找到value最后出现的位置，不存在则返回-1
	
	根据位置返回字符：
		str[索引]		通过索引查找字符
		charAt(索引)		通过索引查找字符
		charCodeAt(索引)

	
字符串对象：
	字符串对象的使用：
		var str1= new String('hello world')
		var str2= 'hello world'
	
	根据字符返回位置(索引)：通过字符查找索引
		indexOf(searchValue, fromIndex): 找到value首次出现的位置，不存在则返回-1
			searchValue要被查找的字符串值
			fromIndex 开始查找的位置，默认0
		lastIndexOf(value): 找到value最后出现的位置，不存在则返回-1
	
	根据索引返回字符：
		charAt(索引)				通过索引查找字符
		str[索引]				通过索引查找字符
		charCodeAt(索引)
	
	其他方法：
		str.concat(str2, [, ...strN])  			连接多个字符串
		str.slice(beginIndex[, endIndex])		截取字符串
		str.substring(indexStart[, indexEnd]) 	截取字符串，但是不接收负值
		str.substr(start[, length])				截取字符串，
		str.toLowerCase() 						转小写
		str.toUpperCase()  						转大写
		str.split([separator[, limit]])			将字符串分割成数组
		str.replace(substr, newSubStr)			替换（修改）字符串中的字符
		
		str.trim() 删除字符串前后空白
		str.trimStart() str.trimEnd()
		
DOM

了解
	API 
		Application Programming Interface 应用程序接口, 简称 接口
		实现某种功能，开发人员无须访问源码，无须理解内部实现机制，只需要知道使用即可。
		例如：打卡摄像头，打开相册	（juhe.cn）
	
	Web API
		操作浏览器和网页的接口。
		比如：console对象、document对象、window对象
		
	DOM
		文档对象模型。
		处理网页的接口，操作网页的元素。
		获取网页元素、获取属性、操作样式等。比如调整div大小，切换标签，做交互效果。
	
	DOM树：将网页看为树结构，称为文档树模型 
		把文档映射成树结构，通过节点对象对其处理。
		专有名词：
			文档 (document)
			元素 (element)
			节点 (node): 网页中的所有内容，都是节点。（比如：元素节点、属性节点、文本节点、注释节点）
	事件:可以被js检测到的行为，是一种“触发-响应”。比如：页面加载，鼠标单击，悬浮，滑动等。
		三要素：
			事件源：触发事件的元素（谁触发了事件）
			事件类型：比如click事件（触发了什么事件）
			事件处理程序：触发事件以后要执行的代码（触发事件以后要做什么）

掌握
获取元素的方式
	通过ID获取元素：document.getElementById('id名')
```
var box = document.getElementById('box')
```
	根据标签获取元素: document.getElementsByTagName('标签名')
		因为相同的标签可以有多个，结果是集合，称为伪数组，可以用数组索引。
```
	var li = document.getElementsByTagName('li')
	//通过数组索引访问伪数组li
	console.log(li[0])
	console.log(li[2])
	//修改css样式
	li[0].style.color = 'red'
```
	根据name获取元素：
	
操作元素的方式


值类型和引用类型
	值类型：		基本数据类型（5种）
		赋值传值：将变量复制一份
	引用类型：	复杂数据类型（引用数据类型）：Object(对象)
		引用传值：传递的是变量地址
		
垃圾回收机制


获取元素的方式
	通过ID获取元素：document.getElementById('id名')
```
var box = document.getElementById('box')
```
	根据标签获取元素: document.getElementsByTagName('标签名')
		因为相同的标签可以有多个，结果是集合，称为伪数组，可以用数组索引。
```
	var li = document.getElementsByTagName('li')
	//通过数组索引访问伪数组li
	console.log(li[0])
	console.log(li[2])
	//修改css样式
	li[0].style.color = 'red'
```
	根据name获取元素： document.getElementsByName('name名')
		因为相同的name可以有多个，结果是集合，称为伪数组，可以用数组索引。
		
	H5新增的获取方式:
		document.getElementsByClassName('class名')
			因为相同的class可以有多个，结果是集合，称为伪数组，可以用数组索引。
		
		document.querySelector('css选择器')
			返回指定css选择器的第一个元素
		
		document.querySelectorAll('css选择器')
			返回指定css选择器的所有元素集合
```
	 document.querySelector('#box')
	 document.querySelector('li')
	 document.querySelector('.ci')
	document.querySelectorAll('.fa')
```
	
	document对象的属性
		document.title
		document.body
		document.documentElement
		document.forms
		document.images

操作元素的方式
	操作元素的内容
	获取内容
		element.innerHTML 		保留标签、空格换行
		element.innerText 		去掉标签、空格、换行
		element.textContent 	去掉标签，保留空格、换行	
	修改内容
		element.innerHTML 	= '内容'
		element.innerText 	= '内容'
		element.textContent = '内容'
	
	操作元素的属性
		获取元素的属性
			element.属性名
		修改元素的属性
			element.属性名 = '属性值'
	
	操作元素的样式(CSS、style)
		1操作style属性
		
		2操作className属性


学习目标

1 应付考试

2 高薪工作

3 实现梦想、改变世界。。。


了解
排他思想:排除掉其它的（包括自己），再给自己设置效果。

事件：
	click 点击事件
	focus 获取文本框焦点
	blur	失去文本框焦点
	mouseover	鼠标指针经过事件
	mouseout 	鼠标指针离开事件

掌握

元素的属性和dom节点操作
属性操作
	获取属性
		推荐、任意属性通用：element.getAttribute('属性')
			内置属性： element.属性，比如id、style等
	设置属性
		推荐、任意属性通用：element.setAttribute('属性','值')
		内置属性： element.属性	= '值'
	移除属性
		element.removeAttribute('属性')
	
	自定义属性：data-属性名
		设置：
			element.setAttribute('data-属性','值')
			element.dataset.属性	= '值'
		获取：
			element.getAttribute('data-属性')
			element.dataset.属性	= '值'
DOM节点基础
	什么是节点：
		常见的节点类型：元素节点，属性节点，文本节点，注释节点等
		
	节点层级：节点之间的层级关系
		根节点、父节点、子节点、兄弟节点
		
	获取父节点
		element.parentNode 
	
	获取子元素节点
		element.children 
	
	获取第一个子元素
		element.children[0]
	
	获取最后一个子元素
		element.children[element.children.length - 1]
		
	获取兄弟节点
		
		
事件的绑定和事件对象的使用

常用的鼠标事件、键盘事件


了解
排他思想:排除掉其它的（包括自己），再给自己设置效果。

事件：
	click 点击事件
	focus 获取文本框焦点
	blur	失去文本框焦点
	mouseover	鼠标指针经过事件
	mouseout 	鼠标指针离开事件

掌握

元素的属性和dom节点操作
属性操作
	获取属性
		推荐、任意属性通用：element.getAttribute('属性')
			内置属性： element.属性，比如id、style等
	设置属性
		推荐、任意属性通用：element.setAttribute('属性','值')
		内置属性： element.属性	= '值'
	移除属性
		element.removeAttribute('属性')
	
	自定义属性：data-属性名
		设置：
			element.setAttribute('data-属性','值')
			element.dataset.属性	= '值'
		获取：
			element.getAttribute('data-属性')
			element.dataset.属性	= '值'
DOM节点基础
	什么是节点：
		常见的节点类型：元素节点，属性节点，文本节点，注释节点等
		
	节点层级：节点之间的层级关系
		根节点、父节点、子节点、兄弟节点
		
	获取父节点
		element.parentNode 
	
	获取子元素节点
		element.children 
	
	获取第一个子元素
		element.children[0]
	
	获取最后一个子元素
		element.children[element.children.length - 1]
		
	获取兄弟节点
		
		
事件的绑定和事件对象的使用

常用的鼠标事件、键盘事件

获取输入框内容
	element.value
获取元素内容
	element.innerHTML 

创建节点
	创建元素节点
	document.createElement()
		element.innerHTML 
		document.write()

添加节点
	element.appendChild(child) 在最后一个子节点后面添加子节点
	element.insertBefore(子节点, 指定节点)	在指定元素之前添加子元素节点
	
	
删除节点
	element.removeChild(child)  删除子节点
	
复制节点
	element.cloneNode(true/false)  
	
注册事件

获取/编辑输入框内容
	element.value
获取/编辑元素内容
	element.innerHTML 

创建节点
	创建元素节点
	document.createElement()
		element.innerHTML 
		document.write()

添加节点
	element.appendChild(child) 在最后一个子节点后面添加子节点
	element.insertBefore(子节点, 指定节点)	在指定元素之前添加子元素节点
	
删除节点
	element.removeChild(child)  删除子节点
	
复制节点
	element.cloneNode(true/false)  
	

事件进阶
注册事件（绑定事件）
	传统方式：on+事件类型，比如onclick、onmouseover
		同一个元素，同一个事件只能监听一次，如果多次则后一个覆盖前一个。
	事件监听：addEventListener ('事件类型',执行函数)
		同一个元素，同一个事件可以监听多次

删除事件
	element.onclick = null
	elemnt.removeEventListener ('事件类型',执行函数)

DOM事件流
	事件捕获：从外向内
	事件冒泡：从内向外

事件对象
	什么是事件对象：与触发事件相关的所有信息
	参数event就是事件对象
	element.事件 = function(event){}

	e.target  触发事件的对象
	this		绑定事件的对象
	
	阻止默认行为
	
	事件委托：把事件绑定在父节点，不给每个子节点单独设置
	
常用的鼠标事件
	onclick	点击事件
	onmouseover 鼠标经过  onmouseout鼠标离开
	onfocus	获取焦点	onblur 失去焦点
	onmousemove  鼠标指针移动
	
鼠标事件对象：跟鼠标事件相关的所有信息
	

常用的键盘事件
	keypress	按键按下去(不识别功能键)
	keydown  按键按下去
	keyup	 按键松开

键盘事件对象：跟键盘事件相关的所有信息
	keyBoardEvent
	
了解
BOM(Brower Object Model 浏览器对象模型)
	与浏览器交互的对象，核心对象（顶级对象）是window


掌握
window对象的常见事件
	window.onload 整个页面加载时触发
	window.resize 调整窗口大小时触发
	
两组定时器的使用
	设置定时器
		setTimeout(函数,毫秒)	在指定的毫秒后调用函数，只执行一次
		setInterval(函数,毫秒)	在指定的周期调用函数，可以执行无数次
	清除定时器
		clearTimeout(定时器ID)
		clearInterval(定时器ID)
	
JavaScript执行机制
	单线程：JS的特点、同一时间只能做一件事。
	
同步和异步：
	同步：前一个任务结束后再执行后一个任务。
	异步：做一件事的同时，可以做其他事情。
		同步做饭： 烧水煮饭，等水开了，再去切菜、炒菜
		异步做饭： 烧水煮饭的同时去切菜炒菜。	
<!-- 线程、协程、纤程、同步和异步 -->

Location对象
	URL的组成：
		http://10.24.0.2:80
		https://www.baidu.com:443
		https://www.bilibili.com/v/douga/?spm_id_from=333.1007.0.0	
	常用属性：
		search  返回查询部分（？之后的）
		host 返回主机加端口
		hostname 返回主机
		location.href 返回完整URL
		pathname
		port
	常用的方法：
		assign() 
		reload() 重新加载

navigator对象
	常用属性：appCodeName appName appVersion platform
	常用方法：

history对象
	常用属性：length
	常用方法：
		back() 回退
		forward() 前进
		go()
		

JS网页特效

了解
网页特效的概念
	
掌握
偏移量offset
	offsetLeft 	相对有定位的父元素左边框的偏移（如果没有，则相对body）
	offsetTop 	相对有定位的父元素上方的偏移（如果没有，则相对body）
	offsetWidth  自身的宽度（包含padding、border、内容）
	offsetHeight	自身的高度（包含padding、border、内容）
	offsetParent 	返回带有定位的父元素（如果没有，则返回body）
	
	offset和style的区别
	
可视区client
	clientLeft  	左边框大小
	clientTop 	 	上边框大小
	clientWidth 	可视的宽度（包含padding，不包含border）
	clientHeight 	可视的高度（包含padding，不包含border）

滚动scroll
	scrollLeft  卷去的左侧距离
	scrollTop 	卷去的上方距离
	scrollWidth 自身内容的宽度（不包含border）
	scrollHeight 自身内容的高度（不包含border）
	

