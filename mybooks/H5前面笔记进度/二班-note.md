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

4,网页编辑器
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
			<!-- <head>
				<meta charset="utf-8">
			</head> -->
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

超链接: <a> 
	//	<a target="_blank" href="作业1.html"> 点击跳转到刚才的作业 </a>
		属性： href: 跳转目标的URL
			  target :在何处打开URL
					默认值：_self  在自己页面打开
					可选值：_blank 在新页面打开
	//第一章结束-作业
	
音频标签： <audio> </audio>
	IE8以及之前的版本不支持<audio>标签
	属性： 
		必须的：  
				src  音频路径 
					相对路径（同一级./ 上一级../ 下一级/）
					绝对路径 
				controls 播放控件
		非必须的：autoplay 自动播放

	第一种语法(单个音频来源)：
		<audio src="音频/海阔天空.mp3" controls="controls" > 你的浏览器不支持audio！ </audio>
	
	第二种语法(多个音频来源)：
		<source> 来源
		有多个音频来源的时候，默认播放第一个支持的音频。
		<!-- 第二种 -->
		<audio controls="controls" > 
			<source src="音频/光辉岁月.mp3" type="audio/mp3" />
			<source src="音频/纸短情长.mp3" type="audio/mp3" />
			你的浏览器不支持音频！ 
		</audio>
		
视频标签：<video> </video>
	IE8以及之前的版本不支持<video>标签
	属性： 
		必须的： src 视频路径
					绝对路径
					相对路径：./ 当前目录  ../ 上级目录 
				controls 显示控件
		非必须： width 宽  height 高  poster 视频加载时显示的图像（视频封面）
	
	有多个视频来源的时候，默认播放第一个支持的视频。
	第一种(单个视频来源):
		<video poster="images/libai.jpg" width="500px"  src="视频/海阔天空60秒.mp4" controls="controls" > 你的浏览器不支持video标签！ </video>
	第二种(多个视频来源):
		<source> 标签
		<!-- <video controls="controls">
			<source src="视频/光辉岁月60秒.ogg" />
			<source src="视频/海阔天空60秒.mp4" />
			你的浏览器不支持video! 
		</video> -->
		
列表： ordered 有序的  unordered 无序的   list 列表
	无序列表(unordered list简写)： <ul>  </ul>
		属性： type 设置列表项开始的符号，取值：默认disc(实心圆)、circle（空心圆）、square(实心正方形)
		列表项 <li> </li>
		<ul type="属性值">
			<li> 第一项 </li>
			<li> 第二项 </li>
			<li> 第三项 </li>
		</ul>
	
	有序列表(ordered list 简写): <ol> </ol>
		属性：type 设置列表项开始的符号，取值：默认1,a,A,i,I
			  start 序号起始值
		列表项 <li> </li>
		
	自定义列表(definition list简写)：<dl>、<dt>、<dd>
	<dt> (definition title简写，定义标题)
	<dd>（definition description简写，定义描述)
	//todo
	<dl>
		<dt> 标题1 </dt> <dd> 注释1 </dd>
		<dt> 标题2 </dt> <dd> 注释2</dd>
		<dt> 标题3 </dt> <dd> 注释3</dd>
		<dt> 标题4 </dt> <dd> 注释4</dd>
	</dl>

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

表单标签： <form> </form>
	属性：
		必须的： name :表单名称
				action : 提交的url
				method : 提交方式 默认get，通常可选：get 、post
	