一、初识JavaScript (与JAVA没有关系)
	1 什么是JS
		编程语言，一般用于开发交互式页面。
		功能强大，可以开发前端（web+APP+小程序）、动画(animate.js)，也可以开发后端(node.js)、数据库(MongoDB)。
		

		网页组成：HTML＋CSS+JavaScript
		JS内嵌在网页中，通过浏览器内置的JS引擎解释并执行（主要运行在浏览器中）
		
		浏览器分类：
		浏览器内核的分类：
			渲染引擎（排版引擎）：解析HTML、CSS，比如Chrome浏览器的Blink
			JS引擎：JS语言的解释器，比如Chrome浏览器的V8引擎
		
		JS代码的执行特点：逐行执行。
		
		JS的常用框架：React.js  Angular.js  Vue.js(尤雨溪)
		
		JS的特点：
			1 脚本语言（JavaScript、python、php）, 编译语言(JAVA、C++)
			2 跨平台 （不依赖操作系统，只需要浏览器支持） 
			3 支持面向对象（C语言不支持面向对象，函数式编程）
			
		JavaScript组成：
			ECMAScript:基本语法，是JS的核心。
			DOM（Document Object Model）: 文档对象模型，操作网页元素。
			BOM: 浏览器对象模型，操作浏览器窗口。
			
	2 常用开发工具
		VS code , Hbuilder, Sublime text, DreamWeaver，WebStorm等等
		
	3 JS入门
		代码书写位置
			1 行内式：JS代码写在HTML标签事件属性中(onclick、oninput、onmousemove)
```
	<input onmousemove="console.log('这是鼠标抚摸事件！')" oninput="alert('你的输入错误！')" type="text" />用户名
	<br />
	<input onclick="alert('你的提交成功了！')" type="submit" value="提交" >
```
			2 内嵌式（嵌入式）：写在<script>标签里面，<script>标签可以写在<head>或者<body>中
```
<script>
		var a = 11;
		var b = 222;
		var c = a+b;
		console.log(c)
		// alert(c)
</script>
```
			3 外部式(外链式):js代码写在单独的文件中,扩展名".js". 通过<script>标签引入.
```
	<script src="js/study.js" > </script>
```

		语法规则:
			1 严格区分大小写
			2 对空格 换行 缩进(tab)不敏感
			3 每行结束的英文分号";"可以省略, 但是推荐加上
		
		注释:
			单行注释 : Ctrl+/
```
	// var n = {};
	// e.m = t, e.c = n, e.p = "/build/", e(0)
```
			多行注释 : Ctrl+Shift+ /
```
/* var n = {};
	e.m = t, e.c = n, e.p = "/build/", e(0) */
```

		输入和输出语句
			alert('警告信息')
			console.log('控制台输出信息')
			prompt('弹出输入框')
```
	alert('这是警告框');
	console.log('每一个星球都有一个驱动核心，每一种思想都有影响力的种子。感受世界的温度，年轻的你也能成为改变世界的动力，百度珍惜你所有的潜力。你的潜力是改变世界的动力！');
	prompt('请你输入年龄！');
```
```
	<script>
		var a = document.getElementById('box');
		a.innerHTML = '哈哈哈哈';
	</script>
```

	4 JS变量
		变量是内存中的一块空间。
		
		注意：可以不声明直接赋值。
		
		变量命名规范
			由字母 数字 下划线_ 美元符号$组成 (中文也可以不推荐)
			严格区分大小写
			不能以数字开头
			不能是关键字、保留字。
				关键字比如 break if
					就是在js中已经被使用了的单词。js本身已经赋予其功能
				保留字
					在未来js标准中可能被用来作为关键字的单词
					
			合理命名，尽量做到见其名知其意。
			三种命名法：
				小驼峰命名法 
				大驼峰命名法
				下划线命名法
