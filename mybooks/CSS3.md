
CSS : 样式表， CSS3 
    优势：1 丰富的修饰样式
         2 内容与修饰分离
         3 样式复用 
         4 页面精确控制
        
    基本语法： 选择器 属性 属性值
        基本语法：
        <style>
            选择器 {
                属性1:属性值1;
                属性2:属性值2;
                ......
            }
        </style>
```
    <style>
        li {
            color:red;
            font-size:30px;
            font-family:隶书;
        }
    </style>
```

​    代码规范：1 不区分大小写，但是推荐小写
​            2 每条样式用英文分号";"隔开
​            3 注释：Ctrl + /
​            
样式表分类：根据书写位置分类，分为行内样式表，内嵌样式表（内部样式表），外部样式表
​    建议使用外部样式表
​    行内样式表：在标签中加入style属性，对当前标签有效
​        <标签 style="属性:属性值;"> 标签内容 </标签>
```
    <p style="color:red;font-size:30px;"> 通过使用CSS来提升工作效率！ </p>
    <hr style="border:3px dashed red;" />
    <p style="color:red;font-size:30px;"> 开始使用CSS！ </p>
```
​    内嵌样式:放在<head>标签里面，通过<style>标签定义
```
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
​    外部样式表：
​        1 放在<head>标签里面，通过<link>标签关联
​        2 在<style>标签里面用 @import
```
    <link rel="stylesheet" style="text/css" href="css/style.css"  />
```
​    或者
```
    <style>
        @import "css/style.css"
    </style>
```

CSS基本选择器：分为标签选择器（元素选择器）、类选择器、ID选择器
    标签选择器（元素选择器）：  标签名 { }
        <标签名>  标签内容 </标签名>
```
        li {
                color:blue;
                font-size:20px;
            }       
```
​    类选择器： 1 类名可以重复  2 .类名 { }  
​        <标签名 class="类名">  标签内容 </标签名>
```
    .red {
            color:blue;
        }
```
​    ID选择器：1 id名不能重复  2 #id名 { }
​        <标签名 id="id名">  标签内容 </标签名>
```
    #header {
                background-color:yellow;
            }   
```

CSS 扩展选择器：分为组合选择器，包含选择器（后代选择器），交集选择器，伪类选择器。
    组合选择器（并集选择器）：多个选择器用英文逗号","连接，同时生效
```
h3,.p_class,#span_id {
                        color:red;
                    }
```
​    包含选择器（后代选择器）：多个选择器用空格" "连接，对后代生效
​        通常称外层标签叫父标签，内层标签叫子标签。
```
#middle ul li a {
                    color:green;
                }
```
​    交集选择器：由两个选择器构成，第一个选择器必须是标签选择器，第二个选择器必须是类选择器或者ID选择器。
​             必须连续书写。
```
    p.save {
                color:red;
            }
```
​    伪类选择器：根据标签的状态来修饰样式
​        标签名:伪类名 { }
```
<style>
        /* 未单击 */
        a:link{
            color:red;
        }
         /* 单击之后 */
        a:visited {
            color:pink;
        }
        /* 鼠标悬浮 */
        a:hover {
            color:green;
            font-size:30px;
        }
        /* 单击未释放 */
        a:active {
            color:orange;
        }
</style>
```

CSS的特性：1继承性 2层叠性和优先级
    继承性： 内层继承外层, 另行更改除外。 
            特殊情况不继承，比如边框border。
    
    层叠性：
        1 当多个选择器定义的样式不发生冲突，应用所有选择器定义的样式。
        2 当多个选择器定义的样式发生冲突，按照选择器的优先级来处理。
            优先级：ID选择器　> 类选择器 > 标签选择器（元素选择器）
        样式表的优先级：行内样式 > 内嵌样式表（内部样式表) > 外部样式表
            总原则：越特殊的样式，优先级越高
            
常用的样式属性：
    字体与文本属性
    字体属性：
            font-weight 字体粗细： bold 加粗
            font-size 字体大小  
            font-family 字体类型  
            color 字体颜色，取值颜色的英文单词，或者十六进制符号#000000-#FFFFFF
```
        <style>
            p {
                font-weight:bold;
                font-size:30px;
                font-family:宋体;
                color:red;
            }
        </style>
```
​        font 设置字体的所有样式属性(注意顺序)
```
        p {
            font:bold 50px 隶书;
        }
```

​    文本属性：
​            line-height 设置行高 
​            text-align 对齐方式：left right center
​            letter-spacing 字符间距 
​            text-decoration 设置文本修饰: underline(下划线)、none、line-through、overline
```
        <style>
            .hot {
                background-color:pink;
                /* height:50px; */
                line-height:50px;
                text-align:center;
                letter-spacing:5px;
                text-decoration:line-through;
            }
        </style>
```

边距和填充：
        边距(margin)：标签与标签的距离
        
        单独设置边距：
            margin-top  上边距
            margin-left 左边距
            margin-right 右边距
            margin-bottom  下边距
```
     margin-bottom:30px;
     margin-right:50px; 
     margin-top:20px;
     margin-left:50px; 
