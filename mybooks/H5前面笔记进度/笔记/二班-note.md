网页设计（前端、front end）
张卫 thinkzw@foxmail.com
电商+金融+ERP、OA+仿抖音微信小红书

上网方式（客户端）：
	电脑端：网页
	移动端：网页+APP+小程序

主要解决：用户体验的问题

必备条件：
	1、会上网、会打字、基础英语
	2、兴趣
	3、肯做练习、耐心

具体学习哪些东西：
	1、软件 5%
		1、浏览器内核分类（谷歌浏览器、火狐浏览器、IE浏览器、苹果浏览器）
		2、浏览器开发者工具：F12 （或者Fn + F12）
		3、编辑器：记事本、DreamWeaver(DW、梦想编织者)、Hbuilder、Sublime、VS code
		了解前端三剑客：FireWorks(PhotoShop)、Flash(Animate)
	2、语言 95%以上
		HTML
		CSS
		JavaScript

什么是互联网？
	WWW（World wide web, 万维网）
		3个基本组成部分：
		URL： 朋友地址 www.baidu.com
		HTTP(三次握手): 协议  http://
		HTML: 网页内容

web标准：
	W3C（万维网联盟），不是某一个标准，它是一系列标准的集合。
	web标准分为三个标准：
	1、结构化标准		网页结构（Structure）  		对应HTML
	2、表现标准		网页样式（表现Presentation）   对应CSS
	3、行为标准		网页行为（Behavior） 			对应JavaScript

HTML：
	1、用来描述网页的一种语言
	2、不是一种编程语言，但是它是一种标记语言
	3、标记语言是一套标记标签

HTML文档
	1、 = 网页
	2、包含HTML标签和纯文本

网页：
	1、扩展名：.html或者.htm
	2、必须通过浏览器来阅读
	3、网页内容包括：文字、图片、音频、视频、动画、特效等

4、网页编辑器
	1，记事本
	2、DreamWeaver（DW）：（所见即所得）
		1、下载 （中文破解版）
		2、安装
		3、使用
			界面：菜单栏、属性栏、面板组、插入栏、编辑窗口
			新建站点（项目）：菜单栏-站点-新建-输入名称、输入路径
			编辑站点：菜单栏-站点-管理站点-点编辑
			新建网页：
				1、菜单栏-文件-新建-选择html-输入名称、路径
				2、点击站点-新建文件-输入名称
				3、快捷键：Ctrl+N - 输入网页标题
			新建目录：左键点击选中站点（或者父级文件夹）- 右键-新建文件夹-输入名称
	3、Hbuilder
		下载：官网下载
		安装：
		使用：
			新建站点（项目）：	
				1、菜单栏文件-新建-项目-输入项目名称、项目路径	
				2、左边项目窗口右键-新建-项目-输入项目名称、项目路径	
				3、快捷键：Ctrl+N
			新建网页：（注意路径）
				1、菜单栏文件-新建- HTML文件-输入网页名称、网页路径	
				2、左边项目窗口右键-新建-项目-输入网页名称、网页路径	
				3、快捷键：Ctrl+N
			新建目录：（注意路径）
				1、菜单栏文件-新建-目录-输入名称、路径	
				2、左键选择上级目录-右键-输入名称
				3、左键选择上级目录-快捷键：Ctrl+N

HTML标签
	doctype:（document type） 声明文档类型
	html:最先出现和最后出现的标签、成对出现
		首标签<html> 尾标签</html>
		网页的所有文件和标签都包含在其中
	head:网页头部标签
		包含：文件标题、编码方式、URL等信息
		以下标签都包含在里面：<title>、<meta>、<script>、<style>、<base>等
		title:定义文档标题
			出现在浏览器窗口
			所有的html文档必需的
		meta: (元宇宙 metaverse)定义网页的元数据
			// <meta charset="utf-8"/>
		style:定义文档样式信息
	body:网页文档主体内容
		这些内容被显示在屏幕上