```
	//小驼峰 第一个单词首字母小写，后面的单词首字母大写
	var mySchoolAddress = '重庆涪陵';
	//大驼峰 第一个单词首字母大写，后面的单词首字母大写
	var MySchoolAddress = '重庆涪陵';
	//下划线 用下划线分割
	var my_school_address = '重庆涪陵';
```

	JavaScript基础（上）
		1数据类型
			JS是弱类型语言，不要提前声明变量类型。
			强类型语言:Python JAVA C C++ GO ..
```
	var age int;
	var name String;
```
			弱类型语言:JS  php 
```
	var age;
	var name;
```
			分为：基本数据类型和复杂数据类型（引用数据类型）
				基本数据类型(5种)：Boolean（布尔型） String字符型 Number数字类型 Null空 Undefined未定义
				引用数据类型(复杂数据类型)：Object（对象）
					Number数字类型，整数和浮点数（小数）
						NaN 非数值
						isNaN 判断变量是否为非数字类型
```
	console.log( isNaN("abcdefg") )
```
					String字符型
						用单引号'' 或者双引号""
							单引号里面不能加单引号（转义），可以加双引号
							双引号里面不能加双引号（转义），可以加单引号
						常见的转义符：\n换行 \'单引号 \"双引号  \\反斜杠
						
						字符串长度：length属性
```
var test="                ";
var long = test.length;
```
						访问字符串中的字符：[index]，如果超过最大值，返回undefined
						
						拼接字符串: 加号"+" 
```
		var str1 = '明天是\'星期六\'!!';
		console.log('字符串长度：'+str1.length)
		console.log('字符串索引：'+str1[6])
		var first = '520';
		var second = '10';
		var name = first + second;
```
			布尔类型: true和false
			
			undefined 未定义型
```
var a;
```
			null 类型
```
var b = null;
```
			判断null
```
	if(a === null){
		console.log('a的数据类型是null')
	}
```
			检测数据类型：typeof 
```
var result = true;
console.log(typeof result)
```
		2数据类型转换
			转化为字符串类型：
				"+" 拼接字符串
				toString() 
				String() 方法
```
	var result = undefined;
	console.log(typeof result)
	// result = result + ""
	// result = result.toString();
	result = String(result)	
	console.log(typeof result)
```
				转化为数字类型：
					parseInt()  转整数
					parseFloat()  转浮点数（小数）
					Number() 
					算术运算符隐式转换(-、*、/)
```
	var result = "111.000";
	console.log(typeof result)	
	// result = (result) - 1 ;
	result = parseInt(result)
	result = parseFloat(result)
	console.log(result)
	console.log(typeof result)
```
				转化为布尔型: Boolean()
					没有意义的值会转为false，比如undefined, null, 0,空'',NaN
					其他的转为true
		3运算符
			算术运算符： + - * /   %（取余数，取模）
			
			递增（自增）、递减（自减）符号： ++ 、 --
				x++和++x 
						相同点：结果加1， x = x + 1;
						不同点：x++返回值不变，++x返回值+1
				优先级高于算术运算符
			
			比较运算符：结果是布尔值,true和false。大于>  小于<  大于等于>=  小于等于<=  等于==  不等于!=  全等===  不全等!==
			
			逻辑运算符：
				&&，与，和
					a&&b ,a和b都是true,结果才是true
				||,或
					a||b, a或者b有一个是true，结果就是true
				! ,非，否定
					!a , a是false，结果才是true
			
			赋值运算符：将右边的值赋值给左边变量
				常用的：=  += -= /= *=  %/
				+= ：
					x += y; 等于 x = x + y;
				-= ：
					x -= y; 等于 x = x - y;
			
			三元运算符： 条件表达式  ? 	表达式1 : 表达式2
