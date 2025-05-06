<img src="http://img.kiss58.com/test/mywechat.jpg" width="200px"><img src="http://img.kiss58.com/test/mypublic.jpg" width="240px">

上网方式（客户端）：  

- ​	电脑端：网页
- ​	移动端：网页+APP+小程序

目的：解决用户体验问题

必备条件：

- ​	会上网、会打字、基础英语
- ​	兴趣
- ​	肯做练习、耐心

具体学习哪些东西：

1. ​	软件 5%时间

   - 浏览器内核分类（谷歌浏览器、火狐浏览器、IE浏览器、苹果浏览器）

   - 浏览器开发者工具：F12 （或者Fn + F12）

   - 写代码的编辑器：记事本、DreamWeaver(DW)、Hbuilder、Sublime、VS code

     了解前端三剑客：DW、FireWorks(PhotoShop)、Flash(Animate)

2. 语言（和浏览器打交道的语言） 95%以上时间

   - HTML

     - CSS

     - JavaScript


教学资源

- http://www.w3school.com.cn 

- http://www.csszengarden.com  禅意花园

- http://www.webpagesthatsuck.com 

- https://www.runoob.com/ 菜鸟教程


# 一、HTML5基础

## 1 什么是 HTML

什么是互联网？
	WWW（World Wide Web, 万维网）

网页的HTML本质

​	HTML(Hypertext Markup Language)

web标准：
	W3C（万维网联盟），不是某一个标准，它是一系列标准的集合。   
	web标准分为三个标准：   

1. 结构化标准		网页结构（Structure）  		   对应		HTML    
2. 表现标准		 网页样式（表现Presentation）  	对应		CSS  
3. 行为标准	 	网页行为（Behavior） 			对应		JavaScript    

HTML：

- ​	用来描述网页的一种语言  
- ​	不是一种编程语言，但是它是一种标记语言  
- ​	标记语言是一套标记标签

HTML文档  

-  = 网页  
- 包含HTML标签和纯文本

网页：

- 扩展名(文件后缀)：.html 或者 .htm
- 必须通过浏览器来阅读
- 组成：文字、图片、视频、音频、超链接、特效、动画等

浏览器：

- 浏览器内核种类（谷歌浏览器、火狐浏览器、IE浏览器、苹果浏览器）
- 开发者工具：F12 或者 Fn+F12（error错误、warn警告）
- 作用：读取HTML文档，并且以网页的形式展现出来
- 界面组成：菜单栏、网页标题、地址栏、网页窗口

4、代码编辑器

- 记事本（纯文本）
- DreamWeaver（DW），所见即所得
- Hbuilder
- VS Code（推荐）	（https://code.visualstudio.com/Download)	
- Notepad++、Sublime Text、UltraEdit 和 Xcode（适用于 macOS）等

### 创建和测试网页

1．创建网页

- 启动“记事本”程序

- 输入 HTML 代码

- “保存”或“另存为”

- 在“文件名”框中输入网页的名称，注意文件名必须以.htm 或.html 为扩展名。如果必要，可定位到特定的目录

2．测试网页

- ​	 Chrome 打开。


## 2 创建网页

### 2.1    标记符基础

#### 1．基本的 HTML 语法

HTML标签(HTML tag):  
	1 由尖括号包围的关键词，比如`<html>`  
	2 通常是成对出现，比如`<p>这是段落</p>`，`<title>这是标题</title>`  
	3 标签对中的第一个标签是开始标签（开放标签），第二个标签是结束标签（闭合标签）  

空标签： 单独存在的标签。比如`<hr />、<br />`	  

- ​	没有内容  
- ​	 没有结束标签  
- ​	 在开始标签中关闭  

HTML元素：从开始标签（start tag）到结束标签（end tag）的所有代码  

- ​	以开始标签起始，以结束标签终止  
- ​	元素的内容：开始标签与结束标签之间的内容  
- ​	某些HTML元素具有空内容(empty content) ,比如 `<hr />`  

​	元素 = 标签+元素内容  

空元素：

- ​	没有内容的HTML元素成为空元素。  
- ​	就是没有关闭标签的空元素。比如`<hr />`  
- ​	在开始标签中关闭。

注意：

- 不要忘记结束标签(即使空标签也要写“/”)  

​		虽然忘记结束标签，大多数浏览器也会正确显示  

- 不区分大小写，建议使用小写标签  

​		HTML标签对大小写不敏感： `<P>` 等同于  `<p>`  

-  所有的代码都要用英文状态  

```html
<h1>这是标题文字</h1>
<p>这是普通段落文字</p>
换行标记符 <br>
```

#### 2．标记符的属性

属性是用来描述对象特征的特性。例如，人的身高、体重。

HTML属性放在开始标记符，属性之间用空格分开，属性值用引号。 

```html
<a href="target.htm" title="点击有惊喜">超链接</a>
```

HTML属性：

1. 属性为HTML元素提供附加信息。  
2. 属性总是以名称/值对的形式出现。比如：name="value"  
3. 属性总是在HTML元素的开始标签中规定。  
   ​       	比如可能有以下属性： align对齐方式 face字体 size大小 color颜色 width宽 height高。。。
4. 适用于大多数HTML元素的属性：  
   ​        style: 设置元素的样式（CSS）  
   ​            比如设置颜色、宽度、高度等：`style="color:red;width:200px;height:100px;"`   
   ​        title：规定元素的额外信息（可在工具提示中显示）

### 2.2    网页的基本结构

学习HTML标签：  
`<html>`:告知浏览器自身是一个 HTML 文档。  

-   最先出现和最后出现的标签、成对出现  
-   首标签`<html>`和尾标签`</html>`分别位于网页文件的最前面和最后面   
-   网页的所有文件和标签都包含在其中    

```html
	<html>
			网页的全部内容
	</html> 
```

`<head>`:表示网页的头部标签。包含网页的标题、编码方式等信息。  
  以下标签都包含在里面：`<title>、<meta>、<script>、<style>、<link>、<base>`等  

​	`<title>`:定义文档的标题

- ​	title标签的内容出现在浏览器窗口
- ​	所有的网页都必须要有title标签。
- ​	是`<head>` 标签中唯一要求包含的标签。
- ​	当把文档加入收藏夹或书签时，标题将成为默认名称。

```html
<head>
		<title>这是网页标题，所有网页必须的</title>
</head>
```

​	`<meta>`: (meta 元)定义网页的元数据  

- ​	    `<meta>`元素提供网页的元信息(meta-information)  
- ​	    位于head标签内部，不包含任何内容。没有结束标签。  
- ​	    \<meta>标签通过属性名称/值对定义文档元信息。  
- ​	    为了正确显示网页，浏览器必须知道要使用哪个字符集。  

​	    我们通常使用utf-8、gb2312（简体中文）字符集表达中文字符。  
​	    设置网页字符集：`<meta charset="utf-8">`  （character 字符集 + set 设置 = charset）

```html
	<head>
		<meta charset="utf-8">
	</head> 
```



`<body>`：定义网页文档的主体内容  

- body元素包含文档的所有内容（比如文本、超链接、图像、表格和列表等等。）  
- 拥有一个开始标签\<body>，以及一个结束标签`</body>`  
- 被浏览器显示在屏幕上  
- 属性：bgcolor	

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