快捷键：
	搜索：Ctrl + F (Find)
	复制行或选区：ctrl+insert
	格式化代码：Ctrl+K 
	浏览器运行：Ctrl + R （run）
	注释：ctrl+/
	向下插入行：Ctrl+enter
	向上插入行：Ctrl+shift+enter

举例演示：4个标签
	1、标题(Heading): <h1> - <h6> 从大到小，h1最大
	2、段落(paragraph): <p> 
	3、超链接：<a>
	4、图片(imgae)：<img> 
	
HTML标签(HTML tag):
	1 由尖括号包围的关键词，比如<html>
	2 通常是成对出现，比如<p>这是一个段落</p>，<title>这是标题</title>
	3 标签对中的第一个标签是开始标签（开放标签），第二个标签是结束标签（闭合标签）

空标签： 比如<hr />、	<br />	
	1 没有内容
	2 没有结束标签
	3 在开始标签中关闭

HTML属性：
	1 为HTML元素提供附加信息。
	2 总是以名称/值对的形式出现。比如： name = "value"
	3 总是在开始标签中规定
		比如可能有以下属性： align对齐方式 face字体 size大小 color颜色 width宽 height高。。
	4 适用于大多数HTML元素的属性：
		style: 设置元素的样式（CSS）
			比如设置颜色、宽度、高度等：style="color:red;width:200px;height:100px;" 
		title：规定元素的额外信息（可在工具提示中显示）

注意：
	1 所有的代码都要用英文状态 
	2 不要忘记结束标签（空标签也有结束"/"）
		即使忘记结束标签，大多数浏览器也会正确显示。	
	3 推荐使用小写标签
		HTML对大小写不敏感：<P> 等同于 <p>
		
HTML注释:
	1、可以将注释插入HTML代码中，提高代码可读性，更容易理解。
	2、 浏览器会忽略注释，也不会显示出来。
	3、 <!-- 这是注释 --> 或者Ctrl+/

学习标签：
	<!DOCTYPE>声明:帮助浏览器正确的显示网页。
		document type（文档类型）的简写
		位于网页文档第一行
		不是HTML标签，没有结束标签，对大小写不敏感。
		
	<html>: 告诉浏览器自身是一个HTML文档
		最先出现的标签，成对出现
	
	<head>:表示网页的头部标签。包含网页的标题、编码方式等信息。
		包含：<title>、<meta>、<script>、<style>等标签。
		<meta>:提供网页的元信息(meta-information)
			<meta>标签位于head元素内部，不包含任何内容。
			为了正确的显示网页，浏览器必须要知道使用哪个字符集。
			我们通常使用utf-8、gb2312（中文简体）字符集表达中文字符。
			character 字符集 + set 设置 = charset 
```
	<head>
		<meta charset="utf-8">
	</head>
```
		<title>:定义文档的标题
			title标签的内容出现在浏览器窗口
			所有的网页都必须要有title标签。
	<body>:
		1 定义网页文档的主体内容
		2 被浏览器显示在屏幕上
		
	标题(Heading)：<h1> - <h6>,从大到小，<h1>最大
		属性：align 对齐方式 ：居中 center  左边 left 右边 right
	
	段落(paragraph): <p>
		属性：align 对齐方式 ：居中 center  左边 left 右边 right
			title 设置工具提示
			style（样式） ： 比如文字变灰色：style="color:grey"
	换行：<br />

	水平标签（水平线、分割线）: <hr />
		属性：  width 宽度(单位px或者百分比)  粗细 size  颜色color 对齐方式align(left,center,right)  noshade 去掉阴影(shade)
	
	文字标签：<font>
		属性： 字体face  颜色color 字体大小size

	强调标签（加粗）: <b>  或者 <strong>

	文本居中：<center>
	
	空格：&nbsp;

	图片标签(image)：<img /> 空标签
		属性：
			必须：src (source 来源) 路径:
					相对路径(相对当前文件)：./ 同一级 ../上一级 ../../上两级，比如：./boy.jpg
					绝对路径（与当前文件无关）: 比如： https://www.xxx.com/xxx.jpg
				alt (alternate 备用的 ) 提示信息（图片不显示的时候才显示）
			非必须：width 宽  height 高 border 边框 (单位px)
			   align     相对于周围文本的对齐方式
					left		把图像对齐到左边
					right		把图像对齐到右边
					middle(中间)	把图像对齐到中间
					top(顶端)	把图像对齐到顶部
					bottom(底部)	把图像对齐到底部

