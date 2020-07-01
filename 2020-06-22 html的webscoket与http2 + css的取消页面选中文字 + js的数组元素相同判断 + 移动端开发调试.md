# 2020-06-22 题目来源：http://www.h-camel.com/index.html #

# [html] websocket和http2有什么区别？http2能取代websocket吗？why？ #
>1.何为http/2：
>
>goole提出的开源协议，意在提高网络传输效率
>
>二进制协议
>
>采用多路复用解决 HOL Blocking 较慢的请求阻塞其他请求的问题
>
>通过压缩http头提高效率
>
>支持全双工，所以可以使用 Server Push 推送到客户端

>2.问题是：
>
>HTTP/2 Server Push 不能被代码使用，所以还得配合SSE(Server sent event)，无论从coder还是运维的角度来看，这混搭增加了复杂度。
>
>IE对http2以及SSE都支持的不好
>
>HTTP/2 连接不确定性会永远保持连接，而websocket有onclose事件
>
>多个tab页windows页可能共用一个HTTP/2连接，你无法知道Server Push来自哪一个
>
>由于多路复用，以前基于HTTP 1.1的网站提速技巧Domain sharding（由于浏览器限制同一域名最多连接数）将不再起作用。

>3.比较：
>http/2 在浏览器上限制很多，websocket较为成熟
>SSE(Server sent event) 对websocket的支持度更高

>4.结论：
>http/2完全不能代替websocket，都有自己的适用场景，app推荐websocket
>
>5.来源： https://zhuanlan.zhihu.com/p/55380863

# [css] 如何取消页面中选中的文字？ #
	解决问题： 前端页面点击较快时，会导致文字被选中，用户体验不好，所以需要这种优化。 3中方式：

	1. 如果想要取消选中文字的功能，可以屏蔽事件，双击 或 鼠标左键 均不可选择文字； 当然 这是 js
		document.onselectstart = function(){return false;}; //取消字段选择功能	
	
	2. css取消双击选中的文字
		div{
		    -moz-user-select:none;/*火狐*/
		    -webkit-user-select:none;/*webkit浏览器*/
		    -ms-user-select:none;/*IE10*/
		    -khtml-user-select:none;/*早期浏览器*/
		    user-select:none;
		}

	3. 为元素添加事件，onselectstart="return false;"
		<p onselectstart="return false;">这又是一段文字</p>	


# [js] 写一个方法判断数组内元素是否全部相同 #
	需要注意的是：
	1. 不能使用 == === 进行比较
		[1,2,3] === [1,2,3] // false 即使是相同的数据类型，但他们是不同的数组，只是元素相同而已。
	2. sort() 的排序问题
		JavaScript默认使用字典序(alphanumeric)来排序。因此，[1, 2, 5 , 10, 4, 11].sort()的结果是[1, 10, 11, 2, 4, 5]。
		如果你想正确的排序，应该这样做：[1, 2, 5 , 10, 4, 11].sort((a, b) => a - b)	 

	判断一个数组内的元素是否全部相同：
	1. 手撕代码
		function isAllEqual(array) {
	      if (array.length > 0) {
	          return !array.some(function (value, index) {
	              return value !== array[0];
	          });
	      } else {
	          return true;
	      }
	  }
	2. 先对数组去重，然后判断数组长度，为1说明数组内元素相同，为2或以上说明数组内元素不同。（个人瞎分析）

# [软技能] 做移动端开发时，你是如何调试的？ #
	web页面在移动端真机调试：https://blog.csdn.net/zjscy666/article/details/95471573
	1. 同一局域网测试
	2. 数据线真机测试
	
	开发时用PC端对移动端页面进行调试: https://www.cnblogs.com/zishang91/p/9414578.html