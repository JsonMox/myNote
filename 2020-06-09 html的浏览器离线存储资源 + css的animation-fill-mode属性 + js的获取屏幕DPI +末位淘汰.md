# 2020-06-09 题目来源：http://www.h-camel.com/index.html

# [html] 浏览器是怎么对HTML5的离线储存资源进行管理和加载的
	1. 在线的情况下，浏览器发现html头部有manifest属性，它会请求manifest文件，
	   如果是第一次访问app，那么浏览器就会根据manifest文件的内容下载相应的资源并且进行离线存储。
	   如果已经访问过app并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会对比新的manifest文件与旧的manifest文件，
	   如果文件没有发生改变，就不做任何操作，如果文件改变了，那么就会重新下载文件中的资源并进行离线存储。
	2. 离线的情况下，浏览器就直接使用离线存储的资源。 
	
	manifest 属性规定文档的缓存 manifest 的位置。<html manifest="URL">，可以指向另一个网站或者网站内的一个文件
	1. 绝对 URL - 指向另一个网站（比如 href="http://www.example.com/demo.appcache"）
	2. 相对 URL - 指向网站内的一个文件（比如 href="demo.appcache"）
	<!DOCTYPE HTML>
	<html manifest="demo.appcache">
	<head>
	<title>文档标题</title>
	</head>
	
	<body>
	文档内容......
	</body>
	
	</html>

# [css] 你有用过animation-fill-mode属性吗？它有什么应用场景？
	定义： 把物体动画地从一个地方移动到另一个地方，并让它停留在那里。
	animation-fill-mode: none|forwards|backwards|both|initial|inherit;
	none: 动画执行前后，元素属性不会改变
	forwards： 动画执行后，元素将得到应用属性
	backwards： 动画将应用第一次迭代的关键帧中定义的属性值
	both： 动画会在两个方向上扩展动画属性
	initial： 设置该属性为它的默认值
	inherit： 从父元素继承该属性

	animation-fill-mode:forwards;
	-webkit-animation-fill-mode:forwards; /* Safari 和 Chrome */

# [js] 写个方法获取屏幕的DPI
	准确的应该是ppi，指的是屏幕的分辨率。 常见的如1920*820这种表示，说的是平屏幕的物理像素尺寸。
	dpi：点每英寸 表示对角线能打印的墨滴数；
	ppi：像素每英寸 表示像素密度(对角线方向)；

	//获取DPI
	function js_getDPI() {
	    var arrDPI = new Array();
	    if ( window.screen.deviceXDPI != undefined ) {
	        arrDPI[0] = window.screen.deviceXDPI;
	        arrDPI[1] = window.screen.deviceYDPI;
	    }
	    else {
	        var tmpNode = document.createElement( "DIV" );
	        tmpNode.style.cssText = "width:1in;height:1in;position:absolute;left:0px;top:0px;z-index:99;visibility:hidden";
	        document.body.appendChild( tmpNode );
	        arrDPI[0] = parseInt( tmpNode.offsetWidth );
	        arrDPI[1] = parseInt( tmpNode.offsetHeight );
	        tmpNode.parentNode.removeChild( tmpNode );
	    }
	    return arrDPI;
	}

# [软技能] 你知道什么是末位淘汰吗？说说你对它的理解 
	首先这是需要一定的员工规模，员工的素质和工作表现呈现正态分布，比较符合末位淘汰的出发点。
	如果不是这种正态分布之下，而是单一的强调把所谓的最差员工淘汰，对其他员工的各方面都有不好的影响。
	
	积极作用：增强员工竞争意识，合理精简，减少管理成本
	消极作用：破坏合作精神，降低安全感和忠诚度，增加了人力成本，缺乏科学性，不利于年轻成员的成长