### 超链接: <a> 
	属性： href: 跳转目标的URL
	    target :在何处打开URL
			默认值：_self  在自己页面打开
			可选值：_blank 在新页面打开
```
	<a target="_blank" href="作业1.html"> 点击跳转到刚才的作业 </a>
```
//第一章结束-作业
	
### 音频标签： &lt;audio> &lt;/audio>
	IE8以及之前的版本不支持<audio>标签
	属性： 
		必须的：  
				src  音频路径 
					相对路径（同一级./ 上一级../ 下一级/）
					绝对路径 
				controls 播放控件
		非必须的：autoplay 自动播放

	第一种语法(单个音频来源)：
```
	<audio src="音频/海阔天空.mp3" controls="controls" > 你的浏览器不支持audio！ </audio>
```	
	
	第二种语法(多个音频来源)：
		<source> 来源
		有多个音频来源的时候，默认播放第一个支持的音频。
		<!-- 第二种 -->
```
	<audio controls="controls" > 
		<source src="音频/光辉岁月.mp3" type="audio/mp3" />
		<source src="音频/纸短情长.mp3" type="audio/mp3" />
		你的浏览器不支持音频！ 
	</audio>
```
		
### 视频标签：<video> </video>
	IE8以及之前的版本不支持<video>标签
	属性： 
		必须的： src 视频路径
					绝对路径
					相对路径：./ 当前目录  ../ 上级目录 
				controls 显示控件
		非必须： width 宽  height 高  poster 视频加载时显示的图像（视频封面）
	
	有多个视频来源的时候，默认播放第一个支持的视频。
	第一种(单个视频来源):
```
	<video poster="images/libai.jpg" width="500px"  src="视频/海阔天空60秒.mp4" controls="controls" > 你的浏览器不支持video标签！ </video>
```
    第二种(多个视频来源):
		<source> 标签
```
	<video controls="controls">
		<source src="视频/光辉岁月60秒.ogg" />
		<source src="视频/海阔天空60秒.mp4" />
		你的浏览器不支持video! 
	</video>
```
		
### 列表： 
	（ordered 有序的  unordered 无序的   list 列表）
	无序列表(unordered list简写)： <ul>  </ul>
		属性： type 设置列表项开始的符号，取值：默认disc(实心圆)、circle（空心圆）、square(实心正方形)
		列表项 <li> </li>
```html
		<ul type="属性值">
			<li> 第一项 </li>
			<li> 第二项 </li>
			<li> 第三项 </li>
		</ul>
```
	有序列表(ordered list 简写): <ol> </ol>
		属性：type 设置列表项开始的符号，取值：默认1,a,A,i,I
			  start 序号起始值
		列表项 <li> </li>
```
		<ol type="设置列表项开始的符号" start="序号起始值">
			<li> 第一项 </li>
			<li> 第二项 </li>
			<li> 第三项 </li>
		</ol>
```
	自定义列表(definition list简写)：<dl>、<dt>、<dd>
	<dt> (definition title简写，定义标题)
	<dd>（definition description简写，定义描述)
	//todo
```html
	<dl>
		<dt> 标题1 </dt> <dd> 注释1 </dd>
		<dt> 标题2 </dt> <dd> 注释2</dd>
		<dt> 标题3 </dt> <dd> 注释3</dd>
		<dt> 标题4 </dt> <dd> 注释4</dd>
	</dl>
```
	
<div> 标签： division(分开、分界)的简写
	1、没有特定含义，作为组合其它HTML元素的容器
	2、div标签默认独占一行（当存在多个div标签时，按照从上到下排练）
	3、如果与 CSS 一同使用，<div> 元素可用于对大的内容块设置样式属性。
	4、<div> 元素的另一个常见的用途是文档布局。它取代了使用表格定义布局的老式方法。使用 <table> 元素进行文档布局不是表格的正确用法。
	5、可以用 id 或 class 来标记 <div> （页面中每个标签的id不能相同,class可以相同）

