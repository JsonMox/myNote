# 2020-06-25 题目来源：http://www.h-camel.com/index.html #

# [html] 请问60*80的canvas占多少内存？你是怎么计算的？ #
	Canvas提供了前端像素级别的控制能力，较之传统DOM，更多的灵活度和复杂度。 
	首先思考，1*1的Canvas占用多大内存呢？在前端设置颜色时，一般用RGBA或者十六进制。
	解释一下RGBA的存储，
	A 取值0-1的小数，步长0.01，100个数字，7bit；
	RGB 0-255 RGB的存储空间应为 8*3=24Bit， 3Byte；
	十六进制存储，
	一个十六进制需要4bit，6个十六进制需要24bit， 也就是3Byte;	
	总结： 理论上一个像素的Canvas所占空间： 31bit； 但是，实际上 1个像素Canvas所占内存为4Byte，多的这1Byte也是为了方便操作。

	我们刚才的推测以及实验都是基于特定的颜色表示方法，比如 RGBA 或者#(六位十六进制)的形式
	如果我们采用别的方式呢？比如之前的 24 位，即 RGB 表示法。那结果就是100 * 100 *3, 
	如果一个颜色不用一个字节，而是更多或者更少的字节呢？这些都会影响到结果。

	更加确切的说，占用内存的多少完全取决于如何对像素进行编码和解码，

	来自一篇讲解的很好的文章 https://blog.csdn.net/azl397985856/article/details/100147918

# [css] 什么是逐帧动画？ #
	逐帧动画就是，在animation的基础上，将连续的图片运动起来。
	关键CSS属性：
	animation	@keyframes	background-position	   
	animation: animation-name .5s steps(3) infinite; //steps(3) 发生3次位移 

	steps(number_of_steps, direction)是一个阶跃函数用于把整个操作领域切分为相同大小的间隔，每个间隔都是相等的。

	控制逐帧动画的启停，添加事件监听，获取对象的animationPlayState的值，设置为 paused/running

	效果及代码： https://blog.csdn.net/Z269571627/article/details/102899242 写的非常好

# [js] 写一个方法实现promise失败后自动重试 #
	描述： getData()产生随机数，异步请求数据返回promise对象，getData()失败后间隔1s自动重试，至第五次，全部失败返回reject，任意一次成功，停止重试。
	
	编码：假定getData的promise是一个简单的随机数例子，生成一个随机数大于10则reject，小于10则resolve：
	function getData(){
    	let p = new Promise(function(resolve, reject){
    		setTimeout(function(){
    			var num = Math.ceil(Math.random()*20); //生成1-10的随机数
    			console.log('随机数生成的值：',num)
    			if(num<=10){
                    console.log('符合条件，值为'+num)
                    resolve(num);
    			}
    			else{
    				reject('数字大于10了执行失败');
    			}
    		}, 2000);
    	   })
    	   return p
      }

	加入重试：
	function myGetData(getData, times, delay) {
	    return new Promise(function(resolve, reject) {
	       function attempt () {
	        getData().then(resolve).catch(function(erro) {
	        console.log(`还有 ${times} 次尝试`)
	          if (0 == times) {
	            reject(erro)
	          } else {
	            times--
	            setTimeout(attempt(), delay)
	          }
	        })
	      }
	       attempt()
	    })
	}
	
	调用： myGetData(getData,5,1000)

	来自： https://blog.csdn.net/qq_40420294/article/details/101920789

# [软技能] 说说你对脚本语言的理解 #
	脚本语言的最大特点是不需要编译，由第三方程序或插件来运行。
	脚本语言是为了缩短，编写-编译-链接-运行 的过程，简单、易学、易用的特点，帮助程序员快速开发。
	脚本语言通常以文本保存，调用时会进行解析。