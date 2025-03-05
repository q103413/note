# 网页设计笔记

![](http://img.rmb520.com/test/mywechat.jpg) ![](http://img.rmb520.com/test/mypublic.jpg)

上网方式（客户端）： 电脑端：网页 移动端：网页+APP+小程序111

目的：解决用户体验问题

必备条件： 1、会上网、会打字、基础英语 2、兴趣 3、肯做练习、耐心

具体学习哪些东西： 1、软件 5%时间 1、浏览器内核分类（谷歌浏览器、火狐浏览器、IE浏览器、苹果浏览器） 2、浏览器开发者工具：F12 （或者Fn + F12） 3、写代码的编辑器：记事本、DreamWeaver(DW)、Hbuilder、Sublime、VS code 了解前端三剑客：DW、FireWorks(PhotoShop)、Flash(Animate) 2、语言（和浏览器打交道的语言） 95%以上时间 HTML CSS JavaScript

教学资源

http://www.w3school.com.cn

http://www.csszengarden.com 禅意花园

http://www.webpagesthatsuck.com

https://www.runoob.com/ 菜鸟教程

## 一、HTML5基础

### 1 什么是 HTML

什么是互联网？ WWW（World Wide Web, 万维网）

网页的HTML本质

​ HTML(Hypertext Markup Language)

web标准： W3C（万维网联盟），不是某一个标准，它是一系列标准的集合。 web标准分为三个标准： 1、结构化标准 网页结构（Structure） 对应 HTML 2、表现标准 网页样式（表现Presentation） 对应 CSS 3、行为标准 网页行为（Behavior） 对应 JavaScript

HTML： 1、用来描述网页的一种语言 2、不是一种编程语言，但是它是一种标记语言 3、标记语言是一套标记标签

HTML文档 1、 = 网页 2、包含HTML标签和纯文本

网页： 1、扩展名(文件后缀)：.html 或者 .htm 2、必须通过浏览器来阅读 3、组成：文字、图片、视频、音频、超链接、特效、动画等

浏览器： 1，浏览器内核种类（谷歌浏览器、火狐浏览器、IE浏览器、苹果浏览器） 2，开发者工具：F12 或者 Fn+F12（error错误、warn警告） 3、作用：读取HTML文档，并且以网页的形式展现出来 4、界面组成：菜单栏、网页标题、地址栏、网页窗口

4、代码编辑器 1，记事本（纯文本） 2、DreamWeaver（DW），所见即所得 3、Hbuilder 4、VS Code（推荐）

​ 5、Notepad++、Sublime Text、UltraEdit 和 Xcode（适用于 macOS）等

#### 创建和测试网页

1．创建网页

​ 1、启动“记事本”程序

​ 2、输入 HTML 代码

​ 3、“保存”或“另存为”

​ 4、在“文件名”框中输入网页的名称，注意文件名必须以.htm 或.html 为扩展名。如果必要，可定位到特定的目录

2．测试网页

​ Chrome 打开。

### 2 创建网页

#### 2.1 标记符基础

**1．基本的 HTML 语法**

HTML标签(HTML tag): 1 由尖括号包围的关键词，比如\<html> 2 通常是成对出现，比如\<p>这是段落\</p>，\<title>这是标题\</title> 3 标签对中的第一个标签是开始标签（开放标签），第二个标签是结束标签（闭合标签）

空标签： 单独存在的标签。比如\<hr />、\<br /> 1 没有内容 2 没有结束标签 3 在开始标签中关闭

HTML元素：从开始标签（start tag）到结束标签（end tag）的所有代码 1、以开始标签起始，以结束标签终止 2、元素的内容：开始标签与结束标签之间的内容 3、某些HTML元素具有空内容(empty content) ,比如 \<hr /> 元素 = 标签+元素内容

空元素： 没有内容的HTML元素成为空元素。 就是没有关闭标签的空元素。比如\<hr /> 在开始标签中关闭。

注意： 1、不要忘记结束标签(即使空标签也要写“/”) 虽然忘记结束标签，大多数浏览器也会正确显示 2、不区分大小写，建议使用小写标签 HTML标签对大小写不敏感： \<P> 等同于 \<p> 3、 所有的代码都要用英文状态

```html
<h1>这是标题文字</h1>
<p>这是普通段落文字</p>
换行标记符 <br>
```

**2．标记符的属性**

属性是用来描述对象特征的特性。例如，人的身高、体重。

HTML属性放在开始标记符，属性之间用空格分开，属性值用引号。

```html
<a href="target.htm" title="点击有惊喜">超链接</a>
```

HTML属性： 1、属性为HTML元素提供附加信息。 2、属性总是以名称/值对的形式出现。比如：name="value"

​ 3、属性总是在HTML元素的开始标签中规定。 ​ 比如可能有以下属性： align对齐方式 face字体 size大小 color颜色 width宽 height高。。。 ​ 4、适用于大多数HTML元素的属性： ​ style: 设置元素的样式（CSS） ​ 比如设置颜色、宽度、高度等：style="color:red;width:200px;height:100px;" ​ title：规定元素的额外信息（可在工具提示中显示）

#### 2.2 网页的基本结构

学习HTML标签： \<html>:告知浏览器自身是一个 HTML 文档。 最先出现和最后出现的标签、成对出现 首标签\<html>和尾标签\</html>分别位于网页文件的最前面和最后面 网页的所有文件和标签都包含在其中

```html
	<html>
			网页的全部内容
	</html> 
```

\<head>:表示网页的头部标签。包含网页的标题、编码方式等信息。 以下标签都包含在里面：\<title>、\<meta>、\<script>、\<style>、\<link>、\<base>等 \<title>:定义文档的标题 title标签的内容出现在浏览器窗口 所有的网页都必须要有title标签。 是\<head> 标签中唯一要求包含的标签。 当把文档加入收藏夹或书签时，标题将成为默认名称。

```html
<head>
		<title>这是网页标题，所有网页必须的</title>
</head>
```

​ \<meta>: (meta 元)定义网页的元数据 ​ \<meta>元素提供网页的元信息(meta-information) ​ 位于head标签内部，不包含任何内容。没有结束标签。 ​ \<meta>标签通过属性名称/值对定义文档元信息。 ​ 为了正确显示网页，浏览器必须知道要使用哪个字符集。 ​ 我们通常使用utf-8、gb2312（简体中文）字符集表达中文字符。 ​ 设置网页字符集：\<meta charset="utf-8"> （character 字符集 + set 设置 = charset）

```html
	<head>
		<meta charset="utf-8">
	</head> 
```

\<body>：定义网页文档的主体内容 1、body元素包含文档的所有内容（比如文本、超链接、图像、表格和列表等等。） 2、拥有一个开始标签\<body>，以及一个结束标签\</body> 3、被浏览器显示在屏幕上 // 属性：bgcolor

```html
<html>
<head>
	<title>我的第一个HTML文档</title>
</head>
<body>
		Hello World!
</body>
</html>
```

HTML注释: 1、提高代码可读性，更容易理解。 2、 浏览器会忽略注释，也不会显示出来。 3、 \<!-- 这是注释 --> 或者编辑器快捷键Ctrl+/

```html
<html>
	<head>
		<title>注释不在浏览器中显示</title>
	</head>
	<body> 正文，正文，正文 </body>
	<!-- 本行内容并不在浏览器中显示！ -->
</html>
```

显示特殊字符

​ 参考字符以“&”号开始，以“；”结束，既可以使用数字代码，也可以使用代码名称。

​ 空格：\&nbsp;

​ &：\&amp;

​ 小于号：\&lt; ​ 大于号：\&gt;

​ 版权符号：\&copy;

​ \*\*注意：\*\*空格、回车这些格式控制在显示时都不起作用。

### 3 综合实例：人物介绍网页

```html
<html>
	<head>
		<title>百里屠苏</title>
	</head>
	<body>
		<h1>百里屠苏<img src="百里屠苏.jpg" align="right"></h1>
		<hr>
		<h2>技能</h2>
		<hr>
		<h3>玄真剑</h3>
		<p>习自师门的道家剑术，看似简单，但其中奥妙无穷！<br />
			耗值：22点气、2行动点数<br />
			效果：剑技攻击，敌方全体<br />
	</body>
</html>
```
