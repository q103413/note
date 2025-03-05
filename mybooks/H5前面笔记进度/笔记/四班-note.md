网页设计（前端、front end）
张卫 thinkzw@foxmail.com
电商+金融+ERP、OA+仿抖音、小红书、微信

上网方式：
	电脑端：网页
	手机：网页+APP+小程序

解决：用户体验问题

必备条件：
	1、会上网、会打字、基础英文
	2、兴趣
	3、肯做练习、耐心

具体学习：
	1软件  5%时间
		浏览器（谷歌浏览器、火狐浏览器、苹果浏览器、IE浏览器）
		浏览器开发者工具：F12
		代码编辑器：
			记事本、DreamWeaver（DW、梦想编织者）、Hbuilder、VS code、Sublime
	2语言（和浏览器打交道的语言） 95%以上时间
		HTML
		CSS
		Javascript 

什么是互联网？
	WWW（Wolrd Wide Web,万维网）
	3个基本组成：https://www.baidu.com/
		URL：www.baidu.com
		HTTP: 协议
		HTML:Hyper Text Markup Language 超文本 标记 语言
			1可以由浏览器直接解释执行
			2不是编程语言、但是是一门标记语言
			3标记语言是一套标记标签
网页：
	1、扩展名：.html或者.htm
	2、必须由浏览器阅读
	3、组成：文字、图片、视频、音频、超链接、特效、动画等
   
web标准：
	W3C（万维网联盟），不是一个标准，它是一系列标准的集合
	1，结构化标准  网页结构（Structure） 		对应 HTML
	2，表现标准	 网页样式（表现Presentation） 	对应 CSS
	3，行为标准	 网页行为（Behavior） 		对应 JavaScript

浏览器：	
	浏览器（谷歌浏览器、火狐浏览器、苹果浏览器、IE浏览器）
	开发者工具：F12（error错误、warn警告）

代码编辑器：
	1、记事本
	2、DreamWeaver（所见即所得）
		1、下载 （中文破解版）
		2、安装
		3、使用
		认识界面：菜单栏、面板组、属性栏、插入栏、网页编辑窗
		新建站点（项目）：
			菜单栏-站点-新建站点-输入名称、路径
		编辑站点：菜单栏-站点-管理站点-输入名称、路径（删除、复制站点等）
		新建网页：
			1、菜单栏文件-新建-输入网页文档标题-创建-文件保存-输入网页文件名称、修改路径
			2、先左键选择父文件夹-点击右键-输入名称
			3、快捷键：Ctrl+N 
		新建目录：（方便管理网页）
			先左键选择父文件夹-点击右键-输入名称
		编辑网页、目录 ： 单击右键-编辑-重命名
	3、HBuilder 
		1、下载 （官网下载）
		2、安装
		3、使用
			认识界面
			新建站点（项目）：
				1、菜单点文件-新建-项目-输入名称、路径
				2、左侧单击右键-新建-项目-输入名称、路径
				3、快捷键：Ctrl+N 
			新建网页：  
				1、菜单点文件-新建-html文件-输入名称、路径
				2、左侧单击右键-新建-html文件-输入文件名称、路径
				3、快捷键：Ctrl+N
			新建目录：（方便管理网页）
				1、菜单栏点文件-新建-目录-输入名称、路径
				2、先左键选择父文件夹-点击右键-输入名称
				3、快捷键：Ctrl+N 
			注意保存路径：
					1、输入名称之后-浏览-选择需要的保存目录
					2、左键点击父文件夹

HBuilder 快捷键：
	搜索：Ctrl + F (find)
	复制行或选区：ctrl+insert
	字体放大：增大字体【ctrl+鼠标滚动向上】
	格式化：Ctrl+k
	注释：Ctrl+/
	向下插入行：ctrl+enter
	向上插入行：ctrl+shift+enter
	 
演示HTML标签：举四个例子
	1，标题：<h1> - <h6> ，从大到小、h1最大。。
	2，段落：<p>
	3、超链接：<a>
	4、插入图片 (image)：<img>

HTML标签（HTML tag）：
	1 由尖括号包围的关键词，比如<html>
	2 通常是成对出现，比如<p>这是段落</p>，<title>这是标题</title>
	3 标签对中的第一个标签是开始标签，第二个标签是结束标签
		开始标签又叫做开放标签，结束标签又叫做闭合标签	
