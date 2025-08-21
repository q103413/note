网页设计（前端、front end）
张卫 thinkzw@foxmail.com
电商、金融、ERP、仿抖音小红书微信

上网方式：
	电脑端：网页 
	移动端：网页+APP+小程序

目的：解决用户体验问题

必备条件：
	1、会上网、会打字、基础英语
	2、兴趣
	3、肯定练习、耐心

学习：
	1软件
		1浏览器（谷歌浏览器、IE浏览器、火狐浏览器、苹果Safari浏览器）
		2浏览器开发者工具（F12或Fn+F12）
		3写代码的编辑器（记事本、DreamWeaver、Huilder、VS code、Sublime）
		了解：前端三剑客：DW、FireWorks(PS)、Flash(Animate)	
	2语言（语言是和浏览器打交道）
		HTML
		CSS
		JavaScript

1什么是互联网
	WWW（World Wide Web）,万维网
	包含3个基本组成部分：https://www.bilibili.com/
	1、URL 
	2、HTTP(三次握手)
	3、HTML （HyperText Markup Language）超文本 标记 语言
		1、直接由浏览器执行
		2、不是编程语言、但是它是一门标记语言
		3、标记语言是一套标签

网页：
	扩展名(文件后缀)：.html、.htm
	必须浏览器阅读
	组成：文字、图片、音频、视频、特效

WEB标准：
	W3C,万维网联盟
	不是一个标准，它是一系列标准的集合：
	包含三个方面：
	1，结构化标准： 		网页结构（Structure）		对应 HTML 
	2，表现标准：		网页样式(Presentation) 	 	对应 CSS
	3，行为标准：		行为（Behavior）				对应JavaScript

浏览器：
	1，浏览器内核种类（谷歌浏览器、火狐浏览器、IE浏览器、苹果浏览器）
	2，开发者工具：F12 或者 Fn+F12
	3、作用：读取HTML文档，并且以网页的形式展现出来
	4、界面组成：菜单栏、网页标题、地址栏、网页窗口

编辑器：
	1、记事本
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
	3、HBuilder 
		1、下载（官网下载）
		2、安装
		3、使用
			界面：菜单栏
			新建项目（站点）：
				1、菜单栏点击文件-新建-项目-输入名称、路径
				2、左侧窗口单击右键-新建-项目-输入名称、路径
				3、快捷键：Ctrl+N (new新的)
			新建网页：
				1、菜单栏点击文件-新建-html文件-输入名称、路径
				2、左侧窗口单击右键-新建-html文件-输入名称、路径
				3、快捷键：Ctrl+N
			注意保存目录：
					1、保存的时候需要选择对应路径
					2、左键单击父级文件夹（项目）
			新建目录：（注意路径）
				1、菜单栏点击文件-新建-目录-输入名称、路径
				2、左侧窗口单击右键-新建-目录-输入名称、路径
				3、快捷键：Ctrl+N 
Huilder快捷键
	搜索：Ctrl+F (find)
	复制当前行：ctrl+insert
	浏览器预览：Ctrl+R
	格式化：Ctrl+k
	注释：Ctrl+/
	向下插入行：Ctrl+enter
	向上插入行：Ctrl+shift+enter

演示HTML标签：举4个例子
	HTML标题 <h>：通过h1-h6等标签定义，从h1到h6从大到小,Heading
	段落 <p>: paragraph
	<a>:超链接
	<img>:插入图片

HTML标签(HTML tag):
	1 由尖括号包围的关键词，如<html>
	2 通常是成对出现，比如<p>这是段落</p>、<title>这是标题</title>
	3 标签对中的第一个标签是开始标签，第二个标签是结束标签
		开始标签和结束标签又叫做开放标签和闭合标签

空标签：比如：<hr />、<br />
	没有内容的标签。
	没有关闭标签。
	在开始标签中关闭。

HTML元素：从开始标签（start tag）到结束标签（end tag）的所有代码
	1、以开始标签起始，以结束标签终止
	2、元素的内容：开始标签与结束标签之间的内容
	3、某些HTML元素具有空内容(empty content) ,比如<hr />

空元素：
	没有内容的HTML元素成为空元素。
	就是没有关闭标签的空元素。比如<hr />
	在开始标签中关闭。

注意：
	1、不要忘记结束标签(即使空标签也要写“/”)
		即使忘记结束标签，大多数浏览器也会正确显示
	2、推荐使用小写标签
		HTML标签对大小写不敏感：<P> 等同于 <p>
	//todo
	3、 所有的代码都要用英文状态