```
'100'=="ok" ? alert('吃火锅') : alert('吃小面');
```
		4流程控制
			顺序结构：默认，逐行执行
			
			分支结构：根据条件执行
				单分支：单个条件表达式
					if(条件表达式){
						//代码段
					}
				双分支：
					if(条件表达式){
						//代码段1
					}else {
						//代码段2
					}
					
				多分支：多个条件表达式
					switch能写的，一定能写。反之则不然。
					if(条件表达式1){
						//代码段1
					}else if(条件表达式2) {
						//代码段2
					}else if(条件表达式3) {
						//代码段3
					}else {
						//代码段n
					}
	
				switch语句：多分支，功能与if..else if类似。
						只有一个表达式。
						break不能少
```
		switch(表达式) {
			case '值1':
				//代码段1
				break;
			case '值2':
				//代码段2
				break;
			default:
				//代码段n
		}
```

		循环结构：重复执行
			for循环：适合循环次数已知。
```
	for(初始化变量; 条件表达式（循环条件）; 操作表达式（每次循环后的操作） ){
		//循环体
	}
```

		断点调试


		循环结构：重复执行
			for循环：适合循环次数已知。
```
	for(初始化变量;循环条件;操作表达式){
		//循环体
	}
```

			断点调试
			
			while循环：适合循环次数未知。可以和for循环互相改
```
	while(条件表达式){
		//循环体
	}
```
			continue（继续）：跳过后面的循环代码，继续下一次循环
				只能跳过当前循环，如果多层循环嵌套，需要加循环标签,continue 标签名;
			break(打断)：跳过整个循环体，终止循环了
				只能中断当前循环，如果多层循环嵌套，需要加循环标签,break 标签名;
			
	数组：
		创建数组：
```
	var arr1 = [];
	var arr2 = new Array();
	var color = ['red','green','yellow','purple','pink','white']
```
		访问数组元素:
```
	console.log(color[6]);
```

		数组遍历：
			for循环遍历
		
		获取数组长度：.length
			
		修改数组长度：

数组：
	创建数组： 
	访问数组元素：
	数组遍历：
		for循环，循环次数.length-1
		for...in
		for...of
		

	数组长度: .length
	修改数组长度：.length=长度值
	新增或者修改数组元素：

二维数组：
	创建二维数组：[]或者new Array()
	遍历二维数组：双层for循环
	
函数：function 方法
	声明函数：
		function 名称(){
			//代码
		}

```
	function jiafa(){
		console.log('i love u')
	}

	jiafa() 
```
	调用函数：


函数(function 方法)：

函数的使用：
	声明函数：
		function 名称(){
			//代码
		}

```
	function jiafa(){
		console.log('i love u')
	}

	jiafa() 
```
	调用函数：
		名称()

什么是函数：
```
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

函数的参数：
	形参：声明函数时的参数
		function 名称(参数1,参数2...)
			//代码
		}
	实参：使用函数时的参数
		名称(参数1,参数2...)
	

	参数的数量：
		形参大于实参，undefined
		实参大于形参,忽略多余的参数
	
	返回值：必须要有返回值
		function 名称(参数1,参数2...)
			//代码
			return 结果;
		}
		
	return可以提前终止函数：
	
	arguments: 获取所有实参


函数(function 方法)：

函数的使用：
	声明函数：
		function 名称(){
			//代码
		}

```
	function jiafa(){
		console.log('i love u')
	}

	jiafa() 
```
	调用函数：
		名称()

什么是函数：
```
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

函数的参数：
	形参：声明函数时的参数
		function 名称(参数1,参数2...)
			//代码
		}
	实参：使用函数时的参数
		名称(参数1,参数2...)
	
	参数的数量：
		形参大于实参，undefined
		实参大于形参,忽略多余的参数
	
	返回值：推荐必须要有返回值，终止函数并且返回
		function 名称(参数1,参数2...)
			//代码
			return 结果;
		}
		
	return可以提前终止函数：
	
	arguments: 获取所有实参

函数进阶：
	匿名函数：没有函数名称

	函数表达式：
		1 声明函数并且赋值给一个变量,通过这个变量调用
		2 函数表达式必须写在调用前
```
	var 名称 = function(参数1,参数2...)
		//代码
		return 结果;
	}
```

	回调函数：
		将一个函数作为参数传递给另外一个函数