空标签：单独存在的标签。 比如：<br />、<hr />
	1 没有内容
	2 没有关闭标签
	3 在开始标签就关闭。

HTML元素：从开始标签（start tag）到结束标签（end tag）的所有代码。
	1 从开始标签起始，到结束标签终止
	2 元素的内容：开始标签与结束标签之间的内容
	3 某些HTM元素具有空内容（empty content）,比如<hr />
	元素 = 标签+元素内容

空元素：
	没有内容的HTML元素成为空元素。
	就是没有关闭标签的空元素。比如<hr />
	在开始标签中关闭。

注意：
	1、不要忘记结束标签(空标签也要写“/”)
		即使忘记结束标签，大多数浏览器也能正常显示。
	2、推荐使用小写标签
		即使HTML标签对大小写不敏感：比如<P> 等同于 <p>
	3、 所有的代码都要用英文状态

HTML属性：
	1 属性为HTML元素提供附加信息
	2 属性总是以名称/值对的形式出现，比如 name="value"
	3 属性总是在开始标签。
		比如可能有以下属性： align对齐方式 face字体 size大小 color颜色 width宽 height高。。。
	4、适用于大多数HTML元素的属性：
		style: 设置元素的样式（CSS）
			比如设置颜色、宽度、高度等：style="color:red;width:200px;height:100px;" 
		title：规定元素的额外信息（可在工具提示中显示）

注释：
	1 提供可读性、更容易理解。
	2 浏览器会忽略注释，也不会显示出来。
	3 <!-- 这是注释 --> 或者快捷键：Ctrl+/

学习HTML标签：
	<!DOCTYPE> 声明：帮助浏览器正确地显示网页
		document type(文档类型)的简写。 
		必须是HTML文档的第一行
		不是HTML标签，是指示浏览器网页的HTML版本。
		没有结束标签，对大小写敏感，一般写的大写。
	<html>: 
		最先出现的标签，成对出现。
		首标签和尾标签分别位于网页文件的最前面和最后面。
		文件的所有HTML标签和文件都包含在其中。
	<head>:表示网页的头部标签。包含网页的标题、编码方式等信息。
		 包含<meta>、<title>等标签
		 <meta>:  (metaverse 元宇宙)定义网页的元数据
			位于head标签内部，不包含任何内容。没有结束标签。
			为了正确显示网页，浏览器必须知道要使用那个字符集。
			我们通常使用utf-8、gb2312(简体中文)表达中文字符。
			<meta charset="utf-8">
			character 字符 + set 设置 = charset
		 <title>:定义文档的标题
			title标签的内容出现在浏览器窗口
			对于所有的网页都必需的
			当把网页加入收藏夹或者书签时，标题成为默认名称。
	<body>:定义网页文档的主体
			被浏览器显示在屏幕上
			1、body元素包含文档的所有内容（比如文本、超链接、图像、表格和列表等等。）
			2、拥有一个开始标签<body>，以及一个结束标签</body>
			// 属性：bgcolor		
	//作业
```
	<!DOCTYPE html>
	<html>
		<head>
			<meta charset="utf-8">
			<title>我的第一个HTML文档</title>
		</head>
		<body>
			Hello World!
		</body>
	</html>
```
	标题(Heading)：<h1> - <h6>，从大到小，<h1>最大
		属性：align(对齐方式) :left center right
	//作业
	段落(paragraph)：<p>
		属性：align(对齐方式) :left center right
			 title：设置工具提示 
			 style： 设置行内样式: style="color:red"
	//作业 
	换行：<br />
	//作业
	
	文字标签：<font> 
		属性：color 颜色  face 字体  size大小
	
	水平标签（分割线、水平线）：<hr 属性名称=“属性值” />
		属性：width 宽(单位：px或者百分比)  
			 size 大小、尺寸 (单位：px)
			 color 颜色 
			 align 对齐方式: left center right
			 noshade 去掉阴影: noshade="noshade"	
	//作业
	
	强调标签：<b> 或者 <strong>
	
	图片标签(image)：<img />、空标签
		属性： 
			必须：  src（source 来源 ）路径 
				   alt（alternate 备用的）提示信息（图片不显示的时候展示出来）
