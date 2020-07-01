# 2020-06-15 题目来源：http://www.h-camel.com/index.html #

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

# [js]写一个 document.querySelector 的逆方法 #
	document.querySelector()将返回所指定css选择器的第一个元素，返回所有元素可以使用querySelectAll()方法代替。
	EG：document.querySelector(".row").style.color = "red"; //将第一个class="row"的元素字体颜色设置为红色。
		document.querySelectorAll(".row")[0].style.color = "green"; //将第一个class="row"的元素字体颜色设置为绿色。
		document.querySelector("#demo");
		document.querySelector("p");
		document.querySelector("p.example"); //返回第一个带有 class="example" 的 p 元素。
	
	当然，还可以这样使用： 规律是--匹配到了选项，就停止。
		<h2>A h2 element</h2>
		<h3>A h3 element</h3>
		document.querySelector("h2, h3").style.backgroundColor = "red"; //将第一个h2的背景色设置为红色。h3没有变化。

	如果h3在h2之前，
		document.querySelector("h2, h3").style.backgroundColor = "red"; //将第一个h3的背景色设置为红色。h2没有变化。
# [软技能]对于前端项目，你是如何做架构设计的？ #
	大环境下的优化：
	1. css样式置顶，优化样式减少不必要的重绘
	2. javascript脚本置底，优化dom操作
	3. 减少http请求：合并静态文件，使用图标字体，合并图片、接口等方式
	4. 延时加载：首屏以外的文件延时加载，提高首屏的加载速度
	5. 避免请求空的src：因为src值为空的时候，也会发送http请求
	6. 使用压缩工具进行压缩传输
	7. 使用CDN加速：提高用户下载速度
	8. 使用缓存技术
	9. 打包优化：webpack，对代码进行拆包、压缩、组件的按需导入
	代码内部的优化：
	1. 组件化：提高代码的重用率，提高页面二次渲染的性能
	2. 使用状态管理工具：便于各个组件之间状态共享，减少不必要的请求
	3. 框架使用优化
	4. 请求优化
	5. 路由优化 
	比如列表：操作 列需要固定权限才可以使用 
	<table> 
	    <tr> 
	        <td>姓名</td> 
	        <td>账号</td>  
	        <td>出生日期</td> 
	        <td>爱好</td> 
	        <td>操作</td> 
	    </tr> 
	</table> 
	可以提取共有表格 
	<table> 
	    <tr> 
	        <td>姓名</td> 
	        <td>账号</td> 
	        <td>出生日期</td> 
	        <td>爱好</td> 
	        <child/> 
	    </tr> 
	</table>  
	在有权限的路由调用的时候传入操作列 
	<MyUserTable> 
	    <td>操作</td> 
	</MyUserTable>  
	不同的前端框架有不同的组件使用模式，
	但原理是相同的，我们通过这种方式，
	可以把操作列和操作相关的代码拿出来，
	这样没有对应权限的用户，
	就不需要加载这部分永远不会用到的代码了 

	总结自 https://www.jianshu.com/p/70804890284e