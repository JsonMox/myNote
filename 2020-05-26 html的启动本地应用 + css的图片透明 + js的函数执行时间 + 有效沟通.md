# 2020-05-26 题目来源：http://www.h-camel.com/index.html

# [html] 如何在网页中打开腾讯QQ？
	
	新增注册表信息，URL Protochol

# [css] 给一个图片设置透明有哪些方式？
	 
	1. visiblity: hidden;
	2. opacity: 0; || background:rgba(255,255,255,0.3);
	3. IE专属滤镜 filter:Alpha(opacity=x)，x 的取值从 0 到 100，如filter:Alpha(opacity=80)
	4. 双层div嵌套，absolute定位，覆盖。

# [js] 你是如何比较js函数的执行速度的？
	
	函数的执行时间计算： 时间戳的差值
	1. var start = Date.now(); 缺点：1毫秒内测不出来。

	2. console.time的方法
	console.timeEnd是记录结束时间点并输出与开始时间点的时间差。

	console.time(1);
	function A();
	console.timeEnd(1);
	
	空间复杂度：
 
# [软技能] 如何高效沟通  
	 
	1.文档虽然重要，但不是必须的；
	2.最有效的沟通方式 -- 面谈；
	3.有效的沟通；

	精神的充实，完成使命的成就感仍然是每个人都需要的精神食粮，没有这些，生命一样不会辉煌。