HTML注释:  

- 提高代码可读性，更容易理解。  
- 浏览器会忽略注释，也不会显示出来。  
- `<!-- 这是注释 -->` 或者**编辑器快捷键Ctrl+/**

```html
<html>
	<head>
		<title>注释不在浏览器中显示</title>
	</head>
	<body> 正文，正文，正文 </body>
	<!-- 本行内容并不在浏览器中显示！ -->
</html>
```

显示**特殊字符**

​	参考字符以“&”号开始，以“；”结束，既可以使用数字代码，也可以使用代码名称。

- ​	空格：`\&nbsp;`

- ​	&：`\&amp;`

- ​	小于号：`\&lt;`
- 大于号：`\&gt;`
- ​	版权符号：`&copy;`


​	**注意：**空格、回车这些格式控制在显示时都不起作用。

## 3    综合实例：人物介绍网页

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

vs code格式化快捷键： shift+alt+f

# 二、文本格式与超链接

## （1）段落格式

段落(paragraph): `<p>`标签  
    属性：

- align 对齐方式 ：居中 center  左边 left 右边 right  
- title： 设置工具提示  
- style ：设置行内样式，比如文字变灰色：style="color:grey"

换行：`<br />`  （空标签）

标题(Heading)：`<h1> - <h6>等标签,从大到小，<h1>最大，<h1>定义最大的标题，<h6>定义最小的标题`  
	属性：align 对齐方式 ，取值：right（右对齐）、left（左对齐）、center（居中对齐）和 justify（两端对齐）

居中标签：`<center>`

水平标签（水平线、分割线）: `<hr />` （空标签）

`<hr 属性名称=“属性值” />`  
    属性： 

- width 宽度（单位是px或者百分比） 
- size(大小、尺寸、厚度) 
- color 颜色
- align 对齐方式 (left center right)
- noshade 去掉阴影 noshade="noshade"

**课堂案例**：段落格式-李商隐(19页)

```html
<html>
  <head>
    <title>李商隐</title>
  </head>
  <body>
    <h1 align="center">李商隐</h1>
    <hr width="80%" size="1" />
    <h2 align="center">锦瑟</h2>
    <p align="center">
      锦瑟无端五十弦，一弦一柱思华年。<br />
      庄生晓梦迷蝴蝶，望帝春心托杜鹃。<br />
      沧海月明珠有泪，蓝田日暖玉生烟。<br />
      此情可待成追忆，只是当时已惘然。
    </p>
  </body>
</html>
```

## （2）字体格式与列表

**字体格式**

- 强调标签（加粗）: `<b>  或者  <strong>`
- `<u>`：下划线标记
- `<s>`或`<del>`：中划线标记（删除线）
- `<i>`或`<em>`：斜体标记
- 上标`<sup>` 下标`<sub>`
- `<big>` 大号字体
- `<small>` 小号字体 

文字标签：`<font>`（不推荐）
	属性： 字体face	颜色color	字体大小size

**列表标签** 

（ordered 有序的  unordered 无序的   list 列表）  
**无序列表**`<ul>`(unordered list简写)： `<ul>  </ul>`  
	属性： type 设置列表项开始的符号，  
        取值：默认disc(实心圆)、circle（空心圆）、square(实心正方形)  
	列表项 `<li> </li>`

```html
<ul type=”disc|circle|square”>
  <li>List item 1</li>
  <li>List item 2</li>
</ul>
```

**有序列表**`<ol>`(ordered list 简写): `<ol> </ol>`  
	属性：type 设置列表项开始的符号，  
        取值：默认1,a,A,i,I  
		start 序号起始值(设置开始项)  
	列表项 `<li> </li>`

```html
<ol type="设置列表项开始的符号" start="序号起始值">
    <li> 第一项 </li>
    <li> 第二项 </li>
    <li> 第三项 </li>
</ol>
```

自定义列表`<dl>`(definition list简写)：`<dl>、<dt>、<dd> ` 
`<dt>` (definition title简写，定义标题)  
`<dd>`（definition description简写，定义描述)

```html
	<dl>
		<dt> 标题1 </dt> <dd> 注释1 </dd>
		<dt> 标题2 </dt> <dd> 注释2</dd>
		<dt> 标题3 </dt> <dd> 注释3</dd>
		<dt> 标题4 </dt> <dd> 注释4</dd>
	</dl>
```

**嵌套列表**

```html
<ol>
  <li>选择英雄：</li>
  <ul type="square">
    <li>坦克（项羽、程咬金等）</li>
    <li>法师（诸葛亮、貂蝉等）</li>
    <li>射手（后羿、孙尚香等）</li>
  </ul>
  <li>组队战斗！</li>
</ol>
```

**课堂案例**：嵌套列表-王者荣耀 (22页)

```

```

## （3）超链接

URL（Universal Resources Locator）用于定位Web上的文档信息。

一个 URL 包含3个组成部分：（http://www.xxx.com/a/b/c.html）

1. URL：计算机地址 www.xxx.com 
2. HTTP: 协议 (三次握手) http:// 
3. HTML （Hyper Text Markup Language）超文本标记语言 /a/b/c.html

   - ​    	由浏览器直接解释执行

   - ​    	不是编程语言、但是它是一门标记语言

   - ​    	标记语言是一套标记标签




- 相对URL、相对路径(相对当前文件)：/下一级 ./ 同一级 ../上一级 ../../上两级，比如：./boy.jpg

- 绝对URL、绝对路径（与当前文件无关）: 比如： https://www.xxx.com/xxx.jpg	http://www.xxx.com/xxx.mp3


**超链接**: `\<a>` 

```html
<a target="_blank" href="作业1.html"> 点击跳转到刚才的作业 </a>
```

属性：   
    **href: 跳转目标的URL地址（绝对地址、相对地址）**  
    target :在何处打开URL  
		默认值：_self  在自己页面打开  
		可选值：_blank 在新页面打开

```html
	<a target="_blank" href="作业1.html"> 点击跳转到刚才的作业 </a>
```

**课堂案例**：超链接-唐诗简介：（24页）

```

```

**锚点链接**

HTML锚点（Anchor）  
	通过`<a>`标签的href属性中的#加标识符（通常是ID）

创建HTML锚点  
	主要分为两步：  
	定义锚点目标（即跳转到的位置）和创建指向该目标的链接。

1. 定义锚点目标  
   通过给某个元素（如`<div>、<section>、<span>`等）添加一个唯一的id属性来实现的。    

   例如：

   ```html
   <div id="section1">这是第一部分的内容...</div>  
   <div id="section2">这是第二部分的内容...</div>
   ```
   
2. 创建指向锚点的链接  
   通过`<a>`标签的href属性来实现，其中href的值设置为#加上锚点的ID    

   例如：

   ```html
   <a href="#section1">跳转到第一部分</a>  
   <a href="#section2">跳转到第二部分</a>
   ```

**课堂案例-**锚点-李商隐：（26页）

```

```

**文件下载**

```html
<a href=xxx.zip>下载</a>
```

**Email**链接

```html
<a href="mailto:xxx@163.com">点击进入我的邮箱</a>
```

**课堂案例**：综合网站：唐诗宋词网站（30页）

```html
<html>
    <head><title>唐诗宋词-首页</title></head>
    <body>
        <p>&nbsp;</p>
        <h1 align="center"><a href="tangshi/tangshi.html">唐诗</a> | 宋词</h1>
        <hr size="1" width="80%">
        <p align="center"><img src="./images/theme.jpg" width="500"></p>
        <hr size="1" width="80%">
        <p align="center"><small>&copy;2020</small></p>
    </body>
</html>
```

# 三、CSS3基础

样式表， CSS3   
	**优势：**

1. 丰富的修饰样式   
2. 内容与修饰分离  
3. 样式复用   
4. 页面精确控制		 

## 语法：

 选择器  属性  属性值  
	基本语法：

```css
	<style>
		选择器 {
			属性1:属性值1;
			属性2:属性值2;
			......
		}
	</style>
```

```css
	<style>
		li {
			color:red;
			font-size:30px;
			font-family:隶书;
		}
	</style>
```

代码规范：语法规则  

1. 不区分大小写，推荐使用小写  
2. 每条样式规则用英文分号";"隔开  
3. 注释： Ctrl + /

## 样式表分类

根据书写位置分类，分为行内样式表，内嵌样式表（内部样式表），外部样式表(推荐使用)  
    **建议使用外部样式表**  

#### 行内样式表

​	行内样式表：**（对单独的标签有效）**  
​        在标签中加入style属性，对当前标签有效  
​        通用写法：  
​    	    <标签 style="样式属性:属性值;" > </标签>  
​	   	 <标签 style="属性:属性值;"> 标签内容 </标签>

```html
	<h1 style="color:red;font-family:隶书">
    <p style="color:red;font-size:30px;"> 通过使用CSS来提升工作效率！ </p>
	<hr style="border:2px dashed blue" />
	<p style="color:red;font-size:30px;">开始学习CSS！</p>
```

#### 	页内样式表

**内嵌(内部)样式表**：（**对当前页面有效**）  
​		 放在`<head> </head>`中，通过`<style>`标签定义  
​		 通用写法：

```html
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

```css
<head>
	<style>
		p {
			color:red;
			font-size:30px;
		}
		hr {
			border:3px dashed blue;
		}
	</style>
</head>
```

#### 站点样式表

**外部样式表**:通过link标签引入，或者用import导入

1. 放在 `<head>`标签里面，通过`\<link>`标签关联
2. 在 `<style>`标签里面用 @import（推荐使用）

```html
	<link rel="stylesheet" type="text/css" href="css文件路径">
```

或者

```html
	<style>
		@import "css文件路径" ;
	</style>
```

**块元素、行元素**

**HTML全局属性**

- id  唯一，不重复
- class
- style
- title
- lang

## CSS基本选择器

​    分为标签选择器（元素选择器）、类选择器、ID选择器

### 	标签选择器

（元素选择器）：标签名 {  }

​		<标签名>  标签内容  </标签名>

```css
	<style style="text/css">
		标签名 {
			属性1: 属性值1;
			属性2: 属性值2;
			......
		}
		
	<style>
```

```css
		li {
				color:blue;
				font-size:20px;
			}		
```

### class选择器

<标签名 class="类名">  标签内容  </标签名>

```css
	<style style="text/css">
		.类名 {
			属性1: 属性值1;
			属性2: 属性值2;
			......
		}
	<style>
```

```css
	.red {
			color:blue;
		}
```

### **ID选择器**：

- 同一页面ID名不能重复（唯一）。
- #id名 {  }
   	`<标签名 id="id名">  标签内容  </标签名>`

```css
	<style style="text/css">
		#ID名 {
			属性1: 属性值1;
			属性2: 属性值2;
			......
		}
	<style>
```

```css
	#header {
				background-color:yellow;
			}	
    #save {
				color: green;
				font-size:50px;
			}
```

### 组合选择器

CSS扩展选择器：组合选择器，包含选择器（后代选择器），交集选择器，伪类选择器
	组合选择器（并集选择器）：多个选择器之间用英文逗号","连接，对所有的选择器同时生效

```css
		h2, .p_class, #span_id {
						color:red;
            font-size:30px;
		}
```

### 伪类选择器

：根据标签处于某种行为或者状态来修饰样式   
    根据标签的状态来修饰样式

```css
标签名：伪类名 {
    属性:属性值;
}
```



```css
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

`:not()`伪类可以用于排除特定条件的元素。

```css
/*选择所有`<div>`元素，但排除`id`为`container`的元素*/
div:not(#container) {
    color: blue;
}
```

## 3类基本属性

### 颜色与背景属性

- color	颜色，取值可以为颜色的英文单词，也可以是十六进制符号#000000 - #FFFFFF之间
- background-color  背景颜色
- background-image (url(URL))  背景图片
- background-attachment (scroll/fixed)  背景附着
- background-repeat (no-repeat/repeat/repeat_x…)  平铺方式
- background-position (x,y) 背景定位
- background（以上5个属性的任意组合）

设置背景图片的尺寸：background-size属性
	background-size: 参数1 参数2;
	第一个值设置宽度，第二个值设置高度（单位px或者百分比）

```css
	background-size: 100% 100%;
