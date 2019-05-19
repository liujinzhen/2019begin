#<center>jquery知识

##一、为什么要学jQuery?

1. jQuery是一个快速、简洁的JavaScript框架，是继Prototype之后又一个优秀的JavaScript代码库（或JavaScript框架）。jQuery设计的宗旨是“write Less，Do More”，即倡导写更少的代码，做更多的事情。它封装JavaScript常用的功能代码，提供一种简便的JavaScript设计模式，优化HTML文档操作、事件处理、动画设计和Ajax交互。
 
2. 目前这个阶段，主要学习如何来使用jQuery操作DOM，其实就是学习jQuery封装好的那些功能方法，这些方法叫做API（Application Programming Interface应用程序编程接口。

3. Jquery  主要版本

	+ 1.xx    1版本    支持ie5678.。。
	+ 2.xx    2 版本	放弃了对ie5678的支持
	+ 3.xx    3 版本	没向前兼容 
		- 这个版本并不是越新越好。根据项目需求。
		- 但是各个版本的基础功能都是一样的。常用api也是一样的。
		- Jquery的版本选择 需要看项目中依赖的或者使用的jquery插件来决定

4. 在开发中 一般使用开发版本，非压缩版本。可以查看源码（比如api不明确的时候，不知道怎么用的时候）。
但是对于jquery  没必要。Jquery很成熟文档很全面，也不存在修改源码的情况。

5. 用jQuery之前，先引入jQuery，然后，再去写我们的jQuery代码。
如果使用了第三方jquery插件（日历、滚动、瀑布流等），必须先引入jquery，再引入该插件。

##二、入口函数

1. $(document).ready(function(){});
2. $(function(){});  推荐
	- (注:script内容写在head里时,需要写入口函数才能获取body内容)
	
##三、事件处理

###事件源

	类选择器   .d1   类 是为了告诉程序员这个标签是什么，它跟谁是一样（类）的，类一般所有的标签都有
	Id选择器   #div1   id=’goods_1’   id是为了区分为一，是js中使用的，id是在需要的时候才有，多用于列表等重复性标签
	标签选择器    div  

###事件

	Js:   onclick    onmouseover  onmousemove  …
	Jquery:   click     mouseover   mousemove  

###事件处理程序
	Js:  .onclick = function(){ }
	Jquery:   click(function(){  });

<strong>注意： jquery中 的事件处理都是方法 ，原生js的事件处理是属性</strong>

	$
	a)命名归法：下划线、字母、$、数字
	b)但是不能以数字作为开头
	
	jQuery的两个变量：$ 和 jQuery
	
<strong>注意：不能再使用这两个变量 防止引起冲突，什么时候使用jQuery？当有其他框架中使用$造成冲突的时候使用jQuery。</strong>

##四、js入口函数跟jQuery入口函数的区别

	1.执行时间
	window.onload必须等到页面内包括图片的所有元素加载完毕后才能执行。
	$(document).ready()是DOM结构绘制完毕后就执行，不必等到加载完毕。只加载了dom框架，对于大的图片需要时间，这个不等。  <img scr=’’>

	2.编写个数不同
	window.onload不能同时编写多个，如果有多个window.onload方法，只会执行一个
	$(document).ready()可以同时编写多个，并且都可以得到执行

	3.简化写法
	window.onload没有简化写法
	$(document).ready(function(){})可以简写成$(function(){});

##五、Javascipt跟jQuery的区别：
	Javascript是一门编程语言，我们用它来编写客户端浏览器脚本。
	jQuery是javascript的一个库，包含多个可重用的函数，用来辅助我们简化javascript开发
 
	jQuery能做的javascipt都能做到，而javascript能做的事情，jQuery不一定能做到。

	所有的前段框架的基础都是javascript，动画基础都是前面跟大家讲过的动画原理。包括以后会讲的vue.js
	Angular.js 甚至市面上各种前段框架，基础都是JavaScript。
	只要框架能实现，js原生写法都能实现。

##<strong>mouseover事件跟mouseenter事件的区别：</strong>
	mouseover/mouseout事件，鼠标经过的时候会触发多次，每遇到一个子元素就会触发一次。
	mouseenter/mouseleave事件，鼠标经过的时候只会触发一次

##六、DOM对象跟jQuery对象相互转换
	Div对div的包装，使其具有各种各样已经封装好的方法。
	jQuery对象转换成DOM对象:
	方式一：$(“#btn”)[0]
	方式二：$(“#btn”).get(0)
	DOM对象转换成jQuery对象：
	$(document) 	-> 把DOM对象转成了jQuery对象
	var btn = document.getElementById(“bt n”);
	btn 	-> $(btn);
##七、筛选选择器

		选择第一个$('div:first')
		选择最后一个$('div:last')
		选择某一个$('div:eq(index)')
		小于给定index的$('div:lt(2)')
		大于给定index的$('div:gt(2)')
		选择偶数的元素$('div:even')从0算
		选择奇数的元素$('div:odd')从0算
		取反$('div:not(:odd)')
	注: $('li').mouseenter(function(){
		console.log(this)//这个this指的是js对象,如果想用jq的方法,那么就需要把它转为jq对象,就需要$(this)