函数进阶：
	匿名函数:
```
	function(参数1,参数2...)
		//代码
		return 结果;
	}
```
	函数表达式： 
		1 声明函数并且赋值给一个变量,通过这个变量调用
		2 函数表达式必须写在调用前
```
	var 名称 = function(参数1,参数2...)
		//代码
		return 结果;
	}
	名称()
```
	回调函数：
		将一个函数作为参数传递给另外一个函数
		
	递归调用：
		函数自己调用自己
		
	作用域：
		全局变量：在整个页面生效
			在函数外面创建的变量，或者在函数内部不用var创建
			在浏览器关闭页面的时候，才会销毁，比较占有内存资源
		局部变量：在函数体内用var定义的变量，
			只能在函数体内使用，不能在函数外使用。
			在函数执行完就会销毁，比较节约内存资源。	
		块级变量：let关键字, 仅在{}里面有效，比如if、for、while
		
	作用域链：由内向外查找变量（函数里面可以用外面的，但是函数外面不能用函数里面的）
		首先在当前函数内查找变量，如果找不到，则向上一层函数查找，直到全局变量(全局作用域)。
		
	闭包函数：
		在函数外部读取函数内部的变量。
		可以让变量常驻内存。


对象 (object, 面向对象编程OOP, 万物皆可对象)
	什么是对象：是一种数据类型，由属性和方法组成。
		属性:事物的特征,通过对象.属性名访问
		方法：事物的行为,通过对象.方法名()访问
		
	创建对象：
	
	利用字面量创建对象：
		1 用大括号{}包裹
		2 每个成员通过键值对（key:value）形式保存，key是属性名或者方法名，value是对应的值
		3 对象成员之间用逗号,分隔
```
	var car = { };
```
	访问对象的属性和方法：
		访问对象的属性: 对象.属性名  或者 对象['属性名']
		访问对象的方法：对象.方法名()  或者  对象['方法名']()
		
		当对象成员中包含特殊字符时，可以用字符串
		
		手动赋值属性或者方法：
			对象.属性名 或者 对象.方法名
		
		this关键字：代表当前对象


​			
	利用new Object创建对象
```
	var car = new Object();
```

	利用构造函数（模板）创建对象:
		构造函数名一般首字母大写
		//编写构造函数
		function 构造函数名(){
			this.属性 = 属性
			this.方法  =方法
			//方法体
		}
		//使用构造函数创建对象
		var obj = new  构造函数名()
	
	静态属性和静态方法：不需要创建实例对象就能使用。
	
	遍历对象的属性和方法：for...in
	
	判断对象成员是否存在： in运算符

内置对象:(不编写,直接使用)
	通过查阅文档熟悉内置对象: mdn	
	Math对象: 数学运算，不需要实例化
		Math.round(x)  四舍五入
		Math.floor(x)  向下取整
		Math.ceil(x)	向上取整
		
		Math.random()  获取大于等于0.0 小于1.0的随机数
		
		//大于等于min,小于max的随机值
		Math.random() * (max - min) + min
		//获取min-max之间的随机整数
		Math.floor( Math.random() * (max - min + 1) + min )
		
		//1-任意数之间,可以等于1
		Math.floor( Math.random() * (max +1) + 1)	


​		
	日期对象: 
		首先使用new Date()实例化
		日期对象的常用方法:
			获取日期
			设置日期
			
		时间戳： 当前时间，单位毫秒，  默认从1970-01-01 00:00:00到当前时间的毫秒数
```
		var date = new Date();
		//获取 时间戳
		var time1 = date.getTime()
		var time2 = date.valueOf()
```

	数组对象：
		数组类型检测：instanceof Array 或者 Array.isArray()
		添加或者删除数组元素：在数组的结尾或者开头，添加或者删除新的元素


