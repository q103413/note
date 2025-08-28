了解

jQuery的基本概念

什么是jQuery：

  快速、简洁的js库，“write less, do more”

特点：

  1、轻量级、代码小巧

  2、语法简洁、学习速度快、文档丰富。

获取jQuery 

  官网：jquery.com

  官网下载地址：jquery.com/download/

  也可以在国内的其它网站下载,比如www.ab173.com/jquery/。

  

使用jQuery

  引入jQuery

​    方式1:引入本地下载的jQuery 

​    方式2:通过CDN引入jQuery(不用下载，在线引入)

  

书写位置

  

DOM和jQuery互相转换

  

  

掌握

jQuery选择器

  基本选择器

​    $('#id')  $('.class') $('标签名')  

​    并集选择器：$('标签名,.class,#id') 

​    全选选择器： $('*')

​    交集选择器：$('li.current')，意思是选择class=current的所有li标签

  层级选择器

​    子代选择器  $('ul>li')

​    后代选择器  $('ul li')

​    隐式迭代

  筛选选择器

  

  其它选择器

​    属性选择器

jQuery操作元素样式

  获取样式:css('样式名')

  设置单个样式：css('样式名','样式值')

​    同时设置多个样式

  类操作：

​    添加类：addClass('类名')

​    移除类：removeClass('类名')

​    切换类：toggleClass('类名')，有就删，无就加

​    

  添加事件：

​    $('选择器').事件名(function(){

​      //执行的代码

​    })

jQuery实现动画效果

  显示与隐藏效果

​    show([speed],[easing],[fn])  显示

​    hide([speed],[easing],[fn]) 隐藏

​    toggle([speed],[easing],[fn]) 显示与隐藏切换

  

  滑动效果

​    slideDown([speed],[easing],[fn])  向下

​    slideUp([speed],[easing],[fn])  向上

​    slideToggle ([speed],[easing],[fn])  切换

  

  hover()方法

​    $('选择器').hover([over,],out)

  

  停止动画： stop() 

  

  淡入淡出

​    fadeIn([speed],[easing],[fn])  淡入显示

​    fadeOut([speed],[easing],[fn])  淡出隐藏

​    fadeTo([speed],opacity,[easing],[fn]) 调整到指定的透明度

​    fadeToggle([speed],[easing],[fn])  切换

  

  自定义动画

​    animate(params,[speed],[easing],[fn])  

​    

第十一章

jQuery操作属性

  prop()方法获取或者设置固有属性

​    prop('属性名')       获取    （元素.固有属性）

​    prop('属性名','属性值')  设置    （元素.固有属性 = 属性值）

​    

  attr()方法获取或者设置自定义属性

​    attr('属性名')       获取    （getAttribute）

​    attr('属性名','属性值')  设置    （setAttribute）

​    

  data()方法：在指定元素上存储数据(保存在内存中)

​    data('数据名')     获取数据

​    data('数据名','数据值')  存储数据

​    

jQuery操作内容

  html()      获取带标签内容   （元素.innerHTML）

  html(content)  设置带标签内容    (元素.innerHTML=content)

  text()      获取不带标签内容   (元素.innerText）

  text(content)  获取不带标签文本内容  (元素.innerText=content）

  val()  获取表单元素的value值    （.value）

  val(value)  设置表单元素的value值    （.value = value）

jQuery元素操作

  遍历元素：$('选择器').each(function(index,domElement){})

  

  遍历对象: $.each(Object, function(index,element){})

  

  创建元素

​    $('HTML字符串')     ( createElement('元素名') )

​    

  添加元素

​    内部添加

​      最前面   父级元素.prepend(添加的元素)

​      最后面 父级元素.append（添加的元素）

​    外部添加

​      后面    目标元素.after(添加的元素)

​      前面    目标元素.before(添加的元素)

  

  删除元素

​    empty()   清空内容，不删元素

​    remove()   清空内容并且删元素

  

  jQuery操作元素尺寸和位置

​    width()   获取或者设置宽度

​    height()   获取或者设置高度

​    outerWidth(true)  获取宽度(包含padding border margin)

​    outerHeight(true)  获取高度(包含padding border margin)

​    innerWidth()   获取宽度(包含padding)

​    innerHeight()   获取高度(包含padding)

​    outerWidth()   获取宽度(包含padding border)

​    outerHeight()  获取高度(包含padding border)

  位置方法

​    offset()方法获取元素的位置，返回一个对象，包含left top属性，

​        表示相对文档的偏移，和父级元素没有关系。

​        

​    position()方法获取距离已定位父元素的位置，如果父元素没有定位，则相对于文档。

​    

​    scrollTop() 获取或者设置被卷去的头部距离

​    scrollLeft() 获取或者设置被卷去的左侧距离

  

jQuery事件的使用

事件绑定

  通过事件方法绑定事件：

​    $('选择器').事件名(function(){

​      //执行的代码

​    })

  通过on()方法绑定事件

​    绑定单个事件：

​      $('选择器').on('事件名',[selector],function(){

​        //执行的代码

​      })

​    绑定多个事件：

​      $('选择器').on({

​        事件名1:function(){},

​        事件名2:function(){},

​        事件名3:function(){},

​      })

​    绑定相同的事件处理函数

​      $('选择器').on('事件名1 事件名2',[selector],function(){

​        //执行的代码

​      })

​      

  事件委派：原本要给子元素绑定的事件绑定到父元素上

事件解绑

  off()方法：移除通过on()方法绑定的事件

  

  one()方法：事件只触发一次

  

触发事件

  $('选择器').事件名()

  trigger('事件名')

  triggerHandler('事件名')  触发事件不执行默认行为

事件对象

  $('选择器').事件名(function(event){

​    //执行的代码

  })

其他方法

  $.extend([deep],target,oject1,[objectN])  拷贝对象

  $.ajax()方法：通过Ajax计算异步请求服务器，获取服务器的响应结果

  

jQuery实现购物车、电梯导航



JS面向对象

了解什么是面向对象编程

  面向对象的特征：

​    封装性、继承性、多态性

​    

掌握类与对象的关系

  类：抽象的事物

  对象：具体的事物

  

掌握类的继承与super关键字的使用

  

掌握使用class创建类的方法

正则表达式

什么是正则表达式：（匹配字符串中的字符）

  是一种描述字符串结构的语法规则

  用于匹配字符串中字符组合的模式

  也是对象

创建正则表达式

  字面量方式

​    var 变量名 = /表达式/

  RegExp构造函数的方式

​    var 变量名= new RegExp(/表达式/)

​    或者 var 变量名= RegExp(/表达式/)