<span>标签： span (跨度、范围)
	1、没有特定含义，作为文本的容器
	2、多个span标签可以存在于同一行（从左到右的方式排列）
	3、如果与 CSS 一同使用，<span> 元素可用于内容块设置样式属性。

### 表格标签：<table></table>  
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
		<th> 定义表头 （td改成th 加粗并且居中）

### 表单标签： <form> </form>
	属性：
		必须的：  name :表单名称
				action : 提交的url
				method : 提交方式 默认get，通常可选：get 、post
					get、post方法的主要区别：
						安全性：
							get方式提交时，表单信息会出现在地址栏（提交的参数附加在URL后面）。
							但是post方式不会出现在地址栏。
						提交数据长度：
							get方式提交的数据有长度限制，但是post提交数据没有长度限制（上传文件建议用post）
							
```	
	<form name="表单名称" action="提交的URL" method="get/post" > 
		表单元素
	</form>
```
	
	表单元素介绍：大部分使用<input>标签
		属性介绍：
			type 表单元素的类型,比如text,password,submit,radio,checkbox...
			name 名称
			value 输入框初始值
			size  输入框初始宽度
			maxlength 输入的最大字符串（默认无限制）
			placeholder 提示文字
			checked  是否选中 （默认不选中）
			readonly  不允许更改
```
	<input name="表单元素的名称" type="类型" value="值" size="显示宽度" maxlenth="能输入的最大长度" checked="是否选中" />
```
	<input type="text"> 文本输入框
	<input type="submit" > 提交表单
	<input type="password"> 密码输入框（*******）
	<input type="radio"> 单选框
	<input type="checkbox"> 复选框
	<textarea> 多行文本域
	<select> 下拉选框

### 输入框： 
	文本框：
		<input name="表单元素名称" type="text" value="初始值" id="表单元素名称" >
	密码框：
		<input name="password"  type="password" >
	多行文本域： 
		<textarea rows="行数" cols="列数" name="名称" >文本</textarea> (text area) 
			不能设置初始值value
```
	<textarea cols="100" rows="20" name="remark">
		文本
	</textarea>
```

### 按钮：（分为提交按钮、重置按钮、普通按钮）
	属性： disabled="disabled" （禁用）
	提交按钮：
```
	<input type="submit" name="名称" value="按钮显示的初始值">
```
		图片按钮:type="image" （提交按钮：）
```
		<input width="50" type="image" src="nz.jpg" alt="这是哪吒" name="imageSubmit">
```
	重置按钮:
```
	<input type="reset"  name="名称" value="按钮显示的初始值">
```
	普通按钮：
```
	<input type="button"  name="名称" value="按钮显示的初始值" >
```
	
### 单选、多选、下拉选框
	单选按钮：1、type="radio" 2、同一组单选有相同的name 3value值不能少
		默认选中： checked="checked" 
```
	  男：<input type="radio" name="gender" value="boy">
	  女：<input type="radio" name="gender" value="girl">	 
```
	多选框：将单选的radio改成checkbox
		默认选中： checked="checked" 
```
	易烊千玺：<input type="checkbox" name="star" value="yyqx">
	谷爱零： <input type="checkbox" name="star" value="gal">
```
	下拉选框：<select>
		属性：size 默认显示的行数    multiple="multiple" 下拉变成多选
		默认选中： selected="selected"	
```
	<select name="chongqing_snack" size="1">
		<option>--请选择你的菜--</option>
		<option value="hotpot"> 火锅 </option>
		<option value="small_noodle"> 小面 </option>
		<option value="ciba"  selected="selected"> 糍粑 </option>
		<option valu="meat" > 腊肉 </option>
	</select>
```

表单验证：
	必填验证： required  或者 required="required"
```
	<input required="required" type="text" name="account"> *
```
	类型验证：email（邮箱） url(网址) number(数字) range(范围) date(日期) 
		邮箱类型：