```
	<img src="boy.jpg" alt="现在你看不到图片啦，哈哈哈" />
```	
			非必须：
				width 宽  height 高  border 边框
				align   相对于周围文本的对齐方式
						left	把图像对齐到左边
						right	把图像对齐到右边
						middle(中间)	把图像对齐到中间
						top(顶部)	 	把图像对齐到顶部
						bottom(底部)	把图像对齐到底部
	超链接: <a>
	//	<a target="_blank" href="作业1.html"> 点击跳转到刚才的作业 </a>
		属性： href: 跳转目标的URL
			  target :在何处打开URL
					默认值：_self  在自己页面打开
					可选值：_blank 在新页面打开
	//第一章结束-作业
	
	空格： &nbsp;
	
	居中标签：<center>
	
	音频标签：<audio>
		IE8以及之前的浏览器版本不支持<audio>标签。
		属性： 
			必须的： src  音频路径
						相对路径 (./同一级  下一级/  上一级../)
						绝对路径 
					controls 播放控件
			
			非必须： autoplay 自动播放  loop 循环播放
	
	第一种语法（单一音频来源）：
```
	<audio src="音频/海阔天空.mp3" controls="controls" > 你的浏览器不支持audio! </audio>
```
	第二种语法（多个音频来源）：
		<source src="xxx" />   , 默认播放第一个支持的音频。
```
	<audio controls="controls" >
		<source src="音频/光辉岁月.mp3" type="audio/mp3" />
		<source src="音频/海阔天空.wav" type="audio/wav" />
		你的浏览器不支持audio
	</audio>
```
	视频标签：<video> 
		IE8以及之前的浏览器版本不支持<video>标签。
		属性： 
			必须的： src  视频路径
					controls 播放控件
			
			非必须： poster 视频加载时显示的图像（视频封面图像）
					width 宽 height 高 (单位 px)
					autoplay 自动播放  loop 循环播放
	第一种语法（单一音频来源）：
```
	<video width="800px"  poster="images/girl.jpg" src="视频/测试视频.mp4" controls="controls" > 你的浏览器不支持播放！ </video>
```
	第二种语法（多个视频来源）：
		<source src="xxx" />  , 默认播放第一个支持的视频。
```
		<video controls="controls">
			<source src="视频/黄家驹.ogg" type="video/ogg" />
			<source src="视频/测试视频.mp4" type="video/mp4" />  
			你的浏览器不支持！
		</video>
			
```
			
	列表标签：ordered 有序的  unordered 无序的   list 列表
		无序列表（unordered list 简写）：<ul> 
					列表项：<li>
			属性：type 用于设置列表项开始的符号 
					取值： 默认：disc 实心圆、 circle空心圆、square 正方形
```
	<ul type="square">
		<li>第一项</li>
		<li>第二项</li>
		<li>第三项</li>
	</ul>
```
	有序列表(ordered list 简写)：<ol>
			列表项：<li> 
		属性：
			type 用于设置列表项开始的符号 
				取值： 默认1、a、A, i, I
			start 序号起始值
```
	<ol type="设置列表项开始的符号" start="序号起始值">
		<li>妲己</li>
		<li>澜</li>
		<li>镜</li>
		<li>庄周</li>
	</ol>
```
	自定义列表(definition list 简写)：<dl> 、
				<dt>  (“definition title”，定义标题)
				<dd> (“definition description”，定义描述)
```
	<dl>
		<dt> 标题1 </dt> <dd> 注释1 </dd>  <dd> 注释2 </dd>  <dd> 注释3 </dd>
		<dt> 标题2 </dt> <dd> 注释2</dd>
		<dt> 标题3 </dt> <dd> 注释3</dd>
		<dt> 标题4 </dt> <dd> 注释4</dd>
	</dl>
```	
			
div标签： <div></div>
	1、没有特定的含义，只是作为组合其他 HTML 元素的容器，
	2、默认情况下独占一行（当存在多个div标签时，从上到下的方式排列）
	3、如果与 CSS 一同使用，<div> 元素可用于对大的内容块设置样式属性。
	4、<div> 元素的另一个常见的用途是文档布局。它取代了使用表格定义布局的老式方法。使用 <table> 元素进行文档布局不是表格的正确用法。
	5、可以用 id 或 class 来标记 <div> （页面中每个标签的id不能相同,class可以相同）

<span>标签： span (跨度、范围)
	1、没有特定含义，作为文本的容器
	2、多个span标签可以存在于同一行（从左到右的方式排列）
	3、如果与 CSS 一同使用，<span> 元素可用于内容块设置样式属性。