```

背景附件
	用于设置 背景图片 是 可滚动的 还是 固定的 ;  
	前提是必须 提前设置 背景图片   
	语法如下 :  
	background-attachment : scroll | fixed   
		scroll : 背景图像 与 网页内容 绑定 , 网页滚动时 , 背景图像也进行滚动 ;  
		fixed : 背景图像 固定 , 滚动网页时 , 背景图像位置保持不变 ;  

### 字体属性

- font-family，取值为字体名称，字体类型
- font-weight 字体粗细, bold 加粗
- font-size 字体大小  (绝对大小/相对大小/长度值/百分比)   
-  font-style (normal/italic/oblique)
- font-weight (normal/bold/bolder/lighter/100/…)
- font-variant （normal/small-caps） 字体变体, small-caps小体大写
-  font ([ <'font-style'> || <'font-variant'> || <'font-weight'> ]? <'font-size'> [ / <'line-height'> ]? <'font-family'>)

```css
	p {
		font-weight:bold;
		font-size:30px;
		font-family:宋体;
        color:red;
	  } 
```

​			font 设置字体的所有样式属性(注意顺序)

```css
	p {
		/* 顺序不能变 */
		font: bold  30px 隶书 ;
	}
```



### 文本属性

- line-height (2em/200%/2)	设置行高，通常用来上下居中
- text-align (left/right/center/justify)	设置左右对齐方式
- text-decoration (none/underline/overline/line-through)	 设置文本修饰
- text-indent (2em)	段落的首行缩进
- letter-spacing 字符间距 
- text-transform 控制文本的大小写  
   	**取值：**  
   - none	默认。  
   - capitalize	以大写字母开头。  
   - uppercase	大写字母。  
   - lowercase	小写字母。    


```css
#max {
    background-color:pink;
    line-height:50px;
    /* height:50px; */
    text-align:left;
    letter-spacing:5px;
    text-decoration:underline;
    /* font-style:italic; */
}
```

# 四、图像

**Photoshop**

- 修改图像的大小
- 调整图像的颜色
- 修图-修复画笔/图章
- 抠图-主体/魔棒/椭圆
- 透明度

## 图片标签

图片标签(image)：`<img />` 空标签

```html
<img align="left" alt="这是李白的画像" src="images/libai.jpg" width="200px" />
```

​	属性：  

必须：  

- src (source 来源) 图片路径:  指定要插入的图像的文件名（包括路径）

  - 相对路径(相对当前文件)：./ 同一级 ../上一级 ../../上两级，比如：./boy.jpg

  - 绝对路径（与当前文件无关）: 比如： https://www.xxx.com/xxx.jpg  


- alt (alternate 备用的 ) 提示信息（图片不显示时替代显示）  


非必须： 

-  width 宽  height 高 
- border 边框(单位px)  

- align   相对于周围文本的对齐方式

  - left		把图像对齐到左边

  - right		把图像对齐到右边

  - middle(中间) 把图像对齐到中间

  - top(顶端)	把图像对齐到顶部

  - bottom(底部) 把图像对齐到底部

- hspace属性设置水平方向的空白

-  vspace属性设置垂直方向的空白

-  vertical-align 设置元素的垂直对齐方式，适用于行级元素、行块级元素。
   -  vertical-align: top | bottom | middle | baseline;


transform 属性向元素应用 2D 或 3D 转换。该属性允许我们对元素进行旋转、缩放、移动或倾斜。

## 音频标签

音频标签：`<audio>` 

音频标签： `<audio> </audio>`

IE8以及之前的版本不支持`<audio>`标签
属性： 
	必须的：  
			src  音频路径 
				相对路径（./当前目录（同一级） 上一级../ 下一级/）
                绝对路径 http://www.xxx.com/xxx.mp3
			controls 播放控件
	非必须的：autoplay 自动播放  loop 循环播放

第一种语法(单个音频来源)：

```html
	<audio src="音频/海阔天空.mp3" controls="controls" > 你的浏览器不支持audio！ </audio>