```
	<input type="email" name="email">
```
		url类型：
```
	<input type="url" name="url_validate" >
```
		number类型：
```
	<input type="number" name="number_validate">
```
		date类型：
```	
	<input type="date" name="date_validate">
```
		range类型: 滑动条
			属性： min  max  step
```
	<input type="range" step="5" min="10" max="100" name="range">
```
		控制字符数量: 输入字符的最大长度
			maxlength = "最大长度"
			
		验证输入范围： min（最小值） max（最大值） step（每次增加或者减少的值）
```
	<input type="number" min="10" max="100" step="6">
```
		自定义错误消息：
		   不合法的时候：oninvalid="setCustomValidity('错误提示消息!')"
```
	<input oninvalid="setCustomValidity('亲爱的! 你的账号必须填写哦!')" required="required" type="text" name="account"> *
```
			正常输入的时候：oninput="setCustomValidity('')"
```
	<input oninput="setCustomValidity('')" oninvalid="setCustomValidity('亲!你的年龄过大了,这边不建议你浏览本网站哦!')" type="number" min="1" max="70">
```

CSS3： 样式表
	优势：1 丰富的修饰样式 
		 2 内容与修饰分离
		 3 样式复用 
		 4 页面精确控制
		 
	语法： 选择器  属性  属性值
	
	代码规范：	
		1 不区分大小写，推荐小写
		2 每条样式规则用英文分号;隔开
		3 注释 Ctrl+/
	
	样式表分类：根据书写位置，可以分为外部样式表，内嵌(内部)样式表，行内样式表, 建议使用外部样式表
		行内样式表：（对单独的标签有效）
			通用写法：<标签 style="样式属性:属性值;" > </标签>
```
	<h1 style="color:red;font-family:隶书">
```
		内嵌(内部)样式表：（对当前页面有效）
			 放在<head> </head>中，通过<style>标签定义
			 通用写法：
```
	<head>
		<style type="text/css">
			选择符 {
				样式属性1:属性值1;
				样式属性2:属性值2;
				样式属性3:属性值3;
			}
		</style>
	</head>
```
			外部样式表:通过link标签引入，或者用import 
```
	<link rel="stylesheet" type="text/css" href="css文件路径">
```
	或者
```
	<style>
		@import "css文件路径"
	</style>
```
	
CSS基本选择器： 分为标签选择器（元素选择器）、类选择器、ID选择器
	标签选择器：标签名 {  }
		<标签名>  标签内容  </标签名>
```
	<style style="text/css">
		标签名 {
			属性1: 属性值1;
			属性2: 属性值2;
			......
		}
		
	<style>
```
	类选择器：1 类名可以重复  2 .类名{ }
		<标签名 class="类名">  标签内容  </标签名>
```
	<style style="text/css">
		.类名 {
			属性1: 属性值1;
			属性2: 属性值2;
			......
		}
	<style>
```
	ID选择器： 1 ID属性是HTML的唯一标识，同一页面不能重复。2 #id名{ }
		<标签名 id="id名">  标签内容  </标签名>
```
	<style style="text/css">
		#ID名 {
			属性1: 属性值1;
			属性2: 属性值2;
			......
		}
	<style>
```

CSS扩展选择器：组合选择器，包含选择器，交集选择器，伪类选择器
	组合选择器（并集选择器）：选择器之间用英文逗号",""连接，对所有的选择器生效
```
		p,h2,#span {
						color:red;
					}
```
	包含选择器（后代选择器）：选择器之间用空格" "连接。对最后代的选择器生效
		用于选择后代元素，通常外层的标签为父标签，内层的标签为子标签。
```
	#header ul li a {
						color: gold;
					}
```
	交集选择器: 两个选择器连续书写。第一个选择器必须是标签选择器，第二个必须是类选择器或者id选择器。
```
	p.save {
				color:green;
			}
```
	伪类选择器：根据标签处于某种行为或者状态来修饰样式
		标签名：伪类名 {
			属性:属性值;
		}