数组对象：
	数组类型检测：instanceof Array 或者 Array.isArray()
	添加或者删除数组元素：在数组的结尾或者开头，添加或者删除新的元素
		添加：尾部push(参数) 		开头unshift(参数) 
		删除：尾部pop()			头部shift()
	修改数组元素：通过索引
	数组排序： 
		颠倒顺序： reverse()   
		顺序（从小到大）： sort()
	数组索引：查找数组元素
		indexOf() 返回给定值的第一个索引，如果不存在则返回-1
		lastIndexOf()	返回给定值的最后一个索引，如果不存在则返回-1
	数组转换为字符串：
		join('分隔符')  分隔符连接
		toString()	逗号连接
	其他方法：填充数组fill()  删除数组元素splice()  截取数组元素slice()  合并数组concat()等
		
字符串对象：
	字符串对象使用: new String('字符串')
	根据字符返回位置：
		indexOf() 返回给定值的第一个索引，如果不存在则返回-1
		lastIndexOf()	返回给定值的最后一个索引，如果不存在则返回-1

项目需求
前台前端：
	首页（主要功能：商品搜索、商品分类、图片轮播、店铺信息、商品列表、客服私聊）
	分类（主要功能：分类筛选、列表排序、列表展示切换）
	商品详情（主要功能：图片轮播、商品收藏、分享、详情展示、库存、销量、规格挑选、添加购物车、购买）
	购物车	（主要功能：商品列表、编辑、数量、合计、结算）
	订单结算	（主要功能：新增地址、选择地址、留言、订单信息、提交订单）
	用户中心：（账号注册、微信授权注册、账号登录、微信授权登录、用户其它注册信息 ）
	账号管理：（主要功能：头像、昵称、修改密码、意见反馈、客服电话、用户协议、隐私政策、退出登录）
	订单管理：（主要功能：全部、待付款、待发货、待收货、待评价）
	我的收藏：（主要功能：增删查改）
	地址管理：（主要功能：增删查改）
	我的足迹：（主要功能：增删查改）
前台后端：

后台管理前端：
后台管理后端：

其它：对接需求+域名+服务器+小程序申请+测试+维护+翻译英语


字符串对象：
	字符串对象使用: new String('字符串')
	
	根据字符返回位置：查找字符
		indexOf() 返回给定值的第一个索引，如果不存在则返回-1
		lastIndexOf()	返回给定值的最后一个索引，如果不存在则返回-1
	
	根据位置（索引）返回字符：
		charAt(index) 根据位置(索引)查找字符
		charCodeAt(index)	根据位置(索引)获取字符的ASCII码
		char[index]	获取指定位置的字符
	
	字符串操作方法：
		concat(str1,str2...)  连接字符串
		slice(start,end) 截取
		substring(start,end) 截取，但是不接收负值
		substr(start, length) 截取，接收长度
		toLowerCase() 转小写
		toUpperCase() 转大写
		split('分隔符') 分割, 将字符串分割为数组
		replace() 替换(修改)
		trim() 删除字符串首尾空白
		trimEnd()  trimStart()
		
	值类型和引用类型
		值类型：基本数据类型(5种)：Boolean（布尔型） String字符型 Number数字类型 Null空 Undefined未定义
		引用类型：引用数据类型(复杂数据类型)：Object（对象）
		
		值类型是赋值传值：不会改变原来的变量值，因为赋值是单独复制一份
		引用类型是引用传值：会改变原来的变量值，因为赋值的是内存地址
	
	js垃圾回收机制自动释放：

