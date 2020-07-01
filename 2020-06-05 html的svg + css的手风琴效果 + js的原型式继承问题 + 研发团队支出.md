# 2020-06-05 题目来源：http://www.h-camel.com/index.html

# [html] svg如何转为字体图标？

	svg 意为可缩放矢量图形。
	<span>意大利国旗</span>
	<svg width="150" height="100" viewBox="0 0 3 2">
	   <rect width="1" height="2" x="0" fill="#008d46" />
	   <rect width="1" height="2" x="1" fill="#ffffff" />
	   <rect width="1" height="2" x="2" fill="#d2232c" />
	</svg>

	svg转为字体图标可以借助一些在线工具：
	https://icomoon.io/ ---- 完全免费，即使没有注册登录也可以使用。
	https://www.iconfont.cn/ ---- 阿里巴巴矢量图库。

# [css] 使用css实现手风琴的效果

        .container::after {
            content: ".";
            visibility: hidden;
            display: block;
            clear: both;
        }

        .nav {
            list-style: none;
        }

        .nav-items { 
            position: relative;
            float: left;
            padding: 0px 5px 5px 5px;
            /* margin-left: 30px; */
            cursor: pointer;
            background-color: red;
            color: #fff;
            font-weight: bold;

            transition: height 2s;
        }

        .nav-items:hover {
            height: 100px;
        }

     <div class="container">
         <ul class="nav">
             <li class="nav-items">网页增加</li>
             <li class="nav-items">资讯开始</li>
             <li class="nav-items">视频小时</li>
             <li class="nav-items">图片爆炸</li>
             <li class="nav-items">图库力量</li>
             <li class="nav-items">知道实时</li>
         </ul>
     </div>
 
# [js] js怎样避免原型链上的对象共享？
 	
	原型链上的对象共享问题，产生原因是原型继承方式的问题，在原型式继承中，所有子类会共享父类的引用属性，造成问题；
	可以采用构造继承的方式，或者组合继承的方式进行继承。

# [软技能] 研发团队的整体支出 

	。。。。。。
	