```
<style>
	/* 未单击，默认 */
	a:link {
		color:red;
	}
	/* 单击后 */
	a:visited {
		color:grey;
	}
	/* 鼠标悬浮 */
	a:hover {
		color:orange;
		font-size:30px;
	}
	/* 单击未释放 */
	a:active {
		color:pink;
	}
</style>
```

CSS的特性：1 继承性 2 层叠性和优先级
	 继承性：内层继承外层样式,但另行更改除外。
			某些特殊情况不继承，比如边框border
	 层叠性：
			1 如果多个选择器定义的样式不发生冲突，则应用全部选择器定义的样式。
			2 如果多个选择器定义的样式发生冲突，则按照选择器的优先级来处理。
	 优先级：
		优先级的总原则：越特殊的样式，优先级越高。
		选择器的优先级：ID选择器 > 类选择器 > 标签选择器(元素选择器)
		样式表的优先级：  行内样式表 >  内嵌(内部)样式表 > 外部样式表 


常用的样式属性：
	字体与文本属性
		字体属性：
				font-weight 字体粗细, bold 加粗
				font-size   字体大小 
				font-family 字体类型
				color 字体颜色
					取值可以为颜色的英文单词，也可以用十六进制符号#000000 - #FFFFFF之间
```
	p {
		font-weight:bold;
		font-size:30px;
		font-family:宋体;
		color: #ACABAB;
	  } 
```
				font 设置字体的所有样式属性(注意顺序)
```
	p {
		/* 顺序不能变 */
		font: bold  30px 隶书 ;
	}
```

	文本属性：
		line-height 设置行高，通常用来上下居中
		text-align 设置左右对齐方式: left center right
		letter-spacing 字符间距 
		text-decoration 设置文本修饰： underline（下划线） none(没有) overline line-through
```
<style>
	#max {
		background-color:pink;
		line-height:50px;
		/* height:50px; */
		text-align:left;
		letter-spacing:5px;
		text-decoration:underline;
		/* font-style:italic; */
	}
</style>
```

	边距和填充：
		边距（外边距，margin）：围绕在元素边框的空白区域
		单独设置边距：
			margin-top  上边距
			margin-left  左边距
			margin-right  右边距
			margin-bottom  下边距
```
	margin-top:20px;
	margin-left:20px;
	margin-right:30px;
	margin-bottom:40px;
```
		也可以复合属性设置边距：
			仅设置一个值，则应用四个边距。
```
	margin: 30px;	
```
		设置两个值，则表示上下边距、左右边距。
```
	margin:10px 20px;
```
		设置三个值，则表示上边距、左右边距、下边距。
```
	margin:10px 20px 30px;
```
		设置四个值，则表示上边距、右边距、下边距、左边距。(顺时针)
```
	margin:10px 20px 30px 40px;
```

		填充(内边距，补白，padding)：定义元素边框与元素内容之间的空白区域。
			单独设置填充：
				padding-top  上填充
				padding-left  左填充
				padding-right  右填充
				padding-bottom  下填充
```
	padding-top:20px;
	padding-left:30px;
	padding-bottom:40px;
	padding-right:50px;
```

	也可以复合属性设置填充：
			仅设置一个值，则应用四个填充。
```
	padding: 30px;	
```
		设置两个值，则表示上下填充、左右填充。
```
	padding:10px 20px;
```
		设置三个值，则表示上填充、左右填充、下填充。
```
	padding:10px 20px 30px;
```
		设置四个值，则表示上填充、右填充、下填充、左填充。(顺时针)
```
	padding:10px 20px 30px 40px;
```
	
	边框属性：1 border属性 2 border-radius属性
		1 border属性
		单独设置边框样式：
			border-style 边框样式: solid实线 dashed虚线 none无 double
			boder-width 边框宽度 
			border-color 边框颜色
```
	border-style:solid;
	border-width:20px;
	border-color:green;
```
			也可以通过复合属性设置边框样式：
```
		border:10px red dashed ;
```

		2 border-radius属性，设置边框圆角
				border-radius:半径像素值。半径像素值越大，圆角效果越明显。
		border-radius:参数1，四个角
