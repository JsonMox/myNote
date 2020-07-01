# 2020-05-16

# [html] 你有使用过template标签吗？说说它的用途有哪些？

	<template>是H5的新标签，就是模板，默认的display为none。可以将列表项放入<template>标签中，进行批量渲染。
	简单使用：
	<template id="tpl">
        <div class="linear-layout">
            <span>静音</span>
            <i class="iconfont icon-duigou linear-icon"></i>
        </div>
        <div class="linear-interval"></div>
    </template>
	在js中的操作：
	var tem = document.getElementById("tpl");
	document.write(tem);

	要操作template中的内容，要使用template.content
	var template = document.getElementById('tpl');
	var layout = template.content.querySelector('div');
	var text = template.content.querySelector('span');

# [css] 如何让背景图片固定不随滚动条滚动？
	
	background-size: cover; //保证全覆盖
	background-attachment: fixed; //保证背景固定不动
 

# [js] js的循环结构有哪些？
	 
	js有4种循环结构：
		1.for循环 ==》多次遍历代码块
	
		2.for / in循环==》遍历对象属性 for (i in obj）{ //dosomething; }
	
		3.while循环==》当指定条件为true时，循环代码块
		
		4.do while循环==》当指定条件为true时，循环代码块


# [软技能] 如果要你实现下拉刷新和上拉加载，说说你的技术方案
	 
	微信小程序开发是，只需要在js中使用onPullDownRefresh命名的方法就可以实现。
	
	js中的实现思路： 为目标对象添加 touchstrat 和 touchmove 的事件监听，然后根据srcllTop的属性值以及元素的移动位移分别对上拉和下拉进行不同的处理。
	
	收录于：03.javascript编程实例中008，借助于@keyframes标签 创建动画从一个css样式转到另一个css样式。