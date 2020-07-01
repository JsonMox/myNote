# 2020-06-08 题目来源：http://www.h-camel.com/index.html

# [html] input如何在各个浏览器下保持UI统一？
	进行初始化样式，例如：
	.input-button {
            padding: 3px 15px;
            *padding: 0 15px;
            *height: 24px;
            font-size: 12px;
            text-align: center;
            text-shadow: #CF510B 0 1px 0;
            border: 1px solid #ec5c0d;
            border-radius: 2px;
            background: #FC750A;
            background-image: -webkit-linear-gradient(top, #fc8746, #ec5d0e);
            color: #FFF;
            cursor: pointer;
            display: inline-block; 
    }

# [css] 当display: flex;遇到white-space: nowrap;会对布局有什么样的影响？如何解决
	display: flex; /* 流式布局，当屏幕变化时，元素位置不变，大小改变 */

	white-space: nowrap; /* nowrap 文本不会换行，文本会在同一行一直继续，知道遇到<br>标签 */

	当display: flex; 遇到white-space: nowrap; flex布局就会被打乱，比如内部元素超出父级范围或者其他情况。
	解决方式： 给flex布局级（例：设置“flex：1；”的子盒子）设置最小宽度为0

![](files/flexwrap.png)

# [js] promise的构造函数是同步执行还是异步执行，它的then方法呢？
	promise:
	1. promise的构造函数是同步执行，promise.then中的函数是异步执行。
	2. 构造函数中的 resolve 或 reject 只有第一次执行有效，多次调用没有任何作用。promise状态一旦改变则不能再变。
	3. promise 的 .then 或者 .catch 可以被调用多次，但这里 Promise 构造函数只执行一次。
	4. 如果在一个then（）中没有返回一个新的promise，则 return 什么下一个then就接受什么，如果then中没有return，则默认return的是 undefined.
	5. then()的嵌套会先将内部的then()执行完毕再继续执行外部的then();
	6. catch和then的连用，如果每一步都有可能出现错误，那么就可能出现catch后面接上then的情况。
	   如果在catch中也抛出了错误，则后面的then的第一个函数不会执行，因为返回的 promise状态已经为rejected了

	async/await: 基于promise实现，不能用于普通函数，与promise一样，非阻塞
	1. await关键字只能用在aync定义的函数内。async函数会隐式地返回一个promise，该promise的reosolve值就是函数return的值。
	2. 使用 async 定义的函数，当它被调用时，它返回的其实是一个 Promise 对象。
	  （当这个 async 函数返回一个值时，Promise 的 resolve 方法会负责传递这个值；当 async 函数抛出异常时，Promise 的 reject 方法也会传递这个异常值。）
	3. await 让出线程，await后面的函数先执行一便，然后跳出整个async函数来执行后面的js代码，
	   本轮事件循环执行后再回到async函数中等待await后面函数的返回值
	   如果返回值为非promise则继续执行async函数后面的代码，否则将返回的promise放入promise队列。

	首先 js 是单线程的，但是有同步异步之分；所有任务分为宏任务和微任务，微任务优先级高于宏任务
	宏任务： script的全部代码 setTimeout() serInterval() serTimediate()
	微任务： promise process nextTick

	   async function async1() {
		 console.log("async1 start");
		 await  async2();
		 console.log("async1 end");
      }

      async  function async2() {
       	console.log( 'async2');
      }

      console.log("script start");

      setTimeout(function () {
        console.log("settimeout");
      },0);

      async1();

      new Promise(function (resolve) {
        console.log("promise1");
        resolve();
      }).then(function () {
        console.log("promise2");
      });

      console.log('script end');

	执行结果：
	script start //第一个同步块
	async1 start //调用async1，执行到await
	async2 //async1 的 await让出线程来执行async2，同时 async1 的 await后面的部分 等待下一轮执行
	promise1 //第二个同步块
	script end //第三个同步块，至此 第一轮事件循环已经结束
	async1 end //第二轮事件循环，回到async1 的 await 后面的函数
	promise2 //promise属于微任务，优先级高于宏任务 setTimeout()
	settimeout // 优先级低于微任务promise

	这里说的相当透彻：： https://www.cnblogs.com/cristina-guan/p/11487403.html

# [软技能]  弹性工作制
	指在完成规定的工作任务或固定的工作时长后，员工可以灵活、自主选择工作具体时间安排。