了解：
	API：
		Application Programming Interface 应用程序接口，简称接口
		实现某种功能，开发人员无须访问源码，无须理解内部实现机制，直接使用即可。
		比如：打开摄像头，打开相册等等
	web API ：操作浏览器和网页的接口
		DOM（Document Object Model）: 文档对象模型，操作网页元素。
		BOM: 浏览器对象模型，操作浏览器窗口。
		比如:console对象、document对象、window对象
	DOM ：
		操作网页的接口。
		DOM（Document Object Model）: 文档对象模型，操作网页元素。
		可以获取网页元素、属性、设置样式等，比如改变div大小，切换标签，购物车等动态效果
	DOM树：
		将HTML文档看成树结构，称为文档树模型。把文档映射成树结构，通过节点对象进行处理。
		专有名称：
			文档（document） 
			元素 (element)
			节点 (node):网页中的所有内容，在DOM树中都是节点。
	
	事件: 可以被js检测到的行为，是一种“触发-响应”机制。比如鼠标单击、悬浮、滑动等
		三要素：
			事件源（谁触发了事件）
			事件类型（触发了什么事件）, 比如点击事件onclick
			事件处理程序（触发事件以后做什么）


​	
掌握
​	获取元素的方式 
​		根据ID获取元素:document.getElementById('ID名')
```
	var cai = document.getElementById('cai')
	console.log(cai)
```
		根据标签获取元素: document.getElementsByTagName('标签名')
			由于有相同name的标签可以有多个，导致结果是伪数组，可以通过数组索引来访问元素。
```
//第一种方法
var ele = document.getElementsByTagName('li')
console.log(ele)
//第二种方法
// var element = document.getElementById('color')
// console.log(element)
// var lis = element.getElementsByTagName('li')
// console.log(lis)
```
		根据name获取元素:	getElementsByName('name名')
			结果是集合, 结果是伪数组，通过数组索引来访问元素。
```
	var fruit = document.getElementsByName('fruit')
	console.log(fruit)
	console.log(fruit[0])
	//将第一个元素的checked属性设置为true
	fruit[0].checked = 'true'
```

	HTML5新增的获取方式
		根据类名获取：getElementsByClassName('类名')
			结果是集合, 称为伪数组，通过数组索引来访问元素。
```
	var one = document.getElementsByClassName('one')
```
		querySelector('css选择器') 
			返回指定css选择器的第一个元素对象
			
		querySelectorAll('css选择器') 
			返回指定css选择器的所有元素对象
			结果是伪数组，通过数组索引来访问元素。
```
	var two = document.querySelectorAll('.two')
	var lable = document.querySelector('label')
	var cai = document.querySelector('#cai')
```

	document对象的属性
		document.body
		document.title
		document.documentElement
		document.forms
		document.images


​	
操作元素的方式
​	1 操作元素内容
​		获取、修改元素内容
​		element.innerHTML  		保留标签、空格、换行
​		element.innerText		去掉标签、空格、换行
​		element.textContent	 	去掉标签，保留空格、换行

	2 操作元素的属性
		获取、修改元素的属性
```
	document.title = '懒猫'
	img.src = '2.jpg'
	img.title = '这是一只懒猫'
```
	3 操作元素的样式(CSS)
		操作style属性
			元素.style.样式名
```
	var box = document.getElementById('box')
	box.style.backgroundColor = 'red'
	box.style.fontSize = '20px'
```
		操作className属性


了解
排他思想
	排除掉其他的(包括自己),然后给自己设置实现的效果.
	事件类型（触发了什么事件）,
		点击事件onclick
		获取文本框焦点onfocus, 失去文本框焦点onblur
		鼠标指针经过事件onmouseover, 鼠标指针离开事件onmouseout
节点基础
	什么是节点
	节点层级（节点之间的关系）
		根节点
		父节点
		子节点
		兄弟节点
		
掌握
元素属性和dom节点操作
	获取属性值
		推荐、通用: element.getAttribute('属性值')	
		获取内置属性: element.属性值
	设置属性值
		推荐、通用: element.setAttribute('属性名','属性值')
			  = 属性值 （属性值会加上data-）
		获取内置属性: element.属性名 = '属性值'
		H5规定用 “data-属性名”的方式设置自定义属性名。
		
	移除属性值
		element.removeAttribute('属性名')


​	
​	
事件的绑定和事件对象的使用

常用的鼠标事件 键盘事件