表格标签：<table></table>  
	主要由表格标签<table>、行标签<tr> (table row行)、单元格<td>标签构成。
	<table>属性： border 边框大小（单位px）
			width 宽 （单位px 或者屏幕的百分比） height (单位px)
			bgcolor (background color简写) 背景颜色
			background 背景图片
			align 对齐方式（表格相对屏幕）
			cellspacing (cell单元 spacing间距)  单元格间距
			cellpadding (cell单元 padding填充、内衬)  单元格填充
			
	<td>属性： rowspan 跨行(row span)   colspan 跨列(column span)
			width 宽 （单位px） bgcolor (background color简写) 背景颜色
			align 对齐方式 （内容相对单元格）
		布局：<td>里面可包含table
		
	表格<table>中的其他标签：
		<caption> 表格标题  （caption 说明文字）
		<th> 定义表头

表单标签: <form> </form>
	必须属性：name 表单名称  
			 action 提交url  
			 method 提交方式, 通常可选get、post, 默认get
				 get、post的主要区别:
					安全性： get方式提交的表单信息会出现在地址栏（参数附加在url后面）。
							但是post方式提交的不会
					提交数据的长度：get方式提交的数据有长度限制。
								  post方式提交的数据没有长度限制（文件上传建议使用post）
```
	<form name="表单名称" action="提交的url" method="提交方式">
		表单元素
	</form>
```

表单元素概述：
	大部分使用input标签，只是属性不同:
		<input>属性:name 表单元素名称
					type 类型：默认text， password checkbox radio submit reset file hidden image button 
					 value 初始值
					 size 指定表单元素的初始宽度。
					 placeholder 输入框的提示文本
					maxlength 输入的最大长度，默认无限制
					checked 是否选中
					readonly  不能更改
```
	<input name="表单元素名称" type="类型" value="初始值" size="显示宽带" maxlength="能输入的最大字符长度" checked="是否选中" >
```
	表单常用控件标签写法：
		单行文本输入框： <input type="text">
		单选框：<input type="radio">
		复选框：<input type="checkbox">
		密码输入框：<input type="password">
		提交按钮： <input type="submit">
		下拉选框: <select>
		多行文本输入框： <textarea>
		
输入框：
	单行文本框：
```
	<input type="text" name="text_show" id="text_show" value="这是初始值" >
```
	密码框：
```
	<input type="password" name="password" id="password">
```
	单行文本域：<textarea>
		属性：cols 设置默认列数  rows 默认行数 
```
	<textarea cols="100" rows="30" name="textarea"> 
		这是多行文本框
	</textarea>
```

按钮：分为提交按钮、重置按钮、普通按钮
	属性：disabled="disabled" 禁用按钮
	提交按钮：用于提交表单数据
```
	<input type="submit" name="submit" value="点击提交到后台">
```
	重置按钮：清空现有表单数据
```
	<input type="reset" name="reset" value="点击清空表单数据" >
```
	普通按钮：一般用于调用JavaScript脚本, value初始值
```
	<input type="button" value="点击查看协议" name="button">
```
	图片按钮：（提交按钮）
```
	<input type="image" src="xiaozhan.jpg" alt="这是肖战" name="imageSubmit" height="50px" >
```
	
单选：1、type="radio"  2、同一组单选有相同的name 3、value值
	默认选中：checked="checked"
```
	未知 <input   type="radio" name="gender" value="unknown">
	男 <input   checked="checked" type="radio" name="gender" value="boy" >
	女 <input  type="radio" name="gender" value="girl">
			
```
多选： 将单选的radio改成checkbox
	默认选中：checked="checked" 
```
	<input type="checkbox" name="fruit" value="apple">苹果
	<input type="checkbox" name="fruit" value="orange">橘子
	<input type="checkbox" name="fruit" value="banana">香蕉
```
下拉选框：<select> </select>
	属性：size 默认显示的行数   多选：multiple="multiple"
	默认选中：selected="selected"
```
	<select name="chongqing_snack" >
		<option value="-1">--请选择你喜欢的重庆小吃--</option>
		<option value="hotpot"> 火锅 </option>
		<option value="zhacai"> 榨菜 </option>
		<option value="small_noodle"> 小面 </option>
	</select>
```

## 表单验证：
	必填验证：required
```
	<input required="required" type="text" name="account">
```
	类型匹配验证：email(邮箱) url（网址） number（数字） range  date(日期)
		email类型：type="email"
```
	<input type="email" name="email">
```
		url类型：type="url"