```

第二种语法(多个音频来源)：
   `<source>` 可选多个音频来源标签,默认选择第一个可用音频来源
    `<source src="xxx" />`   , 默认播放第一个支持的音频。

```html
	<audio controls="controls" > 
		<source src="音频/光辉岁月.mp3" type="audio/mp3" />
		<source src="音频/纸短情长.mp3" type="audio/mp3" />
        <source src="音频/海阔天空.wav" type="audio/wav" />
		你的浏览器不支持音频！ 
	</audio>
```

## 视频标签

视频标签：`<video>`		

视频标签：`<video> </video>`

IE8以及之前的版本不支持`<video>`标签
属性：   
	必须的： src 视频路径  
				绝对路径  
				相对路径：./ 当前目录  ../ 上级目录   
			controls 播放控件  
	非必须：  
        poster 视频加载时显示的图像（视频封面图像）  
        width 宽 height 高 (单位 px)  
		autoplay 自动播放  loop 循环播放  

第一种写法(单个视频来源):

```html
	<video poster="images/libai.jpg" width="500px"  src="视频/海阔天空60秒.mp4" controls="controls" > 你的浏览器不支持video标签！ </video>
	
    //绝对路径 
    <!-- <video controls="controls" src="https:www.xxx.com/xxx.mp4"  > 你的浏览器不支持video！</video> -->
    //相对路径 
    <!-- <video src="视频/海阔天空60秒.mp4" controls="controls" > 你的浏览器不支持video ! </video> -->
```

第二种写法(多个视频来源):  
	`<source src="xxx" />`  , 默认播放第一个支持的视频。  
	`<source>` 标签  
    有多个视频来源的时候，默认播放第一个支持的视频。

```html
	<video controls="controls">
		<source src="视频/光辉岁月60秒.ogg" />
		<source src="视频/海阔天空60秒.mp4" />
		你的浏览器不支持video! 
	</video>

  <video width="300px" poster="美女图片.jpg" controls="controls"  >
			<source src="视频/海阔天空60秒.mp4" type="video/mp4" />
			<source src="https:www.xxx.com/xxx.ogg" type="video/ogg" />
			你的浏览器不支持video!
	</video>
```

```html
		<video controls="controls">
			<source src="视频/黄家驹.ogg" type="video/ogg" />
			<source src="视频/测试视频.mp4" type="video/mp4" />  
			你的浏览器不支持！
		</video>
```

# 五、表格与表单

## 表格标签：

`<table></table>`  

表格标签：`<table> </table> 、<tr></tr>、<td></td>`  
主要由表格标签`<table>`、行标签`<tr>` (table row行)、单元格`<td>`标签构成。

`<table>`属性： 

- border 边框大小（单位px）  
	border-top|border-left|border-right|border-bottom	分别设置上、左、右、下边框大小
- width 宽 （单位px 或者屏幕的百分比） height (单位px)  
- bgcolor (background color简写) 背景颜色
- background 背景图片
- align 对齐方式（表格相对屏幕）
- cellspacing (cell单元 spacing间距)  单元格间距
- cellpadding (cell单元 padding填充、内衬)  单元格填充
- border-collapse    （separate|collapse)合并单元格边框
- text-align	内容对齐方式（内容相对单元格）
- valign	单元格内容垂直对齐方式（内容相对单元格）
- rules      用于控制表格内部的边框显示方式，取值 none|groups|rows|cols|all，HTML5已废弃
- frame     控制表格外边框的显示方式，取值 void|above|below|hsides|vsides|lhs|rhs|box|border，HTML5已废弃

`<td>`属性： rowspan 跨行(row span)   colspan 跨列(column span)  
		width 宽 （单位px） bgcolor (background color简写) 背景颜色  
        background 背景图片  
		align 对齐方式 （内容相对单元格）
	布局：`<td>`里面可包含table
	
表格`<table>`中的其他标签：
	`<caption>` 表格标题  （caption 说明文字）
	`<th>` 定义表头 （td改成th 加粗并且居中）



## 表单标签： 

`<form> </form>`

属性：
	必须的属性：  
            name :表单名称  
			action : 提交的url  
			method : 提交方式 默认get，通常可选：get 、post  
				get、post方法的主要区别：
					安全性：
						get方式提交时，表单信息会出现在地址栏（提交的参数附加在URL后面）。
						但是post方式不会出现在地址栏。
					提交数据长度：
						get方式提交的数据有长度限制，但是post提交数据没有长度限制（上传文件建议用post）

```	html
	<form name="表单名称" action="提交的URL" method="提交方式（get/post）" > 
		表单元素
	</form>
```

表单元素概述：
    表单元素介绍：大部分使用input标签，只是属性不同  
    属性介绍  
	`<input>`属性：  
        type  表单控件类型，  
            默认text， password checkbox radio submit reset file hidden image button   
        name 表单元素名称  
        value 初始值  
        size  表单元素的初始宽度  
        placeholder 输入框的提示文本  
        maxlength 在text、password中输入的最大长度，默认无限制  
        checked 是否选中（默认不选中）  
        readonly 不能编辑 

```html
	<input name="表单元素名称" type="类型" value="初始值" size="显示宽度" maxlength="能输入的最大字符长度" checked="是否选中" >
