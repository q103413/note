
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