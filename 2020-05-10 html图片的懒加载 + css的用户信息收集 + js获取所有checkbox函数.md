# 2020-05-10
# [html] 举例说明图片懒加载的方案有哪些 #
	懒加载：在当前页面，滑动页面时能够看到图片的时候再进行加载。
* window.scroll 监听各种 top 与 height 并使用 _.throttle 节流，但是不好理解各种 top 与 hegith

* window.scroll 监听 getBoundingClientRect() 并使用 _.throttle 节流，没有一个统一事件，相对复杂

* InterpObserver，浏览器推出了一个事件，方便简单

* img.loading=lazy，浏览器直接给你解决，开发者直接标注属性
	将问题拆成2个部分：
	1.如何判断图片出现在当前窗口；
	2.如何控制图片的加载
## 方案一 ##
	1.如何判断图片出现在当前窗口
	关于图片的各种高度对比。。。。。。
	静态参数:
	clientTop： 表示一个元素的上边框的宽度
	offsetTop： 指 obj 距离上方或上层控件的位置
	clientHeight： 浏览器可视高度
	scrollTop: 浏览器的滚动高度

	动态参数：
	可以通过监听 window.scroll事件
	
	2.如何控制图片的加载 <img src = "ocean" alt = "海洋">
	先设置一个临时属性，控制加载时利用setAttribute()进行替代
	
	3.实践：

	var winPos = $(window).scrollTop(); //获取页面滚动到的地方距顶端距离
	$("#myPic").setAttribute("src", "../img/2.png");

## 方案二 ##
	改进一下，window.scroll 监听 Element.getBoundingClientRect() 并使用 _.throttle 节流。
	1.如何判断图片出现在当前窗口
	引入api，Element.getBoundingClientRect()返回元素的大小和相对于视图窗口的位置。
	<script>
        window.addEventListener("scroll", function () {
            var px = document.getElementById("im").getBoundingClientRect().top;
            if (px < 622) {
                document.getElementById("im").setAttribute("src", "./img/2.png");
            }
        })
    </script> 
	2.监听事件的优化 
	加个节流器，提高性能。工作中一般使用 lodash.throttle 就可以了，万能的 lodash 啊！
	_.throttle(func, [wait=0], [options={}])
	
	debounce去抖：一个搜索框，输入1，请求数据得到包含1的数据；再输入2，得到包含12的数据...
	假如用户想得到1234的数据，就要调用4次接口得到，浪费请求资源，本地数据渲染也会走多次。
	
	throttle节流：一个按钮，点击要调用接口，接口成功跳转到下一个页面。这是频繁的点击，频繁的调用接口，会导致页面跳转多次。throttle可以解决此问题。

## 方案三 ##
	再改进一下
	1.如何判断图片出现在当前窗口
	浏览器出了一个三合一事件: InterpObserver API，一个能够监听元素是否到了当前视口的事件，一步到位！
	事件回调的参数是 InterpObserverEntry 的集合，代表关于是否在可见视口的一系列值，其中，entry.isIntersecting 代表目标元素可见

	const observer = new InterpObserver((changes) => {
	  // changes: 目标元素集合
	  changes.forEach((change) => {
	    // interpRatio
	    if (change.isIntersecting) {
	      const img = change.target
	      img.src = img.dataset.src
	      observer.unobserve(img)
	    }
	  })
	})
	
	observer.observe(img)

	InterpObserver 除了给图片做懒加载外，还可以对单页应用资源做预加载。

## 方案四 ##
	浏览器的支持， img标签的loading属性，需要浏览器的兼容性处理
	<img src="shanyue.jpg" loading="lazy">

# [css] 除了可以用js跟踪用户信息外，如果不用js，使用纯css怎么做？ #
	收集关于用户的一些基本信息，例如 屏幕分辨率（当浏览器最大化时）以及用户使用的什么浏览器（引擎）
	可以监测用户是否点击某个链接或鼠标悬停在某个元素上，用来 追踪用户悬停的链接，甚至可以 追踪用户如何移动鼠标（在页面使用不可见的字段），
	普遍认为：css进行追踪更为简洁 优雅。
	* 用 CSS 你可以使用 url(“foo.bar”) 属性引用外部资源添加图像，用 CSS 创建一个选择器，当用户点击某个链接时调用某个特定的 URL
		#link2:active::after {
		  content: url('track.php?action=link2_clicked');
		}
 
	* 浏览器监测 基于 @supports Media-Query 的，我们可以监测浏览器的一些特殊的属性，例如 -webkit-appearance
		@supports (-webkit-appearance: none) {
		  #chrome_detect::after {
		    content: url('track.php?action=browser_chrome');
		  }
		}

	* 字体监测 
		对于 字体监测，需要定义一个新的字体，如果一个字体存在，文本会尝试使用该字体进行样式设置，
		然而，当用户在系统上找不到该字体时，定义的字体会作为备用，在这种情况下，浏览器会尝试去加载定义的字体并在服务器上调用追踪脚本
		/** Font detection **/
		@font-face {
		  font-family: Font1;
		  src: url('track.php?action=font1');
		}
		 
		#font_detection1 {
		  font-family: Calibri, Font1;
		}
	* 悬停监测 需要定义关键帧，每次使用关键帧都要去请求一个URL
		@keyframes pulsate {
		  0% {
		    background-image: url('track.php?duration=00');
		  }
		  20% {
		    background-image: url('track.php?duration=20');
		  }
		  40% {
		    background-image: url('track.php?duration=40');
		  }
		  60% {
		    background-image: url('track.php?duration=60');
		  }
		  80% {
		    background-image: url('track.php?duration=80');
		  }
		  100% {
		    background-image: url('track.php?duration=100');
		  }
	   }
	* 输入监测 监测用户选中了某个复选框，我们可以使用 CSS 提供的 :selected 选择器
		#checkbox:checked {
  			content: url('track.php?action=checkbox');
		}
		为了监测字符串，我们结合了 HTML pattern 属性，可以解决一些基本的输入验证，再结合 :valid 选择器，浏览器当输入匹配成功时会去请求我们的追踪站点。
		<input type="text" id="text_input" pattern="^test$" required>
		#text_input:valid {
		  background: green;
		  background-image: url('track.php?action=text_input');
		}

# [js] 写一个获取页面中所有checkbox的方法 #
	function getAllcheckbox() {
	    var isCheckbox = new Array();
	    var inputs = document.getElementsByTagName("input");
	    for(let i = 0; i <= inputs.length; i++) {
	        let obj = inputs[i];
	        if ( obj.type == "checkbox") {
	            isCheckbox.push(obj);
	        }
	    };
	    return isCheckbox;
	}

# [软技能] 你之前用的是什么协同工具 #
	禅道
	各组分工明确，还有专职的PMO团队，负责制定整体的项目计划并保证执行环节的各节点，
	几乎随便啥事儿，都有一个标准化流程等在那里，一旦被触发，先做什么后做什么一目了然。
	偶尔有个事儿流程没有包含，那么做的第一件事，一定是先把这个空白给补上，保证下次再遇到，就可以有流程来控制。