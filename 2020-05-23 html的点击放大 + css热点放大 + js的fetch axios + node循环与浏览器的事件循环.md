# 2020-05-23 题目来源：http://www.h-camel.com/index.html

# [html] 如何放大点击的区域？
	点击放大
	#btn:active{
    	background: red;
        transform: rotateX(-180deg);
        box-shadow: black;
	}

	悬停放大
	div{
	    width:100px;
	    transition: width 2s;//transition: property duration timing-function delay;
	    -webkit-transition: width 2s; /* Safari */
	}
	div:hover {width:300px;}

# [css] 如何使用伪元素实现增大点击热区来增加用户体验？
	
	利用伪元素来修改点击热区的样式，：active或者：hover
	 

# [js] fetch和axios请求的原理都是基于XMLHttpRequest吗？

	fetch和axios某种程度上都是XMLHttpRequest的封装，使用时都会new一个XMLHttpRequest对象。
	
	1.axios是一种基于Promise封装的HTTP客户端。 通过Promise实现对XHR的封装，是ajax技术的一种实现。

	// axios实例化
	let api = axios.create({
	    baseURL: 'localhost:8080', // 请求的域名
	    timeout: 1000, // 设置请求的超时时长，超过时长报401超时
	    method: 'get,post',
	    headers: {  // 设置请求头
	        token: ''  
	    }, 
	    params: {},
	    data: {}
	})
	// 使用axios实例,发送请求
	api.get('/data.json'); 

	2.fetch [fetʃ] 是一种HTTP数据请求的方式，是XMLHttpRequest的一种替代方案。
	fetch不是ajax的进一步封装，而是原生js。Fetch函数就是原生js，没有使用XMLHttpRequest对象。

	//通过Request构造器函数创建请求对象，GET请求，不缓存响应的结果。
	var req = new Request(URL, {method: 'GET', cache: 'reload'});
	fetch(req).then(function(response) {
	  return response.json();
	}).then(function(json) {
	  insertPhotos(json);
	});
 
# [软技能] node的循环和浏览器的事件循环有什么区别？
	
 	https://www.jianshu.com/p/b221e6e36dcb

	浏览器环境下的 异步任务 分为 宏任务(macroTask) 和 微任务(microTask)：
	
	宏任务(macroTask)：script 中代码、setTimeout、setInterval、I/O、UI render；
	微任务(microTask)： Promise、Object.observe、MutationObserver。 

	执行顺序：：
	浏览器环境
	while (true) {
    	宏任务队列.shift();
   		微任务队列全部任务();
	}

	node环境
	while (true) {
	    loop.forEach((阶段) => {
	        阶段全部任务();
	        nextTick全部任务();
	        microTask全部任务();
	    });
	    loop = loop.next;
	}

	事件循环的笔试题
	function sleep(time) {
	    let startTime = new Date();
	    while (new Date() - startTime < time) {}
	    console.log('<--Next Loop-->');
	}
	
	setTimeout(() => {
	    console.log('timeout1');
	    setTimeout(() => {
	        console.log('timeout3');
	        sleep(1000);
	    });
	    new Promise((resolve) => {
	        console.log('timeout1_promise');
	        resolve();
	    }).then(() => {
	        console.log('timeout1_then');
	    });
	    sleep(1000);
	});
	     
	setTimeout(() => {
	    console.log('timeout2');
	    setTimeout(() => {
	        console.log('timeout4');
	        sleep(1000);
	    });
	    new Promise((resolve) => {
	        console.log('timeout2_promise');
	        resolve();
	    }).then(() => {
	        console.log('timeout2_then');
	    });
	    sleep(1000);
	});