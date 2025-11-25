<img src="http://img.an520.com/test/微信图片_20250519024516.jpg" width="260px"><img src="http://img.an520.com/test/mypublic.jpg" width="240px">

# 初识jQuery

##   什么是jQuery: 

​    快速、简洁的JS库，“write less, do more”

​    特点：

​      1、轻量级、代码小巧。

​      2、语法简洁、学习速度快、文档丰富。

jQuery能做什么：jQuery能做的JavaScript都能做，但使用jQuery能大幅提高开发效率

##   获取jQuery

​    官网：jquery.com

​    官网下载：jquery.com/download/

​    如果官网打不开，则通过国内的网站下载

##   使用jQuery

​    引入jQuery：

​      方式1:引入本地下载的jQuery 

```
<script src="js/jquery-3.6.0.js"></script>
```

​      方式2:通过CDN引入jQuery(不用下载，在线引入)

```
<script src="https://code.jquery.com/jquery-3.7.1.js"></script>
```

​    区别

​    书写位置

​      方式1:完整形式

​      方式2:简写形式

DOM和jQuery互相转换

$(document).ready() 是 jQuery 提供的一个函数，用于在 **DOM 加载完毕后**执行 JavaScript 代码。确保 JavaScript 代码在页面完全加载后再执行，以便能够正确地操作页面元素。

$(document).ready()方法可以在页面中的**任何位置**使用，**通常**放在脚本的**开头或者结束**部分。

<img src="http://img.an520.com/test/image-20241215212234912.png" width="500px">



掌握

```javascript
//在使用jQuery之前，先把jQuery文件引到页面中。src路径一定要写正确
<script src="js/jquery-3.6.0.js"></script>

<script>
 //$(document).ready() 入口函数，可以简写成$()
 $(document).ready(function(){  
	alert(“我们将开启jQuery的学习之旅！ ");
});
</script>
```

# jQuery选择器

##   基本选择器

​    $('#ID名') 、$('.class名')、$('标签名')  	// getElementByid()  / querySelectorAll()

​    全选选择器：$('*') 

​    并集选择器：$('#ID名,.class名标签名,标签名')

​    交集选择器：$('li.current')，意思是选择class=current的所有li标签

```javascript
$("h1").css("color","blue");
$(".price").css({"background":"#efefef","padding":"5px"});
$("#author").css("color","#083499");
$(".intro,dt,dd").css("color","#");
$("*").css("font-weight","bold");
```

##   层级选择器

​	子代选择器，$('ul>li')
​	后代选择器, $('ul li')
​	相邻元素选择器，$("prev+next" )，选取紧邻prev元素之后的next元素
​	同辈元素选择器，$("prev~sibings" )，选取prev元素之后的所有siblings元素

```javascript
$(".textRight>p").css("color"," "#EC0465 ");
$(".textRight p").css("color","#EC0465");

$("h1+p").css(text-decoration","underline");
$("h1~p").css("text-decoration","underline");
```

##     属性选择器

语法特点：使用"[ ]"

```javascript
$("a[class]").css("background","#CCFFCC");
$("a[class='hot']").css("background","#CCFFCC");
$("a[class!='hot']").css("background","#CCFFCC");
$("a[href^='www']").css("background","# CCFFCC ");
$("#news a[href$='html']").css("background","# CCFFCC ");
$("a[href*='k2']").css("background","# CCFFCC "); //a标签href属性值包含“k2”的元素
```

## 过滤选择器

​	语法特点：使用":"

主要分类如下：
	基本过滤选择器

```javascript
$("li:even").css("background","#FCF0D9");
$("li:odd").css("background","#FCECCA");
$("li:first").css({"font-size":"16px","color":"#e90202"}); //表示选取第一个li元素
$("li:last").css("border","none");
//:eq(index) 选取索引等于index的元素（index从0开始）
$("li:eq(0)")
$("li:lt(2)").css({"color":"#1F078D"});//索引小于index的元素
$("li:gt(3)").css({"color":"#2466F5"});//大于
//:not(selector) 选择器选取除了指定元素以外的所有元素。
$("p:not(.intro)") //选取除了 class="intro" 元素以外的所有 <p> 元素：
```