```
		<input type="url" name="url_validate">
```
		number类型： type="number"
```
	<input type="number" name="number_validate">
```	
		date类型：type="date"
```
		<input type="date" name="date_validate">
```	
		range类型：滑动条  min（最小值） max(最大值) step（步长）
```
	<input type="range" step="10" min="10" max="200" name="range">
```
		控制字符数量：maxlength="最大长度"
```
	<input maxlength="6" required="required" type="text" name="account">
```
		输入范围：min（最小值） max(最大值) step（步长）
```
	<input type="number" step="10" min="0" max="100" name="age">
```
		自定义错误消息：
			输入不合法的时候提示消息：oninvalid="setCustomValidity('自定义错误消息')"
```
	<input oninvalid="setCustomValidity('亲爱的,你的年龄不建议浏览此网址哦!')" type="number" min="18" max="60" name="age">
```
		    正常输入的时候：oninput="setCustomValidity('自定义消息')"
```
	<input oninput="setCustomValidity('')" oninvalid="setCustomValidity('亲爱的,你的年龄不建议浏览此网址哦!')" type="number" min="18" max="60" name="age">
```


CSS: 样式表, CSS3
	优势：1 丰富的修饰样式
		 2 内容与修饰分离
		 3 样式复用
		 4 页面精确控制
	
	语法： 选择器 属性 属性值
		<style>
			选择器 {
				属性1:属性值1;
				属性2:属性值2;
				...
			}
		</style>
```
<style>
	li {
		color:red;
		font-size:20px;
		font-family:隶书;
	}
</style>
```
		语法规则： 1 不区分大小写，推荐使用小写
				  2 每条样式用英文分号";"隔开
				  3 注释 Ctrl + /
	
		样式表分类： 根据书写位置，可分为行内样式表、内嵌（内部）样式表、外部样式表(推荐使用)

		行内样式表：对单独的标签有效
			在标签里面加入style属性
			<标签 style="属性1:属性值1;">  </标签>
```
	<p style="color:red;font-size:30px;"> 通过使用CSS来提升工作效率！ </p>
	<hr style="border:2px dashed blue" />
	<p style="color:red;font-size:30px;">开始学习CSS！</p>
```
		内嵌样式表：放在<head>和</head>中，通过<style>标签定义
```
<head>
	<style>
		p {
			color:red;
			font-size:30px;
		}
		hr {
			border:2px dashed blue;
		}
	</style>
</head>
```
		外部样式表：通过link标签建立关联,  或者@import导入（推荐使用）
			<link rel="stylesheet" style="text/css" href="css文件的路径" />
```
	<head>
		<link rel="stylesheet" style="text/css" href="style.css" />
	</head>
```
	或者
```
	<head>	
		<style>
			@import "style.css"
		</style>
	</head>
```

CSS基本选择器：
	分为标签选择器（元素选择器）、类选择器、ID选择器
		<标签名> 标签内容 </标签名>
	标签选择器：标签名 { }
```
	<style>
		li {
			color:blue;
		}
	</style>
```
	类选择器： .类名 { }  类名可以重复
		<标签名 class="类名"> 标签内容 </标签名>
```
	<style>
		.red {
				color:red;
			}
	</style>
```
	ID选择器： #ID名 { }  ID名不能重复(唯一)
		<标签名 id="id名"> 标签内容 </标签名>
```
	<style>
		#middle {
					background-color:pink;
				}
		
		#save {
				color: green;
				font-size:50px;
			}
	</style>
```
扩展选择器：包括组合选择器，包含选择器，交集选择器，伪类选择器
	组合选择器（并集选择器）：多个选择器用英文逗号","连接, 同时生效
```
	h1,.span,#save {
						color:red;
						font-size:30px;
					}
```
	包含选择器（后代选择器）：多个选择器用空格" "连接, 对子标签生效
		用于选择后代元素（外层标签称为父标签，内层的标签称为子标签。）
```
	#header ul li a {
						color:red;
					}
```
	交集选择器：由两个选择器构成，第一个必须是标签选择器，第二个必须是类选择器或者ID选择器。
		   必须连续书写。
		   p.class { }
		   h1#id { }
```
	p.p1 {
		color:pink;
	}
```
	伪类选择器：根据标签的状态来修饰样式