HTML属性：
		1、属性为HTML元素提供附加信息。
		2、属性总是以名称/值对的形式出现。比如：name="value"
		3、属性总是在HTML元素的开始标签中规定。
		比如可能有以下属性： align对齐方式 face字体 size大小 color颜色 width宽 height高。。。
		4、适用于大多数HTML元素的属性：
			style: 设置元素的样式（CSS）
				比如设置颜色、宽度、高度等：style="color:red;width:200px;height:100px;" 
			title：规定元素的额外信息（可在工具提示中显示）

HTML注释：
	1、可以将注释插入HTML代码中，提高代码可读性，更容易理解。
	2、浏览器会忽略注释、也不会显示它们。
	3、<!-- 这是注释 --> 或者快捷键：Ctrl+/
	
学习HTML标签：
	<!DOCTYPE>声明：帮助浏览器正确地显示网页。
		document type（文档类型）的简写
		必须是 HTML 文档的第一行，位于 <html> 标签之前。
		不是 HTML 标签；指示浏览器此网页是使用哪个HTML版本编写。
		没有结束标签。对大小写不敏感。
		HTML5写法：<!-- 	<!DOCTYPE html> -->
	<html>:告知浏览器自身是一个 HTML 文档。
		最先出现的标签，成对出现
		首标签<html>和尾标签</html>分别位于网页文件的最前面和最后面
		文件的所有文件和html标签都包含在其中
	<!-- 	<html>
			网页的全部内容
		</html> -->	
	<head>:表示网页的头部标签。包含网页的标题、编码方式等信息。
	    包含<meta>、<title>、<link>、<script>、<style>等标签
		<meta>: 
			//todo
			<meta>元素提供页面的元信息（meta-information）
			<meta>标签位于head元素内部，不包含任何内容
			<meta>标签通过属性名称/值对定义文档元信息。
			在 HTML 中，<meta> 标签没有结束标签。
				为了正确的显示HTML页面，浏览器必须知道要使用哪个字符集。
				我们通常使用utf-8、gb2312(简体中文)字符集表达中文字符。
				设置网页字符集：<meta charset="utf-8">
				// <head>
				// 	<meta charset="utf-8">
				// </head>
				// 字符集character + 设置set = charset
		<title>:定义文档的标题
			title标签的内容出现在浏览器窗口。
			title元素在所有HTML文档中都是必需的。
			是<head> 标签中唯一要求包含的标签。
			当把文档加入收藏夹或书签时，标题将成为默认名称。
			//<head>
			//	<title>这是网页标题，所有网页必须的</title>
			//</head>
	<body>: <body>元素定义网页文档的主体
			1、body元素包含文档的所有内容（比如文本、超链接、图像、表格和列表等等。）
			2、拥有一个开始标签<body>，以及一个结束标签</body>
			// 属性：bgcolor			
	//作业
	// <!DOCTYPE html>
	// <html>
	// 	<head>
	// 		<meta charset="utf-8">
	// 		<title>我的第一个HTML文档</title>
	// 	</head>
	// 	<body>
	// 		Hello World!
	// 	</body>
	// </html>

	标题(Heading): <h1> - <h6>等标签， 从大到小
		<h1>定义最大的标题，<h6>定义最小的标题
		 属性：align  属性值：left center right
	//作业
	段落(paragraph)：<p>标签
		属性：align(对齐方式) 属性值：left center right
			 title： 设置工具提示
			 style: 设置样式: style="color:red" 
	
	换行：<br /> 空标签
	//作业
	
	文字标签：<font>
		属性：face 字体 color 颜色 size 大小 
	
	水平标签(水平线、分割线)：<hr /> 空标签
		属性： 
			width 宽度（单位是px或者百分比） 
			size(大小、尺寸、厚度)    
			color 颜色
			align 对齐方式 (left center right)
			noshade 去掉阴影 noshade="noshade"
	
	强调标签（加粗）：<b> 或者 <strong>
	
	空格标签： &nbsp;
	
	居中标签：<center>
	
	图片标签(image)：<img /> 空标签
		// <img align="left" alt="这是李白的画像" src="images/libai.jpg" width="200px" />
		属性：
			必须：src（source 来源） 图片路径：
					相对路径(相对当前文件)：./ 同一级 ../上一级 ../../上两级，比如：./boy.jpg
					绝对路径（与当前文件无关）: 比如： https://www.xxx.com/xxx.jpg
				 alt（alternate 备用的） 提示信息（图片不显示的时候才显示）
			非必须：width 宽 height 高  border 边框(单位px)
				   align      相对于周围文本的对齐方式
						left	把图像对齐到左边
						right	把图像对齐到右边
						middle	把图像对齐到中间
						top	 	把图像对齐到顶部
						bottom	把图像对齐到底部
	
	超链接: <a> 
	//	<a target="_blank" href="作业1.html"> 点击跳转到刚才的作业 </a>
		属性： href: 跳转目标的URL地址
				 绝对地址、相对地址
			  target :在何处打开URL
					默认值：_self  在自己页面打开
					可选值：_blank 在新页面打开
	//第一章结束-作业
	
	音频标签：<audio> 
		IE8以前的浏览器不支持audio。
		属性： 
			必须：	
				src 音频路径
					绝对路径 http://www.xxx.com/xxx.mp3
					相对路径  ./当前目录  ../上级目录  /下级目录
				controls 显示播放控件
			非必须： autoplay 自动播放
	
		第一种写法：
			<audio src="音频/纸短情长.mp3" controls="controls"> 你的浏览器不支持audio! </audio>
		
		第二种写法：
			<source> 可选多个音频来源标签,默认选择第一个可用音频来源
			<audio controls="controls">
				<source src="音频/海阔天空.mp3" type="audio/mp3" />
				<source src="音频/海阔天空.wav" type="audio/wav" />
				你的浏览器不支持音频！
			</audio>
			
	视频标签：<video>
		属性： 
			src 视频路径 
				相对路径 、 绝对路径
			controls 播放控件
			poster 视频加载时显示的图片（视频封面）
			
		第一种写法：
			 //绝对路径 
			<!-- <video controls="controls" src="https:www.xxx.com/xxx.mp4"  > 你的浏览器不支持video！</video> -->
			//相对路径 
			<!-- <video src="视频/海阔天空60秒.mp4" controls="controls" > 你的浏览器不支持video ! </video> -->
		
		第二种写法：
		<video width="300px" poster="美女图片.jpg" controls="controls"  >
			<source src="视频/海阔天空60秒.mp4" type="video/mp4" />
			<source src="https:www.xxx.com/xxx.ogg" type="video/ogg" />
			你的浏览器不支持video!
		</video>