​	内容过滤选择器

```javascript
//:contains(text) 选取含有内容为“text”的元素
$("div:contains('相机')" ) //选取含有文本内容“相机”的<div>元素
```

​	可见性过滤选择器

```javascript
$("p:hidden").show();
$("p:visible").hide();
```

​	属性过滤选择器
​	子元素过滤选择器

:nth-child(*n*|even|odd|*formula*) 选取**每个**父元素下的第index个子元素或者奇偶元素(index从1算起)

```javascript
$("ul li:nth-child(odd)") //选择列表中的每个第奇数个元素
$("ul li:nth-child(2)") //选择列表中的每个第2个元素
$("ul li:nth-child(2n+1)") //选择列表中的每个第3、5、7...个元素：
```

​	表单(\<form>)选择器

:input	匹配所有input、textarea、select和button 元素

:text	匹配所有单行文本框

:checkbox	匹配所有复选框

```javascript
//.size()方法从jQuery 1.8开始被废弃。使用.length属性代替。
$(":input").length;

$(":checkbox").length;

//:checked选取所有被选中的元素，单选和复选字段 集合元素
$("input[type='checkbox']:checked").length;
```

​	表单对象属性过滤选择器

对所选择的表单元素进行过滤

:enabled	选取所有可用元素	:disabled	选取所有不可用元素

:checked	选取所有被选中的元素(单选框，复选框)

:selected	选取所有被选中的选项元素(下拉列表)

```javascript
$(":button[value='你的爱好']").click(function(){
	var hobby=$("input[type='checkbox']:checked").size();
	alert("你有"+hobby+"个爱好");
})
```

<img src="http://img.an520.com/test/image-20241120003341913.png" width="700">



## 	其他筛选方法

查找节点：next()/children()/prev()/siblings()/parent()/each()等

```javascript
//parents() 找当前元素的所有父节点 
//parent() 方法返回被选元素的直接父元素。
$( 'li' ).parent()                            // 查找父级
//closest() 是找当前元素的所有父节点 ，直到找到第一个匹配的父节点
//children()方法查找元素的直接子元素，只会查找到一级子元素
$( 'ul').children( 'li')                  // 相当于$( ' ul>li ' )   最近一级（亲儿子）
//find()方法则会查找元素的所有后代元素，不仅限于直接子元素。
$( 'ul' ).find( 'li' )                      //     后代选择器
$( 'li' ).siblings( 'li' )                  //   查找兄弟节点，不包括自己本身
$( 'li' ).nextAll( )                         //    查找当前元素之后所有的同辈元素   
// prev()方法只能获取同级别的上一个Html元素
$( 'li' ).preAll( )                           //    查找当前元素之前所有的同辈元素
$( 'li' ).hasClass( 'protected' )  //  检查当前的元素是否含有某个特定的类，如果有，则返回true
$( 'li' ).eq(2)                              //    相当于在获取到的li元素中，选择索引号为2的li，。即第三个
```



## 隐式迭代

‌隐式迭代是指在操作多个DOM元素时，jQuery会**自动**对每个元素执行操作，而无需手动遍历。这种机制简化了代码编写，提高了开发效率。

```javascript
// 使用jQuery隐式迭代为所有div元素内部添加一个span标签
$('div').html('<span>广州小蛮腰</span>');


// 使用原生JavaScript实现相同功能需要手动遍历每个元素
var divs = document.querySelectorAll('div');
divs.forEach(function(div) {
    var span = document.createElement('span');
    span.textContent = '广州小蛮腰';
    div.appendChild(span);
});
```

## 链式调用

