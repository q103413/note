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