事件: 可以被js检测到的行为，是一种“触发-响应”机制。比如鼠标单击、悬浮、滑动等
	三要素：
		事件源（谁触发了事件）
		事件类型（触发了什么事件）,
			点击事件onclick
			获取文本框焦点onfocus, 失去文本框焦点onblur
			鼠标指针经过事件onmouseover, 鼠标指针离开事件onmouseout
		事件处理程序（触发事件以后做什么）
			
	
操作元素的方式
	1 操作元素内容
		获取、修改元素内容
		element.innerHTML  		保留标签、空格、换行
		element.innerText		去掉标签、空格、换行
		element.textContent	 	去掉标签，保留空格、换行

	2 操作元素的属性
		获取、修改元素的属性
```
	document.title = '懒猫'
	img.src = '2.jpg'
	img.title = '这是一只懒猫'
```
	3 操作元素的样式(CSS)
		操作style属性
			元素.style.样式名
```
	var box = document.getElementById('box')
	box.style.backgroundColor = 'red'
	box.style.fontSize = '20px'
```
		操作className属性


​		

1 应付考试

2 高薪工作

3 改变事件,实现梦想


事件: 可以被js检测到的行为，是一种“触发-响应”机制。比如鼠标单击、悬浮、滑动等
	三要素：
		事件源（谁触发了事件）
		事件类型（触发了什么事件）,
			点击事件onclick
			获取文本框焦点onfocus, 失去文本框焦点onblur
			鼠标指针经过事件onmouseover, 鼠标指针离开事件onmouseout
		事件处理程序（触发事件以后做什么）
			
	
操作元素的方式
	1 操作元素内容
		获取、修改元素内容
		element.innerHTML  		保留标签、空格、换行
		element.innerText		去掉标签、空格、换行
		element.textContent	 	去掉标签，保留空格、换行

	2 操作元素的属性
		获取、修改元素的属性
```
	document.title = '懒猫'
	img.src = '2.jpg'
	img.title = '这是一只懒猫'
```
	3 操作元素的样式(CSS)
		操作style属性
			元素.style.样式名
```
	var box = document.getElementById('box')
	box.style.backgroundColor = 'red'
	box.style.fontSize = '20px'
```
		操作className属性


​		

1 应付考试

2 高薪工作

3 改变事件,实现梦想

事件类型（触发了什么事件）
		click点击事件
		focus获取文本框焦点, blur失去文本框焦点
		mouseover 鼠标指针经过事件, mouseout鼠标指针离开事件
		
了解
排他思想
	排除掉其他的(包括自己),然后给自己设置实现的效果.
	事件类型（触发了什么事件）,
		点击事件onclick
		获取文本框焦点onfocus, 失去文本框焦点onblur
		鼠标指针经过事件onmouseover, 鼠标指针离开事件onmouseout
节点基础
	什么是节点
	节点层级（节点之间的关系）
		根节点
		父节点
		子节点
		兄弟节点
		
掌握
元素属性和dom节点操作
	获取属性值
		通用: element.getAttribute('属性值')	
		获取内置属性: element.属性值
	设置属性值
		H5规定用 “data-属性名”的方式设置自定义属性名。
		通用: element.setAttribute('属性名','属性值')
			 element.dataset.属性名 = 属性值 （属性值会加上data-）
		获取内置属性: element.属性名 = '属性值'
	移除属性值
		element.removeAttribute('属性名')

节点基础
	什么是节点
	节点层级（节点之间的关系）
		根节点
		父节点
		子节点
		兄弟节点
	
	获取父节点
		element.parentNode
	
	获取子元素
		推荐使用： element.children 
			结果是伪数组，通过索引访问
		
	获取子元素的节点： element.children[索引]
		获取子元素的第一个节点：element.children[0]
		获取子元素的最后一个节点：element.children[element.length-1]
	
	获取兄弟节点
	
	获取兄弟元素
		下一个兄弟元素
		element.nextElementSibling
		//上一个兄弟元素
		element.previousElementSibling