列表标签：（ordered 有序的  unordered无序的  list 列表）
	无序列表：ul（unordered list简写）
		属性: type 设置列表项开始的符号:默认disc(实心圆)、circle（空心圆）、square(正方形)
```
		<ul type="设置列表项开始的符号"> 
			<li>第一列</li>
			<li>第二列</li>
			<li>第三列</li>
		</ul>
```

	有序列表：<ol> (ordered list 简写)
		属性：type 设置列表项开始的符号: 1（默认）、a、A、i、I
			start   设置开始项
```
		<ol type="设置列表项开始的符号" start="设置开始项"  >
			<li>第一列</li>
			<li>第二列</li>
			<li>第三列</li>
		</ol>
```


	自定义列表：<dl>  (definition list简写)
		<dt> (definition title简写，定义标题)
		<dd>（definition description简写，定义描述)
```
	<dl>
		<dt> 标题1 </dt> <dd> 注释1 </dd>
		<dt> 标题2 </dt> <dd> 注释2</dd>
		<dt> 标题3 </dt> <dd> 注释3</dd>
		<dt> 标题4 </dt> <dd> 注释4</dd>
	</dl>
```

<div>标签： （division简写 分开、分界）
	1、没有特定含义，只是组合其它HTML元素的容器。
	2、默认独占一行（多个div共存时，从上到下排列）
	3、如果与 CSS 一同使用，<div> 元素可用于对大的内容块设置样式属性。
	4、<div> 元素的另一个常见的用途是文档布局。它取代了使用表格定义布局的老式方法。使用 <table> 元素进行文档布局不是表格的正确用法。<table> 元素的作用是显示表格化的数据。
	5、可以对同一个 <div> 添加 class 或 id 属性（页面中每个标签的ID不能相同）

<span>标签：  (span 跨度、范围)
	1、没有特定含义，可作为文本的容器。
	2、多个span标签可以存在同一行（从左到右排列）
	3、当与 CSS 一同使用时，<span> 元素可用于为部分文本设置样式属性。

表格标签：<table></table> 、<tr></tr>、<td></td>
	主要由表格标签<table>、行标签<tr>、单元格<td>标签构成。
	<table>属性： border 边框大小（单位px）
			width 宽 （单位px 或者屏幕的百分比） height (单位px)
			bgcolor (background color简写) 背景颜色
			background 背景图片
			align 对齐方式（表格相对屏幕）
			cellspacing (cell单元 spacing间距)  单元格间距
			cellpadding (cell单元 padding填充、内衬)  单元格填充
			
	<td>属性： rowspan 跨行(row span)   colspan 跨列(column span)
			width 宽 （单位px） bgcolor (background color简写) 背景颜色 background 背景图片
			align 对齐方式 （表格内容）
		
	表格<table>中的其他标签：
		<caption> 表格标题  （caption 说明文字）
		<th> 定义表头

表单标签：<form> </form>
	必须的属性：  name  表单名称
				action  表单提交的URL
				method  提交方式，可选get、post 默认get
			get、post区别
				安全性：get方式提交的表单信息会出现在浏览器地址栏（参数附加在URL后面）
					   但是post不会出现在地址栏
				提交数据的长度：get方式提交数据的长度有限制。
							 post方式没有长度限制。（文件上传，建议使用post）
						
