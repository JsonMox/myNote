# 2020-06-30 题目来源：http://www.h-camel.com/index.html #

# [html] 怎样禁用页面中的右键、打印、另存为、复制等功能？ #
	1. 禁用右键：属于浏览器默认事件，可以设置
		//第一种 建议用
		document.oncontextmenu = function(){
		  　　return false;
		}
		//第二种
		document.oncontextmenu = nocontextmenu; // for IE5+
		//第三种
		document.onmousedown = norightclick; // for all others
	
	2. 禁用打印，不能实现完全禁用，可以实现打印空白
		@media print {
			body{ display: none; }
		}
	3. 禁用文本选中，禁止复制
		document.onselectstart = function () {
			return false;
		};
		//or
		body{ onselectstart = "return false" }
	4. 取得控件的绝对位置
		借助 offset属性，
		或者obj.getBoundingClientRect();

	来自 https://blog.csdn.net/weixin_45598686/article/details/106398050

# [css] translate3D有什么作用？ #
	transform:translate3d(x,y,z); //定义为3D转换，但效果上还是在一个平面内显示，为3轴方向上的位移, px
	
	在线演示 https://www.softwhy.com/article-8720-1.html

# [js] ReferenceError和TypeError有什么区别？ #
	ReferenceError: 引用错误，作用域中找不到
	TypeError： 类型错误，在作用域中找到了，但被要求做不可能做的事情

# [软技能] 你想当全栈工程师吗？ #
	全栈工程师可以在应用程序的后端和前端等应用程序开发过程中的任何一个环节工作。
	应用程序的后端包含逻辑处理、用户身份验证、数据库交互、服务器配置等。应用程序的前端是用户能看到和与之交互的部分。

	如何成为呢？ https://www.zhihu.com/question/22420900/answer/768545287 道阻且右