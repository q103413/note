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
		line-height 设置行高
		text-align 设置对齐方式: left center right
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