```
	<form name="表单名称" action="提交URL" method="提交方式"  >
	
	</form>
```

表单元素概述：大部分使用input标签，只是属性不同
	<input>属性： type  表单控件类型，通常有text password submit radio checkbox 。。。 
				  name 名称
				  value 初始值
				  size  表单元素的初始宽度
				   maxlength 在text、password中输入的最大长度，默认无限制
				   checked 是否选中
				   readonly 不能编辑 
				   placeholder 设置提示文字
```
	<input type="类型" name=“名称” value=“初始值“ size="显示宽度" maxlength="输入的最大长度" checked="是否选中" >
```
	常用的表单控件标签：
		文本框<input type="text">
		密码框<input type="password">
		提交按钮<input type="submit">
		单选：<input type="radio">
		多选：<input type="checkbox">
		下拉选框： <select>
		多行文本框： <textarea>

输入框：
	单行文本框：<input type="text" name="名称" value="初始值" >
```
	<input size="100" value="" type="text" name="username" id="username">
```
	密码框：
```
<input type="password" name="password" >
```
	多行文本框：<textarea>
		属性：cols 设置列数  rows 设置行数  name名称
```
	<textarea name="textarea" cols="50" rows="5">
		多行文本
	</textarea>
```

按钮： 分为提交按钮、重置按钮、普通按钮
	属性：disabled="disabled" 禁用按钮
	提交按钮：提交表单数据
```
	<input type="submit" name="submit" value="点击注册">
```
	重置按钮：清空现有表单数据
```
	<input type="reset" value="点击清空表单" name="reset">
```
	普通按钮：调用JavaScript脚本
```
	<input onclick="alert('有人没听课')" type="button" name="bt" value="点击提交">
	<input type="button" value="这是按钮，点击起飞" name="button"> 
```
	图片按钮：（提交按钮）
```
	<input type="image" src="图片路径" alt="提示信息" name="名称" >
	<input width="100px" type="image" src="yyqx.jpg" alt="图片按钮" name="imageSubmit"  >
```

	单选按钮：1、type="radio"  2、单选组中具有相同的name 3、加上value值
		<input type="radio" name="同一组有相同的名称">
		默认选中：checked="checked" 
```
	男：<input type="radio" name="gender" value="boy">	
	女：<input type="radio" name="gender" value="girl">
```
	多选按钮：将单选的radio改成checkbox
		<input type="checkbox" name="同一组有相同的名称">
		默认选中：checked
```
	王一博：<input type="checkbox" name="star" value="王一博">
	蔡徐坤：<input checked type="checkbox" name="star" value="蔡徐坤">
```
	下拉选框：<select>
		属性： size 默认显示的行数  multiple="multiple" 变成多选
		默认选中：selected="selected"
```
	<select name="chongqing_snack" size="1">
		<option value=""> -- 请选择你喜欢的小吃-- </option>
		<option value="hotpot"> 火锅 </option>
		<option value="small_noodle" selected="selected">小面</option>
		<option value="bread" >糍粑</option>
	</select>
```

验证
	必填验证： required="required"
```
	<input type="text" name="text" required="required">
```
	类型验证：email(邮箱) url number（数字） range(范围)  date(日期)
		email验证:type="email"
```
	<input type="email" name="email_validate">
```
		url验证:type="url"
```
	<input type="url" name="url_validate">
```
		数字验证：type="number"
```
	<input type="number" name="number_validate">
```
		日期验证：type="date" 
```
	<input type="date" name="date_validate">
```
		range(范围): 滑动条，配合min max step（步长）
```
	<input type="range" step="10" min="1" max="100" name="range_validate">
```
		控制字符数量： maxlength="11"
```
	<input type="text" maxlength="11" name="phone">
```
		验证输入范围：配合min（最小值）  max（最大值）  step（步长）
```
	<input type="number" max="100" min="10" step="5" name="number_validate">
```
	自定义错误消息：
		oninvalid（当用户输入不合法）:
			oninvalid="setCustomValidity('提示的信息')"  (on invalid set custom validity)
```
	<input type="number" min="1" max="100" oninvalid="setCustomValidity('亲,年龄不能超过100哦!')">
```
		oninput(当用户正常输入)
			oninput="setCustomValidity('')" 
```
				<input type="number" min="1" max="100" oninput="setCustomValidity('')"  oninvalid="setCustomValidity('亲,年龄不能超过100哦!')">
```
```
			年龄：<input oninput="setCustomValidity('')" oninvalid="setCustomValidity('亲,年龄过大不建议上网哦!')" type="number" min="0" max="60" required>
```