节点操作
	创建子节点
		document.createElement('tagName')
		动态创建节点：
			document.write()
			element.innerHTML = ''
			document.createElement('tagName')
	
	添加子节点
		node.appendChild()  添加到子节点最后面
		
		node.insertBefore(child, 指定元素)  插入到指定子节点前面
		  
	删除子节点
		node.removeChild(child)
	
	复制节点
		node.cloneNode(true/false)

事件的绑定和事件对象的使用
注册事件（绑定事件）
	传统方式：
		on事件类型，比如onclick、onmouseover等
		特点：同一个元素同一个事件只能设置一个处理函数（如果有多个，后一个覆盖前一个）
	事件监听：
		element.addEventListener(type,callback), type参数：事件类型，callback:处理函数

删除事件：
	传统方式：on事件类型 = null
	事件监听：element.removeEventListener(type,callback)

DOM事件流：
	事件捕获：由外向内
	事件冒泡：由内向外

什么是事件
	event：触发事件相关的所有信息
	element.onclick = function(event) {}

事件对象
	e.target 返回触发事件的对象
	this	返回的是绑定事件的对象

阻止默认行为：e.preventDefault()
事件委托：不给子元素注册事件，给父元素注册事件。
	
	
常用的鼠标事件
	onclick 点击
	onfocus 获取焦点	 onblur 失去焦点
	onmouseover	鼠标经过	onmouseout	鼠标离开
	onmousemove 鼠标移动事件

 键盘事件


element.value 获取文本框的内容

element.innerHTML 获取元素的内容


常用的鼠标事件
	onclick 点击
	onfocus 获取焦点	 onblur 失去焦点
	onmouseover	鼠标经过	onmouseout	鼠标离开
	onmousemove 鼠标移动事件

 键盘事件
	keypress	按键按下触发(不识别功能键)
	keydown  按键按下触发
	keyup 	按键松开触发
	
	

BOM：浏览器对象模型、与浏览器进行交互的对象、顶级对象是window
了解
	什么是BOM
	Location、Navigator、history对象
	
掌握
Window对象的常见事件
窗口加载事件:load
	windows.onload

调整窗口大小事件:resize
	windows.onresize
	
两组定时器的使用
		//设置定时器
		setTimeout(调用的函数，延迟的毫秒数)：在指定的毫秒后执行，只执行一次
		setInterval(调用的函数，延迟的毫秒数)：在指定的周期（毫秒）执行,执行无数次
		
		//清除定时器
		clearTimeout()
		clearInterval()

JS执行机制
	单线程：同一时间只能做一件事。
	
	同步和异步：
		异步：比如click、setTimeout、setInterval等

location对象
	URL的组成：
		http://www.baidu.com:80
		https://www.baidu.com:443
		https://game.bilibili.com/platform/?spm_id_from=666.32.0.0
	常用的属性：search、href、port
	常用的方法：reload()、assign()

navigator对象
	常用属性：appCodeName appVersion
	常用的方法：javaEnabled()

history对象：
	常用属性：length 
	常用方法：后退back()、	forward()、go()

了解
	网页特效的概念
		
掌握
	 元素偏移量offset
		// 打印盒子的宽度和高度(包含边框、padding、内容)
		offsetWidth //盒子宽度
		offsetHeight //盒子高度
		//相对有定位父元素左边框的偏移（如果没有定位，则返回Body）
		offsetLeft
		//相对有定位父元素上方的偏移（如果没有定位，则返回Body）
		offsetTop
	
	offset和style的区别
	
	可视区client
		clientLeft  左边框大小
		clientLeft	上边框大小
		clientWidth	自身内容的宽度（包含padding，不包含border）
		clientHeight	自身内容的高度（包含padding，不包含border）
		
	滚动scroll
		scrollLeft 被卷去的左侧距离，不带单位
		scrollTop  被卷去的上方距离，不带单位
		scrollWidth	自身的宽度(不包含border)，不带单位
		scrollHeight 自身的高度(不包含border)，不带单位