```
	border-radius:55px;
```	
		border-radius:参数1 参数2，参数1左上角右下角，参数2左下角右上角
```
border-radius:20px 40px;
```
		border-radius:参数1 参数2 参数3，参数1左上角，参数2左下角右上角, 参数3右下角
```
border-radius:20px 40px 60px;
```
	border-radius:参数1 参数2 参数3 参数4，参数1左上角，参数2右上角, 参数3右下角，参数4左下角（顺时针）
```
	border-radius:20px 40px 60px 80px;
```
	
	列表属性：
		list-style-type 列表项的符号：none无 disc实心圆 circle空心圆 square实心正方形
		list-style-image 设定图片作为列表项的符号：url(图片路径)
		list-style-position 项目符号在列表项的位置：inside outside（默认）
```
ul {
		/* list-style-type:circle; */
		list-style-image: url(images/arrow.png);
		list-style-position:inside;
	}
```
	通过复合属性设置列表项：
```
	list-style:circle inside url(images/arrow.png);
```
背景和阴影
	背景属性：1背景颜色 2背景图片 3背景图片的重复方式
		1背景颜色 
			background-color 设置背景颜色
				颜色:英文单词、 16进制、 rgb(red, green, blue)
```
	background-color: lightgrey;
```
		2背景图片, 如果同时有背景颜色，优先显示图片
			background-image:url(图片地址)
```
	background-image:url(images/girl.jpg)
```
		3背景图片的重复方式
			background-repeat: repeat水平垂直同时平铺 no-repeat不平铺 repeat-x水平平铺 repeat-y垂直平铺
```
	background-repeat:repeat-x;
```
	多张背景图片：
```
		background-image:url(images/aa.jpg),url(images/girl.jpg);
		background-repeat:repeat-y, no-repeat;
```

	背景图片的定位：1 background-position属性 2 CSS Sprites
		background-position:关键字，百分比，像素值
			关键字：水平方向：left center right;垂直方向：top center bottom
			百分比：水平方向：0% 50% 100%对应左中右；垂直方向：0% 50% 100%对应上中下；
			像素值: 图片左顶点相对于上级元素的左顶点。 正数：水平向右，垂直向下，负数：水平向左，垂直向上
```
	/* background-position:center center; */
	/* background-position:50% 50%; */
	/* background-position:500px 300px; */
		background-position:-50px -50px;
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
	
	CSS Sprites, 雪碧图，精灵图
```
#first {
	background-position:0px 0px;
}
#second {
	background-position:0px -26px;
}
#third{
	background-position:0px -52px;
}
```
	背景渐变：1线性渐变  2径向渐变
		1线性渐变：background:linear-gradient(参数1（角度或者方向），参数2（颜色），参数3（颜色）...)
			参数1的角度是指渐变线与水平线之间的角度。
```
	background:linear-gradient(45deg,red,pink,blue);
	background:linear-gradient(to right,red,blue);
	background:linear-gradient(to right bottom,red 40%,white,black)
```
//todo
	透明度渐变
	rgb(red,green,blue)设置颜色, red green blue取值0-255或者百分比
	rgba(red,green,blue,alpha(透明度) ),设置颜色并使用透明度,alpha取值0-1
```
	background:linear-gradient(to right,rgba(255, 255, 255, 0),rgba(255, 255, 255, 0.6)),url(images/aa.jpg);
```
		重复线性渐变：background:repeating-linear-gradient
```
	background:repeating-linear-gradient(-45deg,red,blue 30px);
```
		2径向渐变：
			background:radial-gradient(参数1（形状或者圆心位置），参数2（颜色），参数3（颜色）。。)
```
background:radial-gradient(red,pink,blue,black)
```
		重复径向渐变：
```
	background:repeating-radial-gradient(circle, red 10px,blue 50px);
```

	阴影属性：1文字阴影 2盒子阴影
	1文字阴影
		text-shadow:h-shadow v-shadow blur color;
			h-shadow阴影水平距离（必须） b-shadow阴影垂直距离（必须） blur阴影半径 color阴影颜色
```
	text-shadow:10px 10px 5px red;
