# 2020-06-27 题目来源：http://www.h-camel.com/index.html #

# [html] 如何判断用户正在操作页面？当页面一个小时没有操作时跳转到指定页面如何做？ #
	html5在页面可见性窗口中提供了一个方法，使用visibilitychange页面事件来判断当前页面可见性的状态，并针对性的执行某些任务。
	同时还有 document.title 可以改变页面title。

>document.hidden 判断用户是否在当前观看的页面，true表示页面最小化或页面后台运行或被tab切换到其他页面；false表示页面正常显示，可能被其他应用遮挡。
>
>document.visibilityState visible表示浏览器激活当前选项卡且窗口不是最小化； hidden表示页面没有被激活或窗口处于最小化；
>						  prerender表示页面正在重新生成，对用户不可见。
>
>visibilitychange事件，监听页面可见性变化，在页面被其他应用覆盖时不会触发，所以判断页面是否打开 利用此属性比较好
>
>visibilitychange事件的应用场景：
>
>页面有嵌入视频正在播放，当用户切换到其他标签页，你的标签页视频应自动暂停播放，当用户回来时继续播放；
>
>页面自动刷新动作，当用户切换到其他标签页时，因该停止刷新，当用户回来时继续之前的动作；
>
	// 当页面的可见性发生变化时会修改页面的title值
	// 各种浏览器兼容 
	var hidden, state, visibilityChange;  
	if (typeof document.hidden !== "undefined") { 
		hidden = "hidden"; 
		visibilityChange = "visibilitychange"; 
		state = "visibilityState"; 
	} else if (typeof document.mozHidden !== "undefined") { 
		hidden = "mozHidden"; 
		visibilityChange = "mozvisibilitychange"; 
		state = "mozVisibilityState"; 
	} else if (typeof document.msHidden !== "undefined") { 
		hidden = "msHidden"; 
		visibilityChange = "msvisibilitychange"; 
		state = "msVisibilityState"; 
	} else if (typeof document.webkitHidden !== "undefined") { 
		hidden = "webkitHidden"; 
		visibilityChange = "webkitvisibilitychange"; 
		state = "webkitVisibilityState"; 
	}// 添加监听器，在title里显示状态变化 
		document.addEventListener(visibilityChange, function() { 
		document.title = document[state]; 
	}, false);// 初始化 
	document.title = document[state]; 

	此外浏览器可以通过window对象的onblur onfocus事件来监听,这两个事件触发前提是 页面之前被focus过，也就是页面刚刚渲染完，
	用户没有在页面上发生任何操作时，页面不会监听这两个事件
	直到，用户操作页面触发focus，之后离开页面才会触发blur，再次点击到当前页面时才会触发focus，如此反复都会触发相应的事件。
>window.onblur触发：
>
>1.chrome浏览器console面板会触发blur(也就是说，页面和console面板之间的来回切换)，前提是之前已经是focus状态
>
>2.页面最小化
>
>3.页面中的弹窗
>
>4.focus状态下切换到其他应用
>
>window.onfocus触发：
>
>1.用户存在页面操作（包括页面中js脚本运行。如页面加载完无js运行，用户无操作，则不会触发 ）
>
>2.onblur事件触发前提下，页面最大化；
>
>3.onblur事件触发前提下，页面 从其他tab页切换回当前页面；

	想要实现跳转，结合页面用户监听事件，修改location.href的值来进行跳转。 例如 location.href = "https://www.baidu.com/"; 就会跳转到百度首页。

# [css] 如何形成BFC？ #
	BFC block formatting context 块级格式上下文。此环境中按照一定规则进行布局不会影响到盒外元素。
	浮动元素就会形成BFC，浮动元素的内部子元素主要受到浮动元素的影响，而不会受到其他浮动元素的影响。
	在CSS3中，BFC叫做 flow root，可见一斑。

>形成BFC的条件
>
>1.浮动元素： float除了 none 以外的值；
>
>2.绝对定位：position： absolut|fixed；
>
>3.display： inline-blocks|table-cells|table-captions;
>
>4.overflow: hidden|auto|scroll;

>BFC的作用：
>
>1.包含浮动元素： 高度塌陷问题：在通常情况下父元素的高度会被子元素撑开，而在这里因为其子元素为浮动元素所以父元素发生了高度坍塌，上下边界重合。这时就可以用bfc来清除浮动了。 也就是overflow 为什么能够清除浮动的另一个说明。
>
>2.不被浮动元素覆盖： 浮动兄弟遮盖问题，由于左侧块级元素发生了浮动，所以和右侧未发生浮动的块级元素不在同一层内，所以会发生遮挡问题。 利用overflow： hidden； 来触发BFC
>
>3.BFC会阻止外边距的折叠： margin塌陷问题：在标准文档流中，块级标签之间竖直方向的margin会以大的为准，这就是margin的塌陷现象。可以用overflow：hidden产生bfc来解决。
![](files/marginTX.png)


# [js] ajax请求地址只支持http/https吗？能做到让它支持rtmp://等其它自定义协议吗？ #
	HTTP协议/RTSP协议/RTMP协议的区别: https://blog.csdn.net/tanga842428/article/details/78847224

	HTTP 超文本传送协议
	FTP 文件传输协议
	RTSP real time streaming protocol 实时传输协议
	RTMP routing table maintenance protocol 路由选择表维护协议

	http将所有数据作为文件进行处理，不是流媒体协议； 而RTSP 和 RTMP是流媒体协议，适用于直播及视频会议等交互场景。	

# [软技能] 如何确保TCP包的有序传输？ #
	TCP具体是通过怎样的方式来保证数据的顺序化传输呢？

	1. 主机每次发送数据时，TCP就给每个数据包分配一个序列号并且在一个特定的时间内等待接收主机对分配的这个序列号进行确认，
	
	2. 如果发送主机在一个特定时间内没有收到接收主机的确认，则发送主机会重传此数据包。
	
	3. 接收主机利用序列号对接收的数据进行确认，以便检测对方发送的数据是否有丢失或者乱序等，
	
	4. 接收主机一旦收到已经顺序化的数据，它就将这些数据按正确的顺序重组成数据流并传递到高层进行处理。
	
	
	具体步骤如下：
	
	
	（1）为了保证数据包的可靠传递，发送方必须把已发送的数据包保留在缓冲区； 
	
	（2）并为每个已发送的数据包启动一个超时定时器； 
	
	（3）如在定时器超时之前收到了对方发来的应答信息（可能是对本包的应答，也可以是对本包后续包的应答），则释放该数据包占用的缓冲区; 
	
	（4）否则，重传该数据包，直到收到应答或重传次数超过规定的最大次数为止。
	
	（5）接收方收到数据包后，先进行CRC校验，如果正确则把数据交给上层协议，然后给发送方发送一个累计应答包，表明该数据已收到，
		如果接收方正好也有数据要发给发送方，应答包也可方在数据包中捎带过去。

	来自： https://blog.csdn.net/ggxxkkll/article/details/7894112