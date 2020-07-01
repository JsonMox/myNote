# 2020-05-27 题目来源：http://www.h-camel.com/index.html

# [html] 页面布局时你使用最多的标签是什么？div吗？在什么情况下会使用到div？
	
	<div>是块级元素，可用于组合其他元素的容器，浏览器在解析时会在<div>前后拆行

	常见用途是 文档布局

# [css] 不用换行的标签，怎么伪元素实现换行的效果？
	 
	span::after{
		display: block;
		content: ""
	}

	首行缩进：p{ text-indent: 2em }

# [js] 手写一个trim()的方法
	
	String.prototype.myTrim = function () {
	  return this.replace(/^\s+/, '').replace(/\s+$/, '')
	}

----------
	function myTrim(str) {
		if(str && typeof str === "string") {
			return str.replace(/^\s+/,"").replace(/\s+$/,"");
		} else {
			console.log("value is wrong data type")
		}
	}
 
# [软技能] ...