```
```html
	<input name="表单元素的名称" type="类型" value="值" size="显示宽度" maxlenth="能输入的最大长度" checked="是否选中" />
```
```html
	<input type="类型" name=“名称” value=“初始值“ size="显示宽度" maxlength="输入的最大长度" checked="是否选中" >
```
常用的表单控件标签：
		单行文本输入框：`<input type="text">`
		密码输入框（*******）：`<input type="password">`
		表单提交按钮`<input type="submit">`
		单选：`<input type="radio">`
		多选：`<input type="checkbox">`复选框
		下拉选框： `<select>`
		多行文本输入框： `<textarea>`多行文本域

输入框： 

单行文本框：

```html
	<input name="表单元素名称" type="text" value="初始值" id="表单元素名称" >
	<input type="text" name="username" id="username" size="100" value="这是初始值">
```
密码框：
	`<input name="password" type="password" >`
多行文本域： `<textarea>` (text area) 
	属性：cols 设置列数  rows 设置行数  name名称

```html
<textarea rows="行数" cols="列数" name="名称" >文本</textarea> 
```
​		不能设置初始值value

```html
	<textarea cols="100" rows="20" name="textarea">
		多行文本
	</textarea>
```

按钮：（分为提交按钮、重置按钮、普通按钮）

属性： disabled="disabled" （禁用按钮）
提交按钮：提交表单数据

```html
	<input type="submit" name="名称" value="按钮显示的初始值">
    <input type="submit" name="submit" value="点击注册">
```
重置按钮：清空现有表单数据

```html
	<input type="reset"  name="名称" value="按钮显示的初始值">
    <input type="reset" value="点击清空表单" name="reset">
```
普通按钮：一般用于调用JavaScript脚本, value初始值

```html
	<input type="button"  name="名称" value="按钮显示的初始值" >
```
```html
	<input type="button" value="点击查看协议" name="button">
```
```html
	<input onclick="alert('有人没听课')" type="button" name="bt" value="点击提交">
	<input type="button" value="这是按钮，点击起飞" name="button"> 
```
图片按钮:（提交按钮）type="image"

```html
	<input type="image" src="图片路径" alt="提示信息" name="名称" >

	<input type="image" src="nz.jpg" alt="这是哪吒" name="imageSubmit" width="50" height="50px" >
```

单选、多选、下拉选框

单选按钮：1、type="radio" 2、同一组单选有相同的name 3、value值不能少
    语法：
    `<input type="radio" name="同一组有相同的名称">`
	默认选中： checked="checked" 

```html
	  男：<input type="radio" name="gender" value="boy">
	  女：<input type="radio" name="gender" value="girl">	 
      未知 <input   type="radio" name="gender" value="unknown">
```
多选框：将单选的radio改成checkbox
    `<input type="checkbox" name="同一组有相同的名称">`
	默认选中：checked="checked" 或者 checked

```html
	<input type="checkbox" name="fruit" value="apple">苹果
	<input type="checkbox" name="fruit" value="orange">橘子
	<input type="checkbox" name="fruit" value="banana">香蕉
```
下拉选框：`<select>`

- ​	属性：size 默认显示的行数    multiple="multiple" 下拉变成多选
- ​	默认选中： selected="selected"	

```html
	<select name="chongqing_snack" size="1">
		<option>--请选择你喜欢的小吃--</option>
		<option value="hotpot"> 火锅 </option>
		<option value="small_noodle"> 小面 </option>
		<option value="ciba"  selected="selected"> 糍粑 </option>
		<option valu="meat" > 腊肉 </option>
	</select>
```

表单验证：
	必填验证： required  或者 required="required"

```html
	<input required="required" type="text" name="account"> *
```
类型匹配验证：email（邮箱） url(网址) number(数字) range(范围) date(日期) 
	邮箱类型：type="email"

```html
	<input type="email" name="email">
```
​	url类型：type="url"

```html
	<input type="url" name="url_validate" >
```
​	number类型：数字验证 type="number"

```html
	<input type="number" name="number_validate">
```
​	date类型：日期验证 type="date" 

```	html
	<input type="date" name="date_validate">
```
​    range类型(范围): 滑动条，配合min max step（步长）
​		属性： min  max  step

```html
	<input type="range" step="5" min="10" max="100" name="range">
```
​	控制字符数量: 输入字符的最大长度
​		maxlength = "最大长度"

```html
	<input type="text" maxlength="11" name="phone">
```
​	验证输入范围： 配合min（最小值） max（最大值） step（步长，每次增加或者减少的值）

```html
	<input type="number" min="10" max="100" step="6">
```
​	自定义错误消息：
​    oninvalid（当用户输入不合法）:
​		oninvalid="setCustomValidity('提示的信息')"  (on invalid set custom validity)

```html
	<input oninvalid="setCustomValidity('亲爱的! 你的账号必须填写哦!')" required="required" type="text" name="account"> *
```
```html
	<input type="number" min="1" max="100" oninvalid="setCustomValidity('亲,年龄不能超过100哦!')">
```
​        oninput(当用户正常输入)
​        oninput="setCustomValidity('自定义消息')"
​		oninput="setCustomValidity('')" 

```html
	年龄：<input oninput="setCustomValidity('')" oninvalid="setCustomValidity('亲!你的年龄过大了,这边不建议你浏览本网站哦!')" type="number" min="1" max="70">
```

对表单控件分组：

`<fieldset>` 标签可以将表单内的相关元素分组。

`<fieldset>` 标签会在相关表单元素周围绘制边框。

 `<legend>` 元素为`<fieldset>`元素定义标题。

# 六、CSS3提高

## （1）CSS3高级选择器

包含选择器（后代选择器）：选择器之间用空格" "连接。对最后代的选择器生效
	用于选择后代元素，通常外层的标签为父标签，内层的标签为子标签。

```css
	#header ul li a {
    color: gold;
  }
```
交集选择器: 由两个选择器构成，第一个必须是标签选择器，第二个必须是类选择器或者ID选择器。
	    两个选择器必须连续书写。
        ``p.class { }`
	    h1#id { }`

```css
	p.class {
				color:green;
			}
```
子代选择器：选择器之间用大于号" > "连接。对子代的选择器生效
	用于选择子元素，通常外层的标签为父标签，内层的标签为子标签。

```css
	#header > ul > li > a {
    color: gold;
  }
```
相邻兄弟选择器：选择器之间用加号" + "连接。对相邻兄弟的选择器生效
	用于选择紧接在另一元素后的元素，且二者有相同父元素。
	相邻兄弟选择器只能选择紧接在另一元素后的元素，如果要选择所有兄弟元素，请使用一般兄弟选择器。

```css
	#header ul li + li a {
    color: gold;
  }
```

属性选择器（Attribute Selector）：用于选取带有指定属性的元素。
通过元素的属性选择 HTML 元素。
如下代码，**input[type="text"]** 选择器将选择所有 **type** 属性为 **"text"** 的 `\<input>` 元素。

```css
input[type="text"] {
  border: 1px solid gray;
}
```