```
	2盒子阴影
		box-shadow:h-shadow v-shadow blur spread color;
			h-shadow阴影水平距离（必须） b-shadow阴影垂直距离（必须） blur阴影半径 spread阴影大小 color阴影颜色
```
	box-shadow:10px 10px 20px 20px blue;
```

盒子模型：1盒子模型原理 2标准稳定流 3浮动 4定位
	1盒子模型原理：
		1盒子模型概述 
			每个HTML元素都可以看作一个盒子。包含内容content 填充padding 边框border 边距(边界)margin
				（填充 边框 边距包含top上、bottom下、left左、right右四部分)
				
		2盒子的大小 
			计算方法：
			盒子实际大小：边框+填充+内容（不算边距）
				盒子实际宽度：左边框+左填充+内容宽度+右填充+右边框（不算边距）
				盒子实际高度：上边框+上填充+内容高度+下填充+下边框（不算边距）
									
			盒子占据空间大小: 盒子实际大小+边距
				盒子占据宽度：盒子实际宽+左边距+右边距
				盒子占据高度：盒子实际高+上边距+下边距

```
	长宽：300*300 px <br>
	边框：10px <br>
	填充：上下10px 左右20px <br>
	边距：10px
	
	盒子的实际宽度：10px + 20px + 300px +20px+10px=360px <br><br>
	
	盒子实际高度：上边框+上填充+内容高度+下填充+下边框（不包含边距）<br><br>

	盒子的实际高度：10px + 10px +300px + 10px + 10px = 340px <br><br>
	
	盒子所占据的空间：
	盒子所占据的宽度：360px + 30px + 30px=420px
	盒子所占据的高度：340px + 60px = 400px
```
		
		3盒子之间的关系:
			垂直盒子:  边距取margin-bottom和margin-top的最大值
			水平盒子： 边距取margin-left和margin-right的之和
			重叠盒子： 边距设置为负值
				margin可以是负数。但是border和padding不能是负数。
```
	margin-left:-50px;
```
			
	标准文档流：
		1概述：从左到右，自上而下的规则
			块元素：标题(<h1> - <h6>) 段落(<p>) 水平线(<hr />) 列表(<ul>、<ol>、<li>等) 表格(<table>) 层（<div>）表单(<form>)
			
			行元素：图片(<img>) 范围（<span>） 换行(<br />)  超链接(<a>)
			
			块元素和行元素的区别
				1排列方式不同
					行元素从左到右，多个行元素可显示在同一行。
					块元素独占一行，自上而下排列。
				2内嵌元素不同
					块元素可以包含块元素和行元素，但是行元素只能包含文本或者其他行元素。
				3属性设置不同
					块元素可以设置所有样式, 但是行元素不能设置width属性、height属性。
					行元素可以设置line-height，margin、padding上下方向无效。
		
		2 diplay属性 
			display: none | block; 
				隐藏元素，不占屏幕空间。若有其他元素，会上移到该区域。
```
#middle {
			display: none;
			display: block;
		}
```
		3 visibility属性
			visibility: hidden | visible; 
				只是控制是否可见，实际上还是存在,占据屏幕空间。
```
		visibility: visible;
		visibility: hidden;
```
		
	盒子浮动：
		float属性 
			float:none,left,right 
				left 移动到父元素左侧
				right 移动到父元素右侧
				none 默认
```
	float: none;
```
		
	清除浮动
		浮动副作用
			背景不能显示
			边框不能撑开
			margin padding不能正确显示
		
		清除浮动影响的方法
		1 对父级元素设置宽高
```
	#max {
			width: 800px;
			height:300px;
		}
```
		2 clear:both清除浮动
			在父级"</div>"结束前加上<div class="clear"> </div>
```
	.clear {
		clear: both;
	}
```
		3 在父级div定义 overflow:hidden;
```
#max {
		overflow:hidden;
	}
```
		div居中：
```
	margin:0px auto;
```
		