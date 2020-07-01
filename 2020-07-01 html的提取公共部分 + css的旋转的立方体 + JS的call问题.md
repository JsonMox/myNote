# 2020-07-01 题目来源：http://www.h-camel.com/index.html #

# [html] 开发静态页面时，不依赖node相关的工具，如何提取出公共部分并引入？ #
	gulp-file-include 的代码复用
	链接：https://segmentfault.com/a/1190000003043326 	
		https://blog.csdn.net/weixin_33831196/article/details/93833568


# [css] 使用css3画个旋转的立方体 #
	各种图形变换 https://c.runoob.com/codedemo/3391
	3D立方体效果实现 https://blog.csdn.net/vampire10086/article/details/107059785

# [js] 一道变态题 Number.call.call(Number, undefined, 0) 等于什么？ #
	Number.call.call(Number, undefined, 0) // 0
	Number.call.call(Number, undefined, 123) // 123
	Number.call.call(Number, undefined) // 0
	Number.call.call(Number) // 0
	Number.call.call(undefined) // TypeError： Number.call.call is not a function

>额外说一点小知识点： var a = new Boolean();  //Boolean{false}   !a; // false  
>
>what? 这是什么情况呢？
>
>这里 a 是一个 对象， a对象里面的数据 是 初始化的 false， 但是a这个对象，本身是存在的转化为Boolean就是true，!a就是false
>
>类似于c语言中的，int *a = 10; *a是一个地址，对一个地址做布尔转换，除非地址是空，否则 a 就是true
>

# [软技能] 全栈工程师 #
	全栈工程师可以在应用程序的后端和前端等应用程序开发过程中的任何一个环节工作。
	应用程序的后端包含逻辑处理、用户身份验证、数据库交互、服务器配置等。应用程序的前端是用户能看到和与之交互的部分。

	如何成为呢？ https://www.zhihu.com/question/22420900/answer/768545287 道阻且右