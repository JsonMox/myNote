# 2020-06-23 题目来源：http://www.h-camel.com/index.html #

# [html] 跨标签页的通讯方式有哪些 #
	1. websocket： 全双工通信协议，可以实现多标签的通信；
	2. localstorage： 浏览器多个标签共用的存储空间，注意如果不手动删除，是永久不会失效的；
	3. sharedworker： html5 浏览器的新特性，可以被多个winodw共同使用，但需要这些标签页都是同源的
		// sharedWorker所要用到的js文件，不必打包到项目中，直接放到服务器即可
		// 注册一个onmessage监听信息的事件，客户端(即使用sharedWorker的标签页)发送message时就会触发。
		let data = ''
		onconnect = function (e) {
		  let port = e.ports[0]
		
		  port.onmessage = function (e) {
		    if (e.data === 'get') {
		      port.postMessage(data)
		    } else {
		      data = e.data
		    }
		  }
		}
		
		webwork 无法在本地使用，会受到浏览器本身的安全机制。

# [css] 实现一个下拉不到底的橡皮筋效果 #
	思路： 利用 animation动画去设置每一帧的transform scale3d效果。
	效果和代码： https://blog.csdn.net/qq_44699174/article/details/106090933

# [js] 异步请求重试策略有哪些呢？ #
	nodejs异步请求重试策略总结 https://blog.csdn.net/weixin_33682790/article/details/85867933
	nodejs重试机制实现 https://blog.csdn.net/weixin_39169700/article/details/79759725
	promise的重试机制 https://blog.csdn.net/qq_40420294/article/details/101920789

# [软技能] LF和CRLF的区别是什么？ #
	都是文本换行方式，
	1. CRLF carriage return line feed  回车换行，“\r\n” windows环境的换行方式；
	2. LF line feed 换行，“\n” linux环境下的换行方式；