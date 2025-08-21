了解

jQuery的基本概念

  什么是jQuery: 快速、简洁的JS库，“write less, do more”

​    特点：

​      1、轻量级、代码小巧。

​      2、语法简洁、学习速度快、文档丰富。

  获取jQuery

​    官网：jquery.com

​    官网下载：jquery.com/download/

​    如果官网打不开，则通过国内的网站下载

​    

  使用jquery

​    引入jquery：

​      方式1:引入本地下载的jquery 

​      方式2:通过CDN引入jquery(不用下载，在线引入)

​    区别

​    书写位置

​      方式1:完整形式

​      方式2:简写形式

  

掌握

jQuery选择器

  基本选择器

​    $('#ID名') 、$('.class名')、$('标签名')

​    全选选择器：$('*') 

​    并集选择器：$('#ID名,.class名标签名,标签名')

​    交集选择器：$('li.current')，li标签中class=current的元素

  层级选择器

​    子代选择器，$('ul>li')

​    后代选择器, $('ul li')

​    

​    隐式迭代

​      $('div').css('background-color', 'pink')

​    

  筛选选择器

​    常用筛选方法

​    

  其它选择器

​    属性选择器

​    

jQuery操作元素样式

  获取样式：css('样式名')

  修改样式：

​    设置单个样式:css('样式名','样式值')

​    设置多个样式：

  

​    类操作：

​      添加类:addClass('类名1 类名2')

​      移除类：removeClass('类名')

​      切换类：toggleClass('类名')，有就删，无就加

​      

  jQuery事件：

​      $('选择器').事件名(function(){

​        //事件的执行代码

​      })

​      

jQuery动画效果

  显示与隐藏动画

​    show([speed],[easing],[fn]) 显示

​    hide([speed],[easing],[fn]) 隐藏

​    toggle([speed],[easing],[fn]) 切换

​    

  滑动效果

​    slideDown([speed],[easing],[fn])  向下

​    slideUp([speed],[easing],[fn])  向上

​    slideToggle([speed],[easing],[fn])  切换

  

  $(selector).hover([over],out)

  

  停止动画

​    stop()

​    

  淡入淡出

​    fadeIn([speed],[easing],[fn])  淡入显示

​    fadeOut([speed],[easing],[fn])  淡出显示

​    fadeTo([speed],opacity,[easing],[fn])  显示到指定的透明度

​    fadeToggle([speed],[easing],[fn])  切换

  自定义动画

​    $('选择器').animate(params,[speed],[easing],[fn])

jQuery操作属性

  prop()方法：获取或者设置元素的固有属性(不能获取自定义属性)  (.) 

​    获取： $('选择器').prop('属性名')

​    设置： $('选择器').prop('属性名','属性值')

  

  attr() 方法：获取或者设置元素的自定义属性     

​    获取： $('选择器').attr('属性名')       (getAttribute)

​    设置： $('选择器').attr('属性名','属性值')  (setAttribute)

  

  data()方法：在指定元素上保存数据（保存在内存中）

​    获取： $('选择器').data('数据名')

​    设置： $('选择器').data('数据名','数据值')

​    

jQuery操作内容

​    html()      获取内容(带标签)    (innerHTML)

​    html(content)  设置内容     (innerHTML = content)

​    text()      获取内容(不带标签)    (innerText)

​    text(content)  设置内容     (innerText = content)

  

​    val()  获取表单元素的value值    (.value) 

​    val(value)  设置表单元素的value值   

  

  遍历元素:each

​    $('选择器').each(function(index,domElement){})

  

  遍历对象： $.each

​    $.each(Object, function(index,element){})

​    

元素操作

  创建元素

​    $('HTML字符串')

  添加元素

​    内部添加(子元素)

​      最前面： 目标元素.prepend(待添加元素)

​      最后面:  目标元素.append(待添加元素)

​    外部添加(兄弟元素)

​      前面: 目标元素.before(待添加元素)

​      后面: 目标元素.after(待添加元素)    

  删除元素

​    empty()   清空内容，不删元素

​    remove()   清空内容并且删元素

jQuery操作元素尺寸和位置方法

  width()   获取或者设置元素宽度

  height()   获取或者设置元素高度

  outerWidth(true) 获取元素宽度（包含padding border margin）

  outerHeight(true) 获取元素高度（包含padding border margin）

  innerWidth()   获取元素宽度(包含padding)

  innerHeight()  获取元素高度(包含padding)

  outerWidth() 获取元素宽度（包含padding border ）

  outerHeight() 获取元素高度（包含padding border ）

  位置方法

​    offset() 获取元素位置，返回对象包含left top, 相对文档的偏移坐标，与父级元素没有关系。

​    

​    position()  获取元素距离父元素的位置，如果父元素没有定位，则相对于文档。

​    

​    scrollTop() 获取或者设置元素被卷去的顶部距离

​    scrollLeft()   获取或者设置元素被卷去的左边距离

​    

jQuery事件的使用

事件绑定

  通过事件方法绑定事件：

​    $('选择器').事件名(function(){

​      //触发事件后执行的代码

​    })

  通过on()方法绑定事件：

​    绑定on()单个事件

​      $('选择器').on('事件名',[selector], function() {

​        //触发事件后执行的代码

​      })

​    通过on()方法绑定多个事件：

​      $('选择器').on({

​        click: function() {

​          //触发事件后执行的代码

​        },

​        mouseover: function() {

​          //触发事件后执行的代码

​        },

​        mouseout: function() {

​          //触发事件后执行的代码

​        }

​      })

​    通过on()方法绑定相同事件：

​      $('选择器').on('事件名1 事件名2',[selector], function() {

​        //触发事件后执行的代码

​      })

​    

​    事件委派：原本要给子元素绑定的事件绑定到父元素上。

​    

  off()方法：移除on方法绑定的事件

  one()方法：事件只触发一次 

  

  触发事件：

​    $('选择器').事件名()

​    $('选择器').trigger('事件名')

​    $('选择器').triggerHandler('事件名') 触发事件时不执行默认行为

  

  事件对象

​    $('选择器').事件名(function(event){

​      //触发事件后执行的代码

​    })

  

  其他方法：

​    $.extend()方法：拷贝对象

​      $.extend([deep],target,Object1,[ObjectN])

​      

  $.ajax()方法：通过ajax技术（异步）请求服务器，获取服务器的响应结果

​    

​    

​    

jQuery实现购物车

jQuery电梯导航


jQuery选择器
	基本选择器
		$('#ID名') 、$('.class名')、$('标签名')
		全选选择器：$('*') 
		并集选择器：$('#ID名,.class名标签名,标签名')
		交集选择器：$('li.current')，li标签中class=current的元素
	层级选择器
		子代选择器，$('ul>li')
		后代选择器, $('ul li')
		
		隐式迭代
			$('div').css('background-color', 'pink')
		
	筛选选择器
		
		常用筛选方法


js面向对象
了解什么是面向对象
	面向对象的特征：	
		封装性、多态性、继承性
掌握类与对象的关系
掌握类的继承以及super关键字的使用
掌握使用class创建类的方法


正则表达式：（匹配字符串中的字符）
	是一种描述字符串结构的语法规则
	用于匹配字符串中字符组合的模式
	也是对象

创建正则表达式的方法
	字面量方式：
		var 变量名 = /表达式/
	RegExp构造函数式
		var 变量名 = new RegExp(/表达式/)  或者RegExp(/表达式/)
		

项目经理、产品经理、leader

jira 
axure xmind
墨刀 蓝湖 

github	gitlab 	gitee