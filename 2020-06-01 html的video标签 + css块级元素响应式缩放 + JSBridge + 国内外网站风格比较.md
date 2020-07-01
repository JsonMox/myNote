# 2020-06-01 题目来源：http://www.h-camel.com/index.html

# [html] html5的video如何附带字幕？
	<video> 标签定义视频，比如电影片段或其他视频流。目前，<video> 元素支持三种视频格式：MP4、WebM、Ogg。

	<video width="320" height="240" autoplay >
	  <source src="movie.mp4"  type="video/mp4">
	  <source src="movie.ogg"  type="video/ogg">
	</video>
	属性： atuoplay(自动播放) loop(循环播放) muted(静音) controls(显示用户控件，播放按钮等)
 
	参考：https://blog.csdn.net/cuixiping/article/details/7760845#
	
	<video id="mainvideo" controls autoplay loop>
	  <track src="en_track.vtt" srclang="en" label="English" kind="caption" default>
	  <track src="cn_track.vtt" srclang="zh-cn" label="简体中文" kind="caption">
	</video>
	
	字幕：
	WebVTT : Web Video Text Track  (Web视频文本轨道)
	TTML : Timed Text Markup Language (时序文本标记语言)


# [css] 在响应式布局中，如何使用纯css使得块元素等比缩放？
	js实现宽度自适应，高度随着宽度变化而变化，获取元素宽度 根据比例重新计算出高度，然后赋值给元素。
	
	元素的margin和padding属性的值（无论是上下边距还是左右边距）如果设置为百分比，都是以宽度为基准计算。
	1. padding-top
	<style>
        .ac_coupon-wrap {
            height: 0;
            padding-top: 20%;
            position: relative;
            background-color: rebeccapurple;
            overflow: hidden;
        }

        .ac_coupon-content {
            position: absolute;
            top: 0;
            width: 100%;
            height: 100%;
            background-image: url("./img/1.png");
            background-size: contain;
            background-repeat: no-repeat;
        }
    </style>

    <div class="ac_coupon-wrap">
	    <div class="ac_coupon-content">
	        <!-- 内容 -->
	    </div>
    </div>
	
	解析：利用padding-top来撑起元素的高度，此时content元素被挤到下方，改变content的定位方式为absolute；
		 父级元素会存在高度塌陷，需要清除浮动，迫使父级重新检查内部的子元素，发现是absolute就撑开高度。

	2. padding-bottom
		#colorBlock {
            padding-bottom: 60%; /* 5:3显示，可修改为其他比例 */
            width: 100%;
            height: 0;
            background: red;
        }

# [js] 说说你对JSBridge的理解 
	https://zhuanlan.zhihu.com/p/32899522

# [软技能] 对于网站的风格，你能说说在国内与国外的区别有哪些 

	1. 对于网站的理解：
	国内： 电商平台或网络营销工具； 
	国外： 一种传播沟通工具，类似报纸杂志，更简便。
	2. 谁是网站设计师
	国内： 只有那些画出漂亮界面的专业人士才配得上 设计
	国外： 参与工作的任何人，视觉设计、交互设计、页面架构 --- Designer，设计包含项目的方方面面。
	3. 设计网站目标
	国内： 吸引人眼球，鹤立鸡群
	国外： 节约浏览者时间，聪明且有效
	4. 网站制作的优劣
	国内： 是否美观、大气、科技、国际化
	国外： 严格按照每项指标工作

	总结： 国内网站风格 -- 文字多 图片多； 国外网站风格 -- 干净、整洁