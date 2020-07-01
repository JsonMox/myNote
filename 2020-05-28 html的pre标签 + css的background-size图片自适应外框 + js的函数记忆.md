# 2020-05-28 题目来源：http://www.h-camel.com/index.html

# [html] 怎样在`<pre>`标签内不转义<和>符号（原样输出html标签）？
	
	<pre>what&lt;div&gtfuck</pre>  推荐使用转义字符

# [css] 固定的外框尺寸，里面的图片尺寸不固定，如何让图像自适应外框呢？
	
	#myPic{
		width: 100px;/* width的值好像没有作用 */
		height: 100px; /* height会使图片按比例变化 */
		background-image: url("./img/1.png");
        background-repeat: no-repeat;
        background-size: contain;
	}

	<div id = "myPic"></div>

# [js] 实现一个函数记忆的方法
	
	实现函数将之前操作的结果记录在某个对象中，避免重复计算。 利用js的对象和数组来实现
	
	
	var memoizer = function(memo, fundamental) {	//memo记忆数组和fundamental函数
	 
		//管理memo存储、何时调用fundamental
		var shell = function(n) {
			var result = memo[n];					
			if(typeof result !== 'number') {
				result = fundamental(shell, n);
				memo[n] = result;
			}
			return result;
		};
		return shell;
	}

	应用1.计算菲波那切数列

	//用memoizer定义fibonacci函数
	var fibonacci = memoizer([0, 1], function(shell, n) {
		return shell(n - 1) + shell(n - 2);
	});
	 
	fibonacci(10);
	>  55　　//结果

	应用2.计算阶乘
	
	//用memoizer定义factorial函数
	var factorial = memoizer([1, 1], function(shell, n) {
		return n * shell(n - 1);
	});
	 
	factorial(10);
	 
	>  3628800    //结果
 
# [软技能] 发现了一个严重的bug，需跨多个部门协作定位并修改问题时，如何提升协作的效率？