```
​        通过复合属性设置边距：
​        仅设置一个值，则应用与四个边距：
```
    margin:20px;
```
​        设置两个值，则表示上下，左右边距：
```
    margin:10px 20px;
```
​        设置三个值，则表示上边距，左右边距，下边距
```
    margin:10px 20px 30px;
```
​        设置四个值，则表示上边距，右边距，下边距，左边距(顺时针)
```
        margin:10px 20px 30px 40px;
```

​        填充(内边距,补白，padding)：标签与标签内容的距离
​            单独设置填充：
​                padding-top     上填充
​                padding-left    左填充
​                padding-right   右填充
​                padding-bottom  下填充
```
    .big {
            border: 2px solid #0000FF;
            /* padding-top: 20px; */
            /* padding-bottom:30px; */
            /* padding-left:30px; */
            padding-right:30px;
        }
```
​        通过复合属性设置填充：
​            仅设置一个值，则应用与四个填充：
```
        padding:20px;
```
​            设置两个值，则表示上下填充，左右填充：
```
        padding:20px 40px;
```
​            设置三个值，则表示上填充，左右填充，下填充
```
        paading:10px 20px 30px;
```
​        设置四个值，则表示上填充，右填充，下填充，左填充
```
        padding:10px 20px 30px 40px;
```

​    边框属性：
​        border属性:
​        单独设置：
​            border-style 设置边框样式，none无边框，solid实线, dashed 虚线,double
​            border-width 设置边框宽度
​            border-color 设置边框颜色
```
    div {
        border-style:solid;
        border-width:10px;
        border-color:lightblue;
    }
```
​        复合属性设置全部样式：border:red  5px solid; 
```
div {
        border:red  5px solid; 
    }
```

​        border-radius属性:圆角边框，像素值越大，圆角越明显。
​        border-radius:参数1， 四个角
```
    border-radius:10px;
```
​        border-radius:参数1 参数2
​                参数1 左上角 右下角
​                参数2 左下角 右上角
```
    border-radius:20px 30px;
```
​        border-radius:参数1 参数2 参数3
​                        参数1 左上角
​                        参数2 左下角 右上角
​                        参数3 右下角
```
    border-radius:20px 30px 40px;
```
​        border-radius:参数1 参数2 参数3
​                                参数1 左上角
​                                参数2 左下角 右上角
​                                参数3 右下角
```
    border-radius:20px 30px 40px;
```
​        border-radius:参数1 参数2 参数3 参数4 (顺时针)
​                                参数1 左上角
​                                参数2  右上角
​                                参数3 右下角
​                                参数4 左下角
```
    border-radius:20px 30px 40px 50px;
```

​    列表属性：1列表属性 2垂直菜单
​        1列表属性
​            list-style-type 设置列表项符号:none无 disc实心圆 circle空心圆 square实心正方形
​            list-style-image 设置图片作为列表项符号：url(图片路径)
​            list-style-position 设置项目符号在列表项的位置:inside,outside（默认）
```
li {
    border:red 4px solid;
    /* margin-left:80px; */
    /* list-style-type:none; */
    /* list-style-image: url(images/aa.jpg); */
    list-style-position:outside;
}
```
​        通过复合属性设置列表属性：
​            list-style:
```
list-style:circle inside url(images/aa.jpg);
```

背景和阴影
    背景属性：1背景颜色 2背景图片 3背景的重复方式
        背景颜色:英文单词、 16进制、 rgb(255, 254, 66)
```
body {
    background-color:red;
}
```
​        背景图片:
​            如果同时有背景颜色，优先显示背景图片。
​            background-image:url(图片路径)
```
    background-color:rgb(255, 254, 66);
    background-image:url(images/aa.jpg)
```
​        背景图片的重复（平铺）方式：
​            background-repeat:属性值，repeat（默认，水平垂直同时平铺） no-repeat不平铺 repeat-x水平平铺 repeat-y垂直平铺
```
        background-image:url(images/aa.jpg);
        background-repeat:no-repeat;
```
​        多张背景图片属性：
```
        background-image:url(images/aa.jpg),url(images/girl.jpg);
        background-repeat:repeat-y, no-repeat;
```

​    背景图片的定位：
​    1 background-position属性 ：
​        background-position:关键字 百分比 像素值
​        关键字：水平方向：left center right；垂直方向：top center bottom   
​        百分比：水平方向：从左到右0%-100%；垂直方向：从上到下0%-100%
​        像素值：
​            正数时：水平向右，垂直向下；
​            负数时：水平向左，垂直向上；
```
    background-image:url(images/aa.jpg);
    background-repeat: no-repeat;
    /* background-position:center center; */
    background-position:-50px -50px;
```
​    2 CSS Sprites(雪碧图，精灵图)
```
    #second {
        background-position:0px -26px;
    }
    #third {
        background-position:0px -52px;
    }
```

​    背景的渐变：
​    1线性渐变 
```
    background:linear-gradient(to right bottom,red 45%,white,black);