```
		<style>
			/* 未单击,默认 */
			a:link{
				color: red;
			}
			/* 单击后 */
			a:visited {
				color:pink;
			}
			/* 鼠标悬浮 */
			a:hover {
				color: chocolate;
				font-size: 30px;
			}
			/* 单击未释放 */
			a:active {
				color: aqua;
			}
		</style>
	```
	
	CSS的特性： 1继承性 2层叠性和优先级
		继承性：内层继承外层，内层另行更改除外。
			   特殊情况不继承，比如边框border
			   
		层叠性和优先级:
				1 如果多个选择器定义的样式不发生冲突，则应用所有选择器定义的样式。
				2 如果多个选择器定义的样式发生冲突,则按照选择器的优先级来处理。
			优先级总原则： 越特殊的样式，优先级越高。
			选择器的优先级：ID选择器 > 类选择器 > 标签选择器(元素选择器)
			样式表的优先级：行内样式表 > 内嵌样式表 > 外部样式表
			
常用的样式属性
	字体与文本属性
		1字体属性 
			font-weight 字体加粗： bold加粗
			font-size 字体大小 
			font-family 字体类型 
			color  字体颜色,取值可以是英文单词，也可以是十六进制符号#000000 - #FFFFFF
```
	p {
		font-weight:bold;
		font-size:30px;
		font-family:华文彩云;
		color:blue;
	}
```
		font 设置字体的所有样式 (注意顺序)
```
	font:bold 30px 华文彩云;
```

		2文本属性
			line-height 设置行高
			text-align  对齐方式: left center right
			letter-spacing 字符间距 
			text-decoration 文本修饰: underline（下划线） none(没有) overline line-through
```
	<style>
		#big {
			background-color:pink;
			line-height:100px;
			text-align:center;
			letter-spacing:10px;
			text-decoration:underline;
			/* height:100px; */
		}
	</style>
```
	
	边距和填充：1 边距（外边距、margin），围绕在元素边框的空白区域
			  2 填充(内边距、补白、padding)，定义元素边框与元素内容之间的空白区域。
		边距：
		单独设置边距：
			margin-top 上边距
			margin-left 左边距
			margin-bottom 下边距
			margin-right 右边距
```
	margin-top:20px;
	margin-left:30px;
	margin-right:40px;
	margin-bottom:50px;
```
		通过复合属性设置边距：
		仅设置一个值，则应用四个边距
```
		margin:20px;
```
		设置两个值，则表示上下边距、左右边距
```
		margin:30px 60px;
```
	设置三个值，则表示上边距、左右边距、下边距
```
		margin:30px 60px 90px;
```
	设置四个值，则表示上边距、右边距、下边距、左边距 (顺时针)
```
		margin:30px 60px 90px 120px;
```
	
	填充（padding）：定义元素边框与元素内容之间的空白区域。
		单独设置填充：
			padding-top 上填充
			padding-left 左填充
			padding-bottom 下填充
			padding-right 右填充
```
	padding-top:20px;
	padding-left:30px;
	padding-right:40px;
	padding-bottom:50px;
```
		通过复合属性设置填充：
		仅设置一个值，则应用四个填充
```
		padding:20px;
```
		设置两个值，则表示上下填充、左右填充
```
		padding:30px 60px;
```
		设置三个值，则表示上填充、左右填充、下填充
```
		padding:30px 60px 90px;
```
		设置四个值，则表示上填充、右填充、下填充、左填充 (顺时针)
```
		padding:30px 60px 90px 120px;
```
		边框属性：1 border属性 2 border-radius属性
			1 border属性
			单独设置：
				border-style 边框样式：solid实线 dashed虚线 none无 double
				border-width 边框宽度
				border-color 边框颜色
```
	border-style:solid;
	border-width:20px;
	border-color:green;
```
			通过复合属性设置边框：
```
	border:15px solid pink;
```
		2 border-radius属性，设置边框圆角
			border-radius:半径像素值。半径像素值越大，圆角越明显
		border-radius:参数1 ,四个角
```
	border-radius:100px;
```
		border-radius:参数1 参数2,参数1对应左上角右下角，参数2对应右上角左下角
```
	border-radius:50px 100px;
```
		border-radius:参数1 参数2 参数3,参数1对应左上角，参数2对应右上角左下角,参数3右下角
```
	border-radius:50px 100px 150px;
```
	border-radius:参数1 参数2 参数3 参数4, 顺时针