在同一个jQuery对象上连续进行多个操作，每一步的操作都会返回这个对象本身，从而可以继续进行下一步操作。这种模式可以使代码更加简洁、易读。

```javascript
$(document).ready(function() {
    // 链式调用
    $('#myElement')
        .css('color', 'red')        // 设置文字颜色为红色
        .css('font-size', '20px')   // 设置文字大小为20px
        .hide()                     // 隐藏元素
        .show('slow');              // 慢慢显示元素
});
```

# jQuery样式操作

jQuery操作元素样式

  获取样式：css('样式名')

## 修改样式：

​    设置单个样式: css('样式名','样式值')

```javascript
$('#elementId').css('color', 'red'); //元素.style.样式名
```

​    同时设置多个样式：

```javascript
$('#elementId').css({
  'color': 'red',
  'background-color': 'blue',
  'border': '1px solid black'
});
```

## 类操作：

​      添加类:addClass('类名1 类名2 类名3')  	//元素.className = 

​      移除类：removeClass('类名')

​      切换类：toggleClass('类名')，有就删，无就加

# jQuey动画

jQuery实现动画效果

##   显示与隐藏效果

​    show([speed],[easing],[fn]) 显示

​    hide([speed],[easing],[fn]) 隐藏

​    toggle([speed],[easing],[fn]) 显示与隐藏切换

​		speed速度  : fast normal slow

##   滑动效果

​    slideDown([speed],[easing],[fn])  向下

​    slideUp([speed],[easing],[fn])  向上

​    slideToggle([speed],[easing],[fn])  切换

## hover()方法

鼠标悬浮事件

​    $('选择器').hover([over,],out)

##   停止动画： 

stop() 

##   淡入淡出

​	控制透明度    

​    fadeIn([speed],[easing],[fn])  淡入显示

​    fadeOut([speed],[easing],[fn])  淡出隐藏

​    fadeTo([speed],opacity,[easing],[fn])  调整到指定的透明度

​		opacity 透明度 0-1

​    fadeToggle([speed],[easing],[fn])  切换

##   自定义动画

​    $('选择器').animate(params,[speed],[easing],[fn])

​	顺序执行多个动画

```javascript
$('.divStyle').animate({ left: '250px' }).animate({ top: '300px' })
```

## 可见性判断

is(':visible')和.is(':hidden')。这两个方法分别用于判断元素是否**可见和不可见**。

## is函数用法

根据选择器、元素或jQuery对象来检测匹配元素集合， 如果这些元素中至少有一个元素匹配给定的参数，则返回true。

```javascript
// 是否是隐藏的
$('#test').is(':visible');
// 判断input元素是否被选中
$('input[name=chkNoChecked]').is(':checked')；
// 是否是第一个子元素
$(this).is(":first-child");
// 是否包含.blue,.red的class
$(this).is(".blue,.red");
// 文本中是否包含Peter这个词
$(this).is(":contains('Peter')");
```



# jQuery属性和内容操作

## jQuery操作属性

###   attr() 方法：

获取或者设置元素的自定义属性     

​    获取： $('选择器').attr('属性名')       (getAttribute)

​    设置： $('选择器').attr('属性名', '属性值')  (setAttribute)

###   prop()方法：

获取或者设置元素的固有属性(不能获取自定义属性)  (.) 

​    获取： $('选择器').prop('属性名')
​        （元素.固有属性）
​    设置： $('选择器').prop('属性名', '属性值')
​        （元素.固有属性 = 属性值）

| **属性**       | **目的**                                | **推荐用法**             |
| -------------- | --------------------------------------- | ------------------------ |
| **`checked`**  | 获取复选框/单选按钮的**当前选中状态**。 | ✅ **`prop('checked')`**  |
| **`disabled`** | 获取或设置元素是否**禁用**。            | ✅ **`prop('disabled')`** |

