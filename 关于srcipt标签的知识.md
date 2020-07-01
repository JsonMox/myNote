# script标签的知识 #

----------

## script标签的执行顺序 ##
>script 是按照它们出现的顺序被执行的，执行时会阻塞程序运行，建议页面实现类的js放到body之前，动作、交互、事件驱动、对于dom属性的访问操作可以放在body的dom之后尾标签之前。这样会加快网页的加载速度。

## script标签的async和defer属性 ##
>HTML5 添加了两个工具来控制脚本的执行。

>async 表示“不用马上执行它”。更具体地它表示：我不介意你在整个网页加载完成之后执行这个脚本，把它放在其他脚本执行之后。这对于统计分析脚本来说非常有用，因为页面上没有其他的代码需要依赖于统计脚本执行。定义一个页面需要的变量或函数在 async 的代码中是不行的，因为你无法知道什么时候 async 代码将会被实际执行。

>defer 表示“等待页面解析完成之后执行”。它大致等价于将你的脚本绑定到 DOMContentedLoaded 事件，或者使用 jQuery.ready。当这个代码被执行，DOM 中的一切元素都可用。不同于 async，所有加了 defer 的脚本将会按照它们出现在 HTML 页面中的顺序执行，它只是推迟到 HTML 页面解析完毕后开始执行

## script标签的atype属性 ##
>在 script 标记上是否写上 type=text/javascript 没有什么关系。如果你通过 type 设置一个非 JavaScript 的 MIME 类型，浏览器不会执行它。当你想要定义你自己的语言时，这会很酷：

	<script type="text/emerald">
	  make a social network
	    but for cats
	</script>

>这段代码实际执行结果由你自己决定，例如： 自己编写runEmeraldCode函数

	<script>
	  var codez = document.querySelectorAll('script[type="text/emerald"]');
	  for (var i=0; i < codez.length; i++)
	    runEmeraldCode(codez[i].innerHTML);
	</script>

>如果你有特别的需要，你也可以重写页面上 script 标记的默认 type，方法是通过一个 meta 标记：

	<meta http-equiv="Content-Script-Type" content="text/vbscript">
>或者一个请求返回一个 Content-Script-Type header。

## script标签的integrity属性 ##
>integrity 属性是子资源完整性新规范的一部分。它允许你为脚本文件将包含的内容内容提供一个 hash。这意味着可以防止在传输的时候内容丢失或者被恶意修改。就算使用了 SSL，这个规范也是有意义的，因为有时候你要加载的资源是你无法控制的站外资源，比如 code.jquery.com。

>如果你选择使用它，你要在 script 标记里包含一个 hash 类型以及 hash 值，将它们以连字符隔开。看起来类似下面这样：
	
	<script
	  src="//code.jquery.com/jquery.js"
	  integrity="sha384-oqVuAfXRKap7fdgcCY5uykM6+R9GqQ8K/uxy9rx7HNQlGYl1kPzQho1wx4JwY8wC">
	</script>

## script标签的crossorigin属性 ##
>虽然还没有完全被标准化，但是一些浏览器支持 crossorigin 属性。基本的想法是，浏览器会限制对非同源资源的使用（同源资源是指相同的协议、hostname 以及端口，例如： `http://google.com:80）。

>这是为了防止你，例如，向你的竞争对手网站发请求，注销你的用户在对方网站的账号（这不好！）。这个问题牵扯到 script 标记虽然有点意外，但如果实现了 crossorigin，你只要加一个 handler 到 window.onerror 事件上，就能在看控制台上看到一些警告信息，提示你引入了一个不该引入的外站脚本。在安全的浏览器下，除非你指定 crossorigin 属性，不然加载外站脚本不会出错。

## document.currentScript ##
>document.currentScript 的属性。它指向当前正在被执行的脚本。如果你想要从你嵌入的 script 标记中拿一些属性来用，它会非常有用。我个人非常高兴它还没有被完全支持，否则它会让我们在一部分工作中渴望嵌入更复杂的代码。 IE并不支持。

## script 标记和 innerHTML ##
>通过 DOM 动态添加到页面上的 script 标记会被浏览器执行：

	var myScript = document.createElement('script');
	myScript.textContent = 'alert("✋")';
	document.head.appendChild(myScript);

>通过 innerHTML 动态添加到页面上的 script 标记则不会被执行：

	document.head.innerHTML += '<script>alert("✋")</script>';
为什么会是这样的原因不是很确定，但是它解决了一个小问题：“是否有一个办法让一个 script 标记在 Chrome 代码检查器中显示但不实际执行？”你可以利用这个来对你的同事做恶作剧。