```
	border-radius:50px 100px 150px 100px;
```
	
	列表属性：
		list-style-type 列表项符号：none无 disc实心圆 circle空心圆 square实心正方形
		list-style-image  设置图片作为列表项的符号: url(图片路径)
		list-style-position 设置项目符号在列表项的位置: inside outside(默认)
```
<style>
	ul {
		/* list-style-type:none; */
		list-style-image:url(images/arrow.png);
		list-style-position:inside;
	}
	li {
		border:2px red solid;
	}
</style>
```
		通过复合属性设置列表项：
```
	list-style:circle inside url(images/arrow.png);
```
背景和阴影
	背景属性：1背景颜色 2背景图片 3背景图片的重复方式
		background-color 设置背景颜色
			颜色:英文单词、 16进制、 rgb(red, green, blue)
```
	background-color:blue;
```
		background-image 设置背景图片: url(图片地址)
				如果同时存在背景图片和背景颜色，优先显示背景图片
```
	background-color:rgb(255, 254, 66);
	background-image:url(images/shrimp_2.jpg)
```	
		background-repeat 设置背景图片的平铺方式：
			repeat(默认)全部平铺 ，默认repeat, no-repeat不平铺,repeat-x横向平铺 repeat-y纵向平铺
```
	/* background-color:blue; */
	background-image:url(images/shrimp_2.jpg);
	background-repeat:repeat-y;
```
	多张背景图片：
```
		background-image:url(images/aa.jpg),url(images/girl.jpg);
		background-repeat:repeat-y, no-repeat;
```

	背景图片的定位：1 background-position属性  2 CSS Sprites
			background-position:关键字 百分比 像素值
			关键字：水平方向left center right, 垂直方向top center bottom

			百分比：水平方向：常用0% 50% 100%表示左中右，垂直方向：常用0% 50% 100%表示上中下
			
			像素值：背景图片左顶点相对于上级元素左顶点的偏移量。
				当为正数时，水平向右，垂直向下。
				当为负数时，水平向左，垂直向上。
```
	#content {
		border:2px solid red;
		width:900px;
		height:700px;
		/* background-color:blue; */
		background-image:url(images/shrimp_2.jpg);
		background-repeat:no-repeat;
		/* background-position:left top; */
		/* background-position:100% 0%; */
		background-position:-100px -50px;
	}
```
		设置多个背景图片属性
```
	<style>
		div {
			border:2px solid red;
			width:900px;
			height:900px;
			background-image:url(images/p1.png),url(images/p2.png),url(images/p3.png),url(images/p4.png);
			background-repeat:no-repeat;
			background-position:center center,right bottom,left center,200px -50px;
		}
	</style>
```
	
	CSS Sprites（雪碧图，精灵图）
```
	#second {
		background-position:0px -26px;
	}
	#third {
		background-position:0px -52px;
	}
```
	背景的渐变：1线性渐变 2径向渐变
	1线性渐变 
		background:linear-gradient(参数1（角度或者方向），参数2（颜色），参数3（颜色）.。。)
			参数1的角度是指渐变线与水平线之间的角度。
```
	background:linear-gradient(45deg,red,pink,blue);
	background:linear-gradient(to right,red,blue);
	background:linear-gradient(to right bottom,red 40%,white,black)
```
	透明度渐变
	rgb(red,green,blue)设置颜色, red green blue取值0-255或者百分比
	rgba(red,green,blue,alpha(透明度) ),设置颜色并使用透明度,alpha取值0-1
```
	background:linear-gradient(to right,rgba(255, 255, 255, 0),rgba(255, 255, 255, 0.6)),url(images/aa.jpg);
```
	重复线性渐变 
		background: repeating-linear-gradient(参数1（角度或者方向），参数2（颜色），参数3（颜色）.。。)
```
	background:repeating-linear-gradient(45deg,red,blue 30px);
```
	
	2径向渐变
		background:radial-gradient(参数1（形状或者圆心位置），参数2（颜色），参数3（颜色）。。)
```
	background:radial-gradient(circle,black,white 20px)
```
	重复径向渐变：
```
	background:repeating-radial-gradient(ellipse,black,white 20px)
```
	阴影属性：1文字阴影 2盒子阴影
	1文字阴影 
		text-shadow:h-shadow水平距离（必须） v-shadow垂直距离（必须） blur模糊半径 color阴影颜色
```
	text-shadow:10px 10px 5px blue;
```
	2盒子阴影
		box-shadow:h-shadow水平距离（必须） v-shadow垂直距离（必须） blur模糊半径 spread阴影大小 color阴影颜色