**区别**：一般来说，具有 **true 和 false 两个属性的属性**，如 checked, selected 或者 disabled 使用**prop()**方法，其他的使用 attr()方法

### 使用建议

- **如果属性的值会随着用户交互而改变（状态类属性）**：使用 **`prop()`**。例如：`checked`, `disabled`, `selected`, `value`。
- **如果属性不会改变，或者您操作的是自定义属性**：使用 **`attr()`**。例如：`id`, `class`, `data-*`。

### 删除属性

​	removeAttr()和removeProp()

###   data()方法：

在指定元素上存储数据(保存在内存中)

​    获取： $('选择器').data('数据名')

​    设置： $('选择器').data('数据名','数据值')  存储数据

​    

## jQuery操作内容

  html()      获取带标签内容   （元素.innerHTML）

  	html(content)  设置带标签内容    (元素.innerHTML=content)

  text()      获取不带标签内容   (元素.innerText）

```
  text(content)  获取不带标签文本内容  (元素.innerText=content）
```

  val()  获取表单元素的value值    （.value）

  	val(value)  设置表单元素的value值    （.value = value）

# jQuery元素（节点）操作

## 遍历元素（节点）

  遍历元素:each

```
$('选择器').each(function(index,domElement){})
```

  **遍历对象或者数组： $.each**

```
$.each(Object, function(index,element){})
```

遍历元素：基本语法 $(selector).each(function(index, domEle) {});

```javascript
<div>1</div><div>2</div><div>3</div>

<script>
  var arr = ["red", "green", "blue"];

  $("div").each(function (index, domEle) {
    console.log(index); // 查看索引号
    console.log(domEle); // 查看DOM元素
      
    $(domEle).css("color", arr[index]); // 对每个元素进行操作
  });
</script>
```

$.each()方法：基本语法$.each(Object, function(index, element) {});

```javascript
// 遍历数组
var arr = ["red", "green", "blue"];

$.each(arr, function(index, element) {
  console.log(index); // 数组中的每个元素的索引
  console.log(element); // 数组中的每个元素的值
});

// 遍历对象
var obj = { name: "andy", age: 18 };
$.each(obj, function(index, element) {
  console.log(index); 		// 对象中的每个成员的名
  console.log(element); 	// 对象中的每个成员的值
});
```

遍历节点：next()/children()/prev()/siblings()/parent()/each()等


##   创建元素

​    $('HTML字符串')     (  createElement('元素名')  )

##   添加元素（插入节点）

​    内部添加(子元素)

​      最前面： 目标元素.prepend(待添加元素)
​          父级元素.prepend(添加的元素)

​      最后面:  目标元素.append(待添加元素)
​          父级元素.append（添加的元素）

​    外部添加(兄弟元素)

​      前面: 目标元素.before(待添加元素)

​      后面: 目标元素.after(待添加元素)    

##   删除元素（删除节点）

​    empty()   清空内容，不删元素

​    remove()   清空内容并且删元素

# jQuery尺寸和位置操作

jQuery操作元素尺寸和位置方法

## 尺寸方法

  width()   获取或者设置元素宽度

  height()   获取或者设置元素高度

  outerWidth(true) 获取元素宽度（包含padding border margin）

  outerHeight(true) 获取元素高度（包含padding border margin）

  innerWidth()   获取元素宽度(包含padding)

  innerHeight()  获取元素高度(包含padding)

  outerWidth() 获取元素宽度（包含padding border ）

  outerHeight() 获取元素高度（包含padding border ）

##   位置方法

​    offset()方法获取元素的位置，返回一个对象，包含left top属性，
​        表示相对文档的偏移坐标，和父级元素没有关系。


​    position()方法获取距离已定位父元素的位置，如果父元素没有定位，则相对于文档。


​    scrollTop() 获取或者设置元素被卷去的顶部距离

​    scrollLeft()   获取或者设置元素被卷去的左边距离

# jQuery事件和其他方法    

jQuery事件的使用

## 事件绑定

  通过事件方法绑定事件：

```javascript
$('选择器').事件名(function(){
	//触发事件后执行的代码
})
```

  通过on()方法绑定事件：

​    绑定on()单个事件

```javascript
$('选择器').on('事件名',[selector], function() {
	//触发事件后执行的代码
})
```

​    通过on()方法绑定多个事件：

```javascript
$('选择器').on({
    事件名1:function(){},
    事件名2:function(){},
    事件名3:function(){},
})
```

```javascript
$('选择器').on({
    click: function() {
    //触发事件后执行的代码
    },

    mouseover: function() {
    //触发事件后执行的代码
    },

    mouseout: function() {
    //触发事件后执行的代码
    }

})
```

​    通过on()方法绑定相同的事件处理函数

```javascript
   $('选择器').on('事件名1 事件名2',[selector], function() {
       //触发事件后执行的代码
   })
```



## 事件委派

​    事件委派：原本要给子元素绑定的事件绑定到父元素上。

## 事件解绑

  off()方法：移除通过on()方法绑定的事件

  one()方法：事件只触发一次 

## 触发事件

​    $('选择器').事件名()

​    $('选择器').trigger('事件名')

​    $('选择器').triggerHandler('事件名') 触发事件时不执行默认行为

##   事件对象

```javascript
$('选择器').事件名(function(event){
	//触发事件后执行的代码
})
```


  其他方法：

​    $.extend()方法：拷贝对象

​      $.extend([deep],target,Object1,[ObjectN])

## AJAX

即异步 JavaScript 和 XML（Asynchronous JavaScript and XML），是一种与服务器交换数据的技术  

 $.ajax()方法：通过ajax技术（**异步**）请求服务器，获取服务器的响应结果  

http请求类型包括**get方法、post方法**

```javascript
$.ajax({
    url: 'http://localhost/shoppingcar/list/',  //规定发送请求的 URL
    type: 'GET',  //规定请求的类型GET
    // 成功回调
    success: function (result) {
        $("#div1").html(result);
    },
    // 失败回调
    error: function (e) {
        console.log(e);
    }
})
```

```javascript
function add(pid) {
    $.ajax({
        url: "http://localhost/shoppingcar/add/",
        type: 'GET',
        data: {
        	sc_pid: pid
        },
        // 成功回调
        success: function (res) {
            console.log(res);
            getData();
        },
        // 失败回调
        error: function (e) {
        	console.log(e);
        }
    })
}
```

Windows 搭建**PHP集成环境**：XAMPP、WAMP、phpStudy

jQuery实现购物车

jQuery电梯导航

# jQuery插件

### 插件的概念与用途

#### 什么是插件 

- 　　插件（Plugin）又称为扩展（Extension），是一种遵循一定规范的应用程序接口编写出来的程序。

- ​	为什么要用jQuery插件：当jQuery库里面的功能不能满足我们的时候，我们就可以开发新的功能来**扩展jQuery库**，开发jQuery插件的过程其实就是给jQuery对象上面添加新的方法。jQuery的**官方插件是jQuery UI**。开发者可以任意扩展jQuery的函数库或者按照自己的需求开发UI组件。

- ​	插件实际上也是一个JS文件

- ​	所有jQuery插件的使用方法均为：**先引入jQuery，再引入插件**


#### 为什么要使用插件

**优点：**

1. 代码简洁：调用时只需要用很少的代码就能实现比较复杂的效果。
2. 避免重复写代码：特别是一些企业网站的客户，看到别人网站上面有那种效果，就希望自己的站点也有那种效果。
3. 网上插件很多很丰富，容易找到。
4. 不需要关注具体实现，只关心如何调用api（方法）。

#### 插件使用通法

1. 引入jquery库
2. 引入插件样式（有的插件不需要样式）
3. 引入插件js库
4. 在你的页面按照插件编写html结构和样式，调用插件的方法
5. 测试效果

#### 插件使用的三步曲 

1. 下载相关插件(在网上查找相关需要的插件,下载)

  •官网网址：https://plugins.jquery.com

2. 引入相关内容(jq库 插件js CSS 在网页中从示例代码中,找到实现的代码,写到自己的网页中)

3. 配置相关插件(结合插件的使用,看示例或文档来实现)



###  ss-menu插件

ssMenu是一款jQuery固定侧边栏插件。

​	下载地址：https://github.com/CodeHimBlog/jquery.ssMenu

​	https://www.bootstrapmb.com/item/3661/preview

```javascript
//使用ss-Menu固定侧边栏插件，需要引入三个文件，一个jQuery库，一个ss-menu插件js文件和一个ss-menu的CSS文件，操作步骤如下：
<script src="js/jquery-1.12.4..js" type="text/javascript"></script>

<script src="js/jquery.ss.menu.js"></script>

<link rel="stylesheet" href="css/ss-menu.css"> 
```

### Layer插件

主要用于创建**弹出层**，对话框和其他覆盖层，从而增强用户交互体验。

​	http://layui.apixx.net/layer/index.html

```html
<link rel="stylesheet" href="path/to/layer.css">
<script src="path/to/jquery.min.js"></script>
<script src="path/to/layer.min.js"></script>
<script>
    $(document).ready(function(){
        // 显示一个简单的弹出层
        layer.open({
            type: 1, // 弹出层类型
            title: 'Hello Layer', // 弹出层标题
            content: 'This is a simple layer pop-up.' // 弹出层内容
        });
    });
</script>
```

### Pinterest Grid

实现响应式网格**瀑布流**布局

​	https://www.jq22.com/demo/jquery-pbl-150519204337/flexible.html

```javascript
<link rel="stylesheet" href="path/to/pinterest_grid.css">
<script src="path/to/jquery.min.js"></script>
<script src="path/to/jquery.pinterest_grid.js"></script>
```

### swiper插件

swiper插件是一个流行的**轮播图插件**，用于创建响应式的**图片轮播**效果。它具有丰富的配置选项，可以通过参数来自定义插件的功能和外观。

​	https://www.swiper.com.cn/

```javascript
<link rel="stylesheet" href="path/to/swiper.min.css">
<script src="path/to/jquery.min.js"></script>
<script src="path/to/swiper.min.js"></script>
```

### Validate插件

jQuery Validate插件是一个强大的**表单验证**工具，它提供了各种验证规则，并且可以进行自定义扩展。

​	参考教程：https://www.runoob.com/jquery/jquery-plugin-validate.html

​		https://www.jq22.com/jquery-info3350

```javascript
<script type="text/javascript" src="jquery-1.11.1.js"></script>
<script type="text/javascript" src="jquery-validate.js"></script>
```

### *Supersized* 插件

背景图片切换

```javascript
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<script src="supersized.3.2.7.min.js"></script>
<link rel="stylesheet" href="supersized.css">
```

### bxSlider插件

适用于图片轮播、内容滑块等场景

官网：http://bxslider.com/ 

​	https://sliderui.com/



### 编写jQuery插件

将你的jQuery代码封装成一个jQuery插件以便以后重用，你可以通过以下代码来创建

```javascript
function($){  
    $.fn.yourPluginName = function(){  
        // Your code goes here  
        return this;  
    };  
})(jQuery); 
```

养成良好的代码编写习惯

- ​	代码要排版 (如：格式，命名，结构，注释)

- ​	代码要优化 (一行代码能实现绝不写两行)

- ​	代码要先构思后实现

- ​	CSS文件放在\<head>中调用（加快页面渲染速度）

- ​	JS文件放在\</body>前调用（防止报错后js不运行）


产品工具

- ​	jira 
- ​	axure 
- xmind
- ​	墨刀 
- 蓝湖 