| 选择器             | 示例            | 示例说明                                 |
| ------------------ | --------------- | ---------------------------------------- |
| [attribute]        | [target]        | 选择所有带有target属性元素               |
| [attribute=value]  | [target=-blank] | 选择所有使用target="-blank"的元素        |
| [attribute~=value] | [title~=flower] | 选择标题属性包含单词"flower"的所有元素   |
| [attribute^=value] | a[src^="https"] | 选择每一个src属性的值以"https"开头的元素 |
| [attribute$=value] | a[src$=".pdf"]  | 选择每一个src属性的值以".pdf"结尾的元素  |

## 

## （2）盒子模型

1盒子模型原理 2标准文档流 3盒子浮动 4盒子定位  
	一、盒子模型原理：
		1盒子模型概述 
			每个HTML元素都可以看作一个盒子。
            包含内容content 填充padding 边框border 边距(边界) margin
            填充 边框 边距包含top上、bottom下、left左、right右四部分

### 边距和填充：

- 边距（margin、外边距、外补丁）：围绕在元素边框的空白区域
- 填充(padding、内边距、补白、内补丁)：定义元素边框与元素内容之间的空白区域。

​    边距：
​	单独设置边距：

- ​		margin-top  上边距
- ​		margin-left  左边距
- ​		margin-right  右边距
- ​		margin-bottom  下边距

```css
	margin-top:20px;
	margin-right:30px;
	margin-bottom:40px;
    margin-left:20px;
```

​	也可以通过复合属性设置边距：
​		仅设置一个值，则应用四个边距。

```
	margin: 30px;	
```

​	设置两个值，则表示上下边距、左右边距。

```
	margin:10px 20px;
```

​	设置三个值，则表示上边距、左右边距、下边距。

```
	margin:10px 20px 30px;
```

​	设置四个值，则表示上边距、右边距、下边距、左边距。(顺时针)

```css
	margin:10px 20px 30px 40px;
```

​	填充(padding、内边距、补白、内补丁)：定义元素边框与元素内容之间的空白区域。  
​		单独设置填充：  

- ​			padding-top  上填充
- ​			padding-left  左填充
- ​			padding-right  右填充
- ​			padding-bottom  下填充

```css
	padding-top:20px;
	padding-left:30px;
	padding-bottom:40px;
	padding-right:50px;
```

也可以通过复合属性设置填充：  
		仅设置一个值，则应用四个填充。

```
	padding: 30px;	
```

​	设置两个值，则表示上下填充、左右填充。

```css
	padding:10px 20px;
```

​	设置三个值，则表示上填充、左右填充、下填充。

```
	padding:10px 20px 30px;
```

​	设置四个值，则表示上填充、右填充、下填充、左填充。(顺时针)

```css
	padding:10px 20px 30px 40px;
```

​				

### 	盒子的大小   

​		计算方法：  
​		盒子实际大小：边框+填充+内容（不算边距）  
​			盒子实际宽度：左边框+左填充+内容宽度+右填充+右边框（不算边距）
​			盒子实际高度：上边框+上填充+内容高度+下填充+下边框（不算边距）  
​								
​		盒子占据空间大小: 盒子实际大小+边距  
​			盒子占据宽度：盒子实际宽+左边距+右边距  
​            盒子占据空间的宽度：左边距+左边框+左填充+内容宽度+右填充+右边框+右边距  
​            
​			盒子占据高度：盒子实际高+上边距+下边距  
​            盒子占据空间的高度：上边距+上边框+上填充+内容高度+下填充+下边框+下边距

```
- 长宽：300*300 px 

- 边框：10px 

- 填充：上下10px 左右20px 

- 边距：10px

  
- ​	盒子的实际宽度：10px + 20px + 300px +20px+10px=360px 
- 盒子实际高度：上边框+上填充+内容高度+下填充+下边框（不包含边距）
- 盒子的实际高度：10px + 10px +300px + 10px + 10px = 340px 
  ​	
  ​	盒子所占据的空间：
  ​	盒子所占据的宽度：360px + 30px + 30px=420px
  ​	盒子所占据的高度：340px + 60px = 400px
```



```html
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

​	3盒子之间的关系:  

- ​		垂直盒子:  

​            边距取margin-bottom和margin-top的最大值 (合并)

- ​		水平盒子： 

​            边距取margin-left和margin-right的之和（不合并）

- ​		重叠盒子： 

​			边距margin设置为负值
​			margin可以是负数，但是border和padding不能是负数。

```css
	margin-left:-50px;
```

## 

## （3）CSS3布局

`<div>` 标签： （division简写 分开、分界）

1. 没有特定含义，只是作为组合其它HTML元素的容器
2. div标签默认独占一行（当存在多个div标签时，从上到下的方式排列）
3. 如果与 CSS 一同使用，`\<div>` 元素可用于对大的内容块设置样式属性。
4. `<div>` 元素的另一个常见的用途是文档布局。它取代了使用表格定义布局的老式方法。使用 `\<table>` 元素进行文档布局不是表格的正确用法。`\<table>` 元素的作用是显示表格化的数据。
5. 可以用 id 或 class 来标记 `<div>` （页面中每个标签的id不能相同,class可以相同）

`<span>`标签： span (跨度、范围)

1. 没有特定含义，可作为文本的容器
2. 多个span标签可以存在于同一行（从左到右的方式排列）
3. 当与 CSS 一同使用时，`\<span>` 元素可用于为部分文本设置样式属性。

### 标准文档流

（普通流、标准流）：

​    1概述：浏览器根据从左到右，自上而下的规则排列HTML元素

​    	标签排列规则：从左到右，自上而下。

**块元素：**`标题(<h1> - <h6>) 段落(<p>) 水平线(<hr />) 列表(<ul>、<ol>、<li>等) 表格(<table>) 层（<div>）表单(<form>)`  
		
**行元素：**`图片(<img>) 范围（<span>） 换行(<br />)  超链接(<a>) `   
		
		块元素和行元素的区别  
			1排列方式不同
            	块元素独占一行，自上而下排列。
				行元素从左到右，多个行元素可显示在同一行。
			2内嵌元素不同
				块元素可以包含块元素和行元素，
                但是行元素只能包含文本或者其他行元素。
			3属性设置不同
				块元素可以设置所有样式属性, 但是行元素不能设置width属性、height属性。
				行元素可以设置line-height，不可以设置上下边距，上下填充。（行元素margin、padding上下方向无效）
	
	2 diplay属性 
		display: none | block | inline;
        控制是否存在。 none 隐藏（消除）该元素，不占屏幕空间。若有其他元素，会上移到该区域。

取值及用途

**`none`**

- **描述**：将元素隐藏，不显示。
- **特点**：
  - 元素不会占用空间，不会影响页面布局。

**`block`**

- **描述**：将元素显示为块级元素。
- **特点**：
  - 块级元素独占一行，宽度默认占满父元素的宽度。
  - 可以设置宽度（`width`）和高度（`height`）。

**`inline`**

- **描述**：将元素显示为内联元素。
- **特点**：
  - 内联元素不会独占一行，多个内联元素可以在同一行显示。
  - 不能设置宽度和高度。

**`inline-block`**

- **描述**：将元素显示为内联块级元素。
- **特点**：
  - 内联块级元素不会独占一行，多个内联块级元素可以在同一行显示。
  - 可以设置宽度和高度。

```css
#middle {
    display: none;
    display: block;
}
```
​	3 visibility属性
​		visibility: hidden | visible; 
​			只是控制是否可见，实际上还是存在,占据屏幕空间。

```css
visibility: visible;
visibility: hidden;
```

3 盒子浮动：
	float属性 
		float:none,left,right 
			left 移动到父元素左侧
			right 向上级元素右边浮动
			none 默认，不浮动

```css
float: none;
float: left ;
```

清除浮动
	浮动的副作用
		背景不能显示
		边框不能撑开
		margin padding不能正确显示

**清除浮动影响的方法**
1 对父级元素设置宽高

```css
#max {
    width: 800px;
    height:300px;
}
```
2 clear:both清除浮动
​		在父级`</div>`结束前加上`<div class="clear"> </div>`

```css
.clear {
    clear: both;
}
```
3 在父级div定义 overflow:hidden;

```css
#max {
    overflow:hidden;
}
```

### 盒子定位

​	1 静态定位
​        默认，按照标准文档流，HTML元素从左到右，自上而下排列。

```css
	position: static;
