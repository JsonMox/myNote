# 2020-05-19

# [html] android手机能同时播放两个video音频吗？
	
	应该可以同时播放2个video音频，如果想要避免这种现象的出现：
	js中处理：渲染文本完成后获取所有audip标签，后一个想要播放必须先关闭前一个；绑定pasueAll()事件。
	
	var self = e.target;//获取到当前的点击的audio


# [css] 使用css写一个垂直翻转图片的效果
	
	关键属性 + hover 触发
	transition 设置过渡效果,transition: property duration timing-function delay;
		div
		{
		    width:100px;
		    transition: width 2s;
		    -webkit-transition: width 2s; /* Safari */
		}
		div:hover {width:300px;}

	transform 允许将元素旋转、缩放、移动、倾斜； // transform: rotate(180deg);
	transform-style属性指定嵌套元素是怎样在三维空间中呈现。 //transform-style:preserve-3d;
	
	<style>
        #container{
            position: relative;
            width: 300px;
            height: 200px;
            transition: all 1s linear; /* all 或指定想要变化的属性eg：width；*/
            transform-style: preserve-3d;
        }

        #front,
        #back{
            position: absolute;
            width: 300px;
            height: 200px;
            /* 属性设为0 很重要，要不然效果不同 */
            top: 0; 
            left: 0; 
        }

        #front{ background-color: green; }

        #back{ background-color: skyblue; transform: rotateX(-180deg); }
        
        #container:hover{ transform: rotateX(180deg); }
	</style>
	<body>
		<div id="container">
		    <div id="front">正面</div>
		    <div id="back">反面</div>
		</div>
	</body>

# [js] Number()的存储空间是多大？假如接口返回一个超过最大字节怎么办？
	 
 	js的number类型有个最大值（安全值）。即2的53次方，为9007199254740992。如果超过这个值，那么js会出现不精确的问题。这个值为16位。
	
	1.限制传输字节数； 2.转为String类型传输；

# [软技能] 对于前端的验收标准有哪些呢？ 
	
 	1.js css压缩，少用js特效
	2.http请求次数，dom操作次数
	3.缓存图片 css js	
	4.编码规范
	5.运行效率，速度的评估