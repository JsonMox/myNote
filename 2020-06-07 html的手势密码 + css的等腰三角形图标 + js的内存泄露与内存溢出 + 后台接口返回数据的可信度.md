# 2020-06-07 题目来源：http://www.h-camel.com/index.html

# [html] 使用H5实现一个手势密码

	参考文章：： https://blog.csdn.net/weixin_34013044/article/details/93798067

	需要引入 jq插件jquery.gesture.password.min.js

# [css] 用css实现一个等腰三角形的小图标

	各种三角形的绘制 https://www.cnblogs.com/chengxs/p/11406278.html

		.triangle-up {
            width: 0;
            height: 0;
            border-left: 50px solid #fff;
            border-right: 50px solid #fff;
            border-bottom: 100px solid black;
            /* border-top: 100px solid red; */
        }

# [js] 内存泄漏和内存溢出有什么区别
 	
	  1. 内存溢出： 指的是程序运行的一种错误，当程序运行所需的内存超过了剩余可用内存，就会出现内存溢出错误，
		 内存溢出一般是由于内存泄露造成的，占用的内存得不到释放，影响系统性能，所以造成内存泄漏的原因也是造成内存溢出的原因。
	
	  2. 内存泄漏： 占用的内存没有得到及时的释放，积累过多就会造成内存溢出。
	  	 
	    全局变量引起：根据js的垃圾回收机制，全局变量是不会被回收的，意外的、不需要的全局变量过多就会造成内存泄漏；  
		function fn () {
			b = new Array[1000000
		  	a = [] //不小心没有var定义，这时候a变量是全局的
		}
		fn()
	 
		闭包： 函数内部的变量由于闭包的引用而得不到释放，会造成内存泄漏；
		function fn1() {
		  var arr = new Array[100000];
		  function fn2() {
		    console.log(arr.length)
		  }
		  return fn2;
		}
		var f = fn1();
		f();
		f();
		f = null // 让内部函数成为垃圾对象，释放闭包

		<body>
			<div id="oDiv">Lee</div>
		
			<script type="text/javascript">
			    function box() {
			        var oDiv = document.getElementById('oDiv'); 
			        var text = oDiv.innerHTML;
			        oDiv.onclick = function () {
			            alert(text);
			        };
			        oDiv = null;       //解除引用,等待垃圾回收
			        alert(oDiv);       //null,说明已经不存在了
			    }
			    box();
			</script>
		</body>
	
		计时器、回调函数、监听等事件 没有及时清除  clearInterval(intervalId) // 及时清理计时器； removeEventListener();// 移除监听事件；

		DOM的属性、方法添加：也会造成变量引用得不到释放，造成内存泄漏。

# [软技能] 后台接口返回的数据可信吗？如果不可信，那么前端应该怎么做？
	前后端分离之后，前端的责任是展现和交互，不负责核心业务逻辑。
	服务器端是前端唯一的数据来源，前端只能调用服务器端的API获取数据。
	对服务器端API提供的数据，前端应该进行基本语法和JSON格式上的校验，保证展现和交互不出现错误。但不应该做业务逻辑上的校验，因为想做也做不到，或者增加了复杂性。
	验证一个数据是否合法，就需要更多数据支持，而这些更多数据还是调用服务器端API获取的。

	通过API提交给服务器端的数据，服务器端要做完全验证。

	转自 https://www.zhihu.com/question/326313810