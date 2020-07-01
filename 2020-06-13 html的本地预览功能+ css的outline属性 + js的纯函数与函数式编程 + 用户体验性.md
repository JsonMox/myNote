# 2020-06-13 题目来源：http://www.h-camel.com/index.html #

# [html]图片上传时实现本地预览功能的原理是什么？ #
	原理：input的 type = file属性和window的内置FileReader对象，利用FileReader对象的readAsDataURL方法，
		 把图片数据转成base64字符串数据，然后把这个base64字符串数据赋值给一个图片标签的src。
	关于原生实现js上传文件，可以看这篇文章 https://www.jb51.net/article/147092.htm
	关于图片的上传预览，可以看这篇文章 https://blog.csdn.net/wxl1555/article/details/79165850

# [css]你用过outline属性吗？它有什么运用场景？ #
	outline 用来设置元素的周围轮廓，位于边框边缘的外围，起到突出元素的作用。
	可以设置的属性分别是（按顺序）：outline-color, outline-style, outline-width
	outline 效果上和border相同，但是border的大小会被计算到元素尺寸上面。
	
	bootstrap 里面的按钮的 active 样式就应用了这个属性用来突出强调。 需要注意的是在firefox下具有特殊性。

# [js]纯函数和函数式编程有什么关系？ #
	什么是纯函数？定义：
	1. 函数的调用参数相同，永远返回相同的结果。不依赖程序执行期间函数外部任何状态或数据的变化，仅依赖于函数入参。
	2. 函数不会产生任何可观察的副作用，例如网络请求，输入输出设备或数据突变。

	举例说明：
	1. 纯函数
		function pure(price) { return (price*10 + price)} // 返回结果仅依赖于入参price
	2. 非纯函数
		var tax = 10;
		function impure(price) { return (price*tax + price) } // 返回结果还受到外部全局变量tax的影响

	什么是副作用？
	一个可以被观察的副作用，函数内部与外部的任意交互，可能是函数内修改外部变量，或者在函数内调用另外一个函数等。
	如果纯函数调用纯函数，如果不产生副作用，那么它还是纯函数。
	副作用来自，不限于：
    * HTTP请求
    * 输出数据到console或屏幕
    * DOM查询/操作
    * Math.random()
    * 获取当前时间
    * Mutating data 变异数据
	
	纯函数的重要意义：
	1. 函数式编程中应用广泛，ReactJS Redux等优质的库需要使用纯函数
	2. 测试及重构
		纯函数利用代码维护和代码重构，你可以放心的对一个纯函数进行重构，不会担心这样做对其他函数的影响，从而减少副作用的产生。

	函数式编程： 关心数据的映射，强调函数的计算比指令的执行重要。

	关系： 要实现函数式编程，我们所封装的方法应该是抽象的，和外部状态无关，也就是需要纯函数的，js里面封装好的高阶纯函数一定程度上体现了函数式编程思想。

# [软技能] 用户体验性 #
	户体验（User Experience，简称UE/UX）是用户在使用产品过程中建立起来的一种纯主观感受。
	但是对于一个界定明确的用户群体来讲，其用户体验的共性是能够经由良好设计实验来认识到。