```
​    重复线性渐变
```
    background: repeating-linear-gradient(45deg, red 20px, white 30px, black 40px);
```
​    透明度渐变
​    rgb(red,green,blue)  red,green,blue在0-255之间
​    rgba(red,green,blue,alpha(透明度) ) alpha在0-1之间
```
    background:linear-gradient(to right, rgba(255,0,0,0),rgba(255,0,0,0.5) ),url(girl.jpg);
```

​     2径向渐变
```
        background: radial-gradient(red,white ,black )
```

​     重复径向渐变
```
    background: repeating-radial-gradient(ellipse,white 10px,black 40px)
```

​    阴影属性
​    1文字阴影
​        text-shadow:水平距离 垂直距离 模糊半径 阴影颜色
```
text-shadow:20px 20px 5px pink;
```
​    2盒子阴影
​        box-shadow:水平距离 垂直距离 模糊半径 阴影大小 阴影颜色
```
box-shadow:20px 20px 20px 5px blue;
```

​    盒子模型
​    1盒子模型原理
​        盒子模型概述
​            包含内容content 填充padding 边框border 边距（边界）margin
​            有上top、下bottom、左left、右right四个部分。
​            
​        盒子的大小
​            盒子的实际大小：内容+填充+边框 （不算边距）
​                盒子的实际宽度：左边框+左填充+内容宽度+右填充+右边框（不算边距）
​                盒子的实际高度：上边框+上填充+内容高度+下填充+下边框（不算边距）
​                
​            盒子占据空间大小：盒子的实际大小+边距
​                盒子占据空间的宽度：左边距+左边框+左填充+内容宽度+右填充+右边框+右边距
​                盒子占据空间的高度：上边距+上边框+上填充+内容高度+下填充+下边框+下边距
​                
​            
​        盒子之间的关系
​    2标准文档流
​    3盒子浮动
​    4盒子定位

1盒子模型原理
    盒子模型概述
    盒子的大小
        盒子占据空间大小
        盒子的实际大小
    盒子之间的关系
    
2标准文档流
    概述：
    标签排列规则：从左到右，自上而下。
    块元素：标题 段落 水平线(<hr />) 列表 表格(<table>) 表单(<form>) 层(<div>)
    行元素：图片<img> 范围<span> 换行<br> 超链接<a>
    块元素和行元素的区别：
        1 排列方式不同。块元素：自上而下。行元素：从左到右
        2 内嵌元素不同。块元素可以包含块元素和行元素，但是行元素只能文本或者行元素。
        3 属性设置不同。
            块元素可以设置width height属性，但是行元素不可以。
            行元素不可以设置上下边距，上下填充。
    
    display属性:
        消除元素，不占屏幕空间。
        display:none | block;
```
    display:block;
```
​    visibility属性
​        控制元素是否显示，实际上存在屏幕空间。
​        visibility: hidden|visible;
```
    visibility: visible;
```

3盒子浮动
    1 float属性
        float: none|left|right ;
```
    float: left ;
```
​    2 清除浮动
​        浮动的副作用：
​            背景不能显示
​            边框不能撑开
​            margin和padding不能正确设置
​            
​        清除浮动影响的方法
​            1 给父级元素设置宽高属性
```
        width:700px;
        height:156px;
```
​            2 clear:both 清除浮动
​                在父级div结束前加  <div class="clear"> </div>
```
.clear {
        clear:both;
    }
```
​            3 在父级div定义 overflow:hidden
```
    overflow:hidden;
```

​    4盒子定位
​        1静态定位
​            默认，按照标准流从左到右，从上到下布局。
​        2相对定位
​            参考点：原来元素的左顶点
​            从原来的位置移动到一个相对位置，占据原来的空间。
```
    position:relative;
    top:50px;
    left:150px;
```
​        3固定定位
​            相对于浏览器窗口定位。
```
    position: fixed;
    left:100px;
```
​        4 绝对定位
​            不占据空间。
```
position:absolute;
top:170px;
left:230px;
```
​        5 z-index属性
​            设置元素的堆叠顺序,必须先定位。
```
    z-index:13;
```

​    页面布局（ div+css布局）
​        1表格布局 2流式布局 3 div布局 4div高级


去屏幕白边
```
* {
    padding:0px;
    margin:0px;
}
```

div居中：
  先设置宽度width
```
    margin:0px auto;
```

文本居中：
    左右居中 text-align
    上下居中 line-height
    
背景图片的尺寸
    background-size:参数1(水平px或百分比) 参数2（垂直）;
```
    background-size:100% 100%;
```


去屏幕白边
```
* {
    padding:0px;
    margin:0px;
}
```

div居中：
  先设置宽度width
```
    margin:0px auto;
```

文本居中：
    左右居中 text-align
    上下居中 line-height
    
背景图片的尺寸
background-size: 参数1 参数2;
    第一个值设置宽度，第二个值设置高度（单位px或者百分比）

```
    background-size: 100% 100%;
```