```
	box-shadow:10px 10px 15px 5px blue;
```

盒子模型：1盒子模型原理 2标准文档流 3盒子浮动 4盒子定位
		盒子模型原理
			1盒子模型概述:每个HTML元素都可以看作一个盒子。包含内容content 填充padding 边框border 边距(边界)margin
				（填充 边框 边距包含top上、bottom下、left左、right右四部分)
			 
			2盒子大小
			  盒子实际大小（不算边距）
					盒子实际宽度：左边框+左填充+内容宽度+右填充+右边框 （不算边距）
					盒子实际高度：上边框+上填充+内容高度+下填充+下边框 （不算边距）
					
			  盒子占据空间大小: 盒子实际大小+边距
					盒子占据宽度：盒子实际宽+左边距+右边距
					盒子占据高度：盒子实际高+上边距+下边距
```
	<div id="content">
		内容宽度：300px  <br />
		内容高度：500px <br />
		
		边框宽度：15px <br />
		
		左右填充：40px <br />
		上下填充：20px <br />
		
		左右边距：40px <br />
		上下边距：30px <br /><br />
		
		盒子实际宽度：15px+40px+300px+40px+15px=410px <br /><br />
		盒子实际高度：15px+15px+20px+20px+500px=570px <br /><br />
		
		盒子占据宽度：410px+40px+40px=490px <br /><br />
		
		盒子占据高度：570px+30px+30px=630px <br /><br />
		
	</div>
```
		3盒子之间的关系
			垂直盒子：取margin-bottom和margin-top的较大值
			水平盒子：取margin-right和margin-left之和
			重叠盒子：margin设置为负数。但是border、padding只能取正数
```
	margin-left:-50px;
```

	2标准文档流（普通流、标准流）
		1概述：浏览器根据从左到右，自上而下的规则排列HTML元素
			块元素：标题(<h1> - <h6>) 段落(<p>) 水平线(<hr />) 列表(<ul>、<ol>、<li>等) 表格(<table>) 层（<div>）表单(<form>)
			行元素：图片(<img>) 范围（<span>） 换行(<br />)  超链接(<a>)
			块元素和行元素的区别：
				1排列方式不同
					块元素从上而下排列。
					行元素从左到右排列，多个行元素可显示在同一行。
				2内嵌元素不同
					块元素可以包含块元素和行元素。
					但是行元素只能包含文本或者行元素。
				3属性设置不同
					块元素可以设置所有样式属性
					行元素不能设置width和height，也不能设置上下边距，上下填充，但是可以设置line-height
					
		2display属性: display:none|block;
			控制是否存在。 隐藏该元素，不占屏幕空间。 若有其他元素，会上移到该区域。
```
	display:none;
```
		3visibility属性: visibility:hidden | visible;
			控制是否显示。隐藏但是占据屏幕空间。
```
	visibility:hidden;			
```  
	  
	  3盒子浮动 
		1 float属性
			float:none | left | right
				left 向上级元素左边浮动
				right 向上级元素右边浮动
				none 默认，不浮动
```
	float: left;
```			
		2 清除浮动
			浮动副作用
				背景不能撑开
				边框不能撑开
				margin padding不能正常设置
				
			清除浮动影响的方法：	
			1 对父级设置宽高属性
```
	#max {
			width: 1000px;
			height: 300px; 
		}
```			
			2 clear:both清除浮动
				在父级"</div>"结束前加上<div class="clear"> </div>
```
	.clear {
		clear: both;
	}
```
			3 在父级定义overflow:hidden
```
	overflow:hidden; 
```
	  
	4盒子定位
		1 静态定位
			默认，按照标准文档流，HTML元素从左到右，自上而下排列。
```
	position: static;
```
		2 相对定位
			从原来的位置移动到一个相对位置。参考点：左顶点
			占据原来的空间。
```
	position: relative;
	top:100px;
	left:100px;
```
		3 固定定位
			相对于浏览器窗口定位。
```
	position:fixed;
	top:200px;
	left:200px;
```
		4 绝对定位
			脱离文档标准流。不占据空间。可以将指定标签放到任意绝对坐标位置。
```
	position:absolute;
	top:200px;
	left:200px;
```	
		5 z-index属性，设置元素堆叠顺序
			必须先设置定位。
			z-index:数字; 数字越大，越靠前