```
​	2 相对定位
​        从原来的位置移动到一个相对位置。参考点：左顶点
​		占据原来的空间。

```css
	position:relative;
	top:50px;
	left:150px;
```
​	3固定定位
​        相对于浏览器窗口定位。

```css
	position:fixed;
	top:200px;
	left:200px;
```
​	4绝对定位
​        相对于最近的一个已定位的“祖先”元素(即非static定位的元素)进行定位。如果没有，则相对于浏览器左上角（body）。    
		脱离文档标准流。不占据空间。可以将指定标签放到任意绝对坐标位置。

```css
	position:absolute;
	top:200px;
	left:200px;
```
​    5 z-index属性，设置元素堆叠顺序
​		必须先设置定位。
​		z-index:数字; 数字越大，越靠前

```css
    z-index:13;
```

页面布局（table布局 或者 div+css布局）
​    1表格布局 2流式布局 3 div布局 4div高级

div居中：
	首先设置宽度width属性

```css
	width: 200px; 
	margin: 0px auto;
```

文字居中：
	水平居中：text-align:center;
	垂直居中：line-height:高度值; 

```css
	line-height:50px;
```

重置样式

目的是消除不同浏览器默认样式之间的差异，从而确保网页在不同浏览器中具有一致的布局效果。

将所有HTML元素的`margin`和`padding`属性设置为`0px`。

清除浏览器白边

```css
	* {
		margin:0px;
		padding:0px;
	}
```



## （4）CSS高级属性

### cursor属性

设置当鼠标指针位于元素上方时所显示的样式

`cursor: value;`

**常用值**

| 值              | 描述                                                   |
| :-------------- | :----------------------------------------------------- |
| `auto`          | 默认值，浏览器根据元素的上下文自动选择光标样式。       |
| `default`       | 普通光标（通常是箭头）。                               |
| `pointer`       | 指针光标（通常是手形），表示可点击。                   |
| `wait`          | 等待光标（通常是沙漏或旋转的圈），表示正在加载或等待。 |
| `text`          | 文本选择光标（通常是竖线），表示可以编辑文本。         |
| `move`          | 移动光标（通常是十字箭头），表示可以移动对象。         |
| `not-allowed`   | 不允许光标（通常是斜杠圆圈），表示操作不被允许。       |
| `help`          | 帮助光标（通常是问号或气泡），表示可以获取帮助。       |
| `crosshair`     | 十字准线光标，通常用于绘图或选择区域。                 |
| `vertical-text` | 垂直文本选择光标。                                     |
| `alias`         | 表示正在创建别名或快捷方式。                           |
| `copy`          | 表示可以复制内容。                                     |
| `no-drop`       | 表示不能在此处放置拖动的内容。                         |
| `grab`          | 表示可以抓取对象。                                     |
| `grabbing`      | 表示正在抓取对象。                                     |
| `e-resize`      | 表示可以水平向右调整大小。                             |
| `w-resize`      | 表示可以水平向左调整大小。                             |
| `n-resize`      | 表示可以垂直向上调整大小。                             |
| `s-resize`      | 表示可以垂直向下调整大小。                             |
| `nw-resize`     | 表示可以向左上角调整大小。                             |
| `ne-resize`     | 表示可以向右上角调整大小。                             |
| `sw-resize`     | 表示可以向左下角调整大小。                             |
| `se-resize`     | 表示可以向右下角调整大小。                             |
| `url`           | 自定义光标，可以指定一个光标图像的URL。                |

### 

### 列表属性

​	1列表属性 2垂直菜单  

**列表属性：**    

**1. `list-style-type`**

`list-style-type` 属性用于指定列表项标记的类型

**常用值**

- `none`：不显示列表项标记。
- `disc`：使用实心圆点（默认值）。
- `circle`：使用空心圆点。
- `square`：使用实心方块。
- `decimal`：使用数字（1, 2, 3, ...）。
- `lower-roman`：使用小写罗马数字（i, ii, iii, ...）。
- `upper-roman`：使用大写罗马数字（I, II, III, ...）。
- `lower-alpha`：使用小写英文字母（a, b, c, ...）。
- `upper-alpha`：使用大写英文字母（A, B, C, ...）。

**2. `list-style-position`**

`list-style-position` 属性用于指定列表项标记的位置。

**常用值**

- `inside`：列表项标记位于内容内部。
- `outside`：列表项标记位于内容外部（默认值）。

**3. `list-style-image`**

`list-style-image` 属性用于指定自定义的列表项标记图像。

```css
ul {
    /* list-style-type:circle; */
    list-style-image: url(images/arrow.png);
    list-style-position:inside;
}
li {
	border:red 4px solid;
	/* margin-left:80px; */
	/* list-style-type:none; */
	/* list-style-image: url(images/aa.jpg); */
	list-style-position:outside;
}
```

**4. `list-style`**

`list-style` 是一个复合属性，可以同时设置 `list-style-type`、`list-style-position` 和 `list-style-image`。

```css
ul {
  	list-style:circle inside url(images/arrow.png);
}
```

​	

### 边框属性

​	1 border属性 2 border-radius属性  
1 border属性  
​	单独设置边框样式：
​        border-style 设置边框样式：none无边框，solid实线, dashed 虚线,double
​		boder-width 设置边框宽度 
​		border-color 设置边框颜色

```css
	border-style:solid;
	border-width:20px;
	border-color:green;
```

​		也可以通过复合属性设置边框全部样式：

```css
		border:10px red dashed ;
```

2 border-radius属性，设置边框圆角

​	语法：`border - radius: value;`

​		value值越大，圆角效果越明显。

- **长度值**：像 `10px`、`2em` 这种，明确指定圆角的半径大小。
- **百分比**：例如 `50%`，通常用于创建圆形或椭圆形元素。

​	border-radius:参数1，四个角

```css
border-radius:55px;
```

​	border-radius:参数1 参数2
​        参数1对应 左上角 右下角
​		参数2对应 左下角 右上角

```css
border-radius:20px 40px;
```

​	border-radius:参数1 参数2 参数3

- ​        参数1对应 左上角
- ​        参数2对应 左下角 右上角
- ​        参数3对应 右下角

```css
border-radius:20px 40px 60px;
```

border-radius:参数1 参数2 参数3 参数4 (顺时针)

- ​    参数1  左上角
- ​    参数2  右上角
- ​    参数3  右下角
- ​    参数4  左下角

```css
	border-radius:20px 40px 60px 80px;
```

背景和阴影  

### 背景属性

​	1背景颜色 2背景图片 3背景图片的重复方式（平铺）  
1背景颜色   
​			background-color 设置背景颜色  
​				颜色:英文单词、 16进制、 rgb(red, green, blue)

```css
	background-color: lightgrey;
```

2背景图片
​        如果同时有背景颜色，优先显示背景图片。
​		background-image:url(图片地址)

```css
	background-color:rgb(255, 254, 66);
	background-image:url(images/girl.jpg)
```

3背景图片的重复（平铺）方式    
​        background-repeat:属性值，  

-   repeat（默认，水平垂直同时平铺） no-repeat 不平铺 
-   repeat-x 水平平铺
-   repeat-y 垂直平铺

```css
	/* background-color:blue; */
	background-image:url(images/aa.jpg);
	background-repeat:repeat-x;
```

多张背景图片：

```css
		background-image:url(images/aa.jpg),url(images/girl.jpg);
		background-repeat:repeat-y, no-repeat;
```

背景图片的定位：1 background-position属性 2 CSS Sprites  
1 background-position属性 ：  
	background-position:关键字，百分比，像素值  
		关键字：
            水平方向：left center right;
            垂直方向：top center bottom
		百分比：
            水平方向：
                从左到右0%-100%，
                0% 50% 100%对应左中右；
            垂直方向：
                从上到下0%-100%，
                0% 50% 100%对应上中下；
		像素值: 图片左顶点相对于上级元素的左顶点。 
            正数时：水平向右，垂直向下，
            负数时：水平向左，垂直向上

```css
	background-image:url(images/aa.jpg);
	background-repeat: no-repeat;
	/* background-position:center center; */
	background-position:-50px -50px;
	/* background-position:center center; */
	/* background-position:50% 50%; */
	/* background-position:500px 300px; */
		background-position:-50px -50px;
```

设置多个背景图片属性

```css
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

2 CSS Sprites (雪碧图，精灵图)

```css
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

### 背景渐变

​	1线性渐变  2径向渐变  
1线性渐变：  
​        background:linear-gradient(参数1（角度或者方向），参数2（颜色），参数3（颜色）...)
​		参数1的角度是指渐变线与水平线之间的角度。

```css
	background:linear-gradient(45deg,red,pink,blue);
	background:linear-gradient(to right,red,blue);
	background:linear-gradient(to right bottom,red 40%,white,black)
```

//todo
	透明度渐变  
	rgb(red,green,blue)设置颜色, red green blue取值0-255或者百分比
	rgba(red,green,blue,alpha(透明度) ),设置颜色并使用透明度,alpha取值0-1

```css
	background:linear-gradient(to right,rgba(255, 255, 255, 0),rgba(255, 255, 255, 0.6)),url(images/aa.jpg);
```

​	重复线性渐变：

​	background: repeating-linear-gradient(参数1（角度或者方向），参数2（颜色），参数3（颜色）.。。)        

```css
background:repeating-linear-gradient(-45deg,red,blue 30px);
```

2径向渐变：
	background:radial-gradient(参数1（形状或者圆心位置），参数2（颜色），参数3（颜色）。。)

```css
background:radial-gradient(red,pink,blue,black)
```

​	重复径向渐变：

```css
background:repeating-radial-gradient(circle, red 10px,blue 50px);
```

## 

### 阴影属性

​	1文字阴影 2盒子阴影  
1文字阴影  

`text-shadow:h-shadow v-shadow blur color;`

- h-shadow 阴影水平距离（必须） 
- v-shadow阴影垂直距离（必须） 
- blur阴影半径 
- color阴影颜色

```css
text-shadow:10px 10px 5px red;
```

2盒子阴影  

`box-shadow: [h-shadow v-shadow blur spread color inset ]+`

- h-shadow阴影水平距离（必须） 
- v-shadow阴影垂直距离（必须） 
- blur阴影半径/模糊半径
- spread阴影大小 
- color阴影颜色
- **`inset`**：向内投影。如果不指定 `inset`，则阴影默认向外投影。

```css
box-shadow:10px 10px 20px 20px blue;
```

### 过渡效果

基本语法:

```css
transition: [property] [duration] [timing-function] [delay];
```

- **`property`**：指定需要过渡的CSS属性名称。可以是单个属性，也可以是多个属性（用逗号分隔），或者使用 `all` 表示所有属性。
- **`duration`**：指定过渡效果的持续时间，单位通常是秒（`s`）或毫秒（`ms`）。
- **`timing-function`**：指定过渡效果的时间曲线，常见的值有：
  - `ease`（默认值，平滑的加速和减速）
  - `linear`（匀速）
  - `ease-in`（加速）
  - `ease-out`（减速）
  - `ease-in-out`（先加速后减速）
  - `cubic-bezier(n,n,n,n)`（自定义贝塞尔曲线）
- **`delay`**：指定过渡效果的延迟时间，单位通常是秒（`s`）或毫秒（`ms`）。默认值为 `0`。

```css
 /*当鼠标悬停在 .box 元素上时，元素的宽度、高度和透明度会同时开始过渡，过渡时间为 0.5 秒，延迟 0.2 秒，并且以匀速进行。*/.

.box {
    width: 100px;
    height: 100px;
    background-color: red;
    opacity: 1;
    /* 对宽度、高度和透明度属性应用过渡效果，持续时间为 0.5 秒，使用匀速过渡，延迟 0.2 秒 */
    transition: width 0.5s linear 0.2s, height 0.5s linear 0.2s, opacity 0.5s linear 0.2s;
}

.box:hover {
    width: 200px;
    height: 200px;
    opacity: 0.5;
}
```

**CSS的特性：**1 继承性 2 层叠性和优先级  
	 **继承性：**

- 内层继承外层样式,但另行更改除外。  
- 某些特殊情况不继承，比如边框border

 **层叠性：**

1.  如果多个选择器定义的样式不发生冲突，则应用全部选择器定义的样式。
2.  如果多个选择器定义的样式发生冲突，则按照选择器的优先级来处理。

## (5)样式的优先级

**基本原则**：就近优先：style属性 > style标记符 > link标记符

```css
<html>
<head>
    <link rel="stylesheet" type="text/css" href="test.css" />
    <style>
    	p {color: red;}
    </style >
</head>
<body>
	<p style="color:blue;">正文内容</p>
</body>
</html>
test.css p{color:green;}
```

 **优先级：**

- ​	优先级的总原则：越特殊的样式，优先级越高。

- ​	选择器的优先级：

  ​	        ID选择器 > 类选择器 > 标签选择器(元素选择器)

- ​	样式表的优先级：  

  ​		行内样式表 >  内嵌(内部)样式表 > 外部样式表 		

## 

# 第7章 Javascript与前端开发技术

详见JavaScript文档

# 第8章 网页设计基础

# 第9章 使用Dreamweaver

# 第10章 综合项目实践