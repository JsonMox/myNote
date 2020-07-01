# 2020-06-14 题目来源：http://www.h-camel.com/index.html #

# [html]websocket和http有什么区别？ #
	相同点：
	1. websocket 与 http 同属于应用层协议，都是基于TCP协议进行传输数据的，都是对TCP的进一步封装。
	2. 都要遵循TCP协议中的三次握手和四次挥手。

	不同点：
	1. websocket是双向传输，而http是单向传输的；
	2. websocket浏览器与服务器通过http建立连接，之后采用TCP协议进行数据传输，而http是浏览器发起向服务器的连接，服务器预先不知道这个连接。

	再来说说 websocket 与 socket：
	socket 并不是一个协议，它是应用层与TCP/IP协议通信的中间软件抽象层，七层模型中的第五层--会话层。
	在门面模式中，将复杂的TCP/IP隐藏在后面，相当于一组接口去调用该TCP/IP协议。

	这样来看，其实websocket与socket并没有什么关联，形象的来说就像java与javascript之间的关系。
	
# [css]width属性的min-content和max-content有什么作用？ #
	自适应内部元素，
	1. fill-available的意义——自动填满剩余的空间
		就是有个div没有任何样式的时候，浏览器是按照自动填充的样式呈现的，就是100%width的样式填充的。
		按照盒子模式，不仅元素在block中可以呈现自动填满空间的样式，
		在inline-block上也是可以这样呈现的（包裹收缩的inline-block元素上，这里说的inline-block是具有收缩特性）。

		div { display:inline-block; width:fill-available; }
	2. max-content和min-content是会个跟随有定宽的的最大最小宽度，不会进行收缩。
	
		min-content的例子：
	
		将图片同级文字显示根据图片的大小一样
	
	3.fit-content的属性
	
		width:fit-content可以实现元素收缩效果的同时，保持原本的block水平状态，
		于是，就可以直接使用margin:auto实现元素向内自适应同时的居中效果了。
		就是div的自适应宽度不是100%而是内容的大小。很好的实现了，block元素的水平居中

	具体的效果，可以查看我的另一篇文章，https://blog.csdn.net/vampire10086/article/details/106764848

# [[js]说说你对js沙箱的理解，它有什么应用场景？ #
	在某些场景下，使程序跑在一个隔离的环境中，就要应用到沙箱，来避免潜在的代码注入以及未知的安全问题。
	这篇文章很有用：
 	https://segmentfault.com/a/1190000020463234

# [软技能] 规范文档 #
	......