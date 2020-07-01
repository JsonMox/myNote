# 2020-06-11 题目来源：http://www.h-camel.com/index.html #

#  [html] 切页面时，每次都动手刷新看效果很麻烦，如果要让你写一个实时刷新预览的工具你该怎么写？ #
	1. 在 <meta> 标签里面设置， <meta http-equiv = "refresh" content = "20">  每20s刷新一次
	2. 在script中利用定时器setTimeout()：
		<script type = "text/javascript">
			function refresh () {
				window.location.reload();
			}
			
			setTimeout(refresh, 2000);
		</script>
	
# [css] 使用纯CSS实现3D按钮效果 #
	想要营造出3维立体的感觉，离不开box-shadow属性，手写一个康康,不怎么好看
	.container {
            width: 800px;
            height: 500px;
            margin-left: 300px;
            margin-top: 40px;
            padding: 30px;
            border: 1px solid lightblue;
            background-color: lightgray;
        }

        a,
        a:hover {
            text-decoration: none;
        }

    #manner1 {
            width: 50px;
            height: 30px;
            padding: 10px;
            box-shadow: 5px 4px 12px 3px grey;
            border-radius: 5px;
            border-bottom: 3px solid red;
            background-color: orange;
            line-height: 30px;
            color: #fff;
        }

    #manner1:active {
        border-bottom: 1px solid red;
        box-shadow: 1px 1px 15px 0px grey;
    }

	<div class="container">
        <a id="manner1" type="button" href="javascript:void(0);">PUSH ME !</a>
    </div>

	发现一个神奇的网站资源 https://www.html5tricks.com/
 
# [js] 使用js实现一个图片剪裁的功能  #
	https://blog.csdn.net/dreamfj/article/details/82842715

# [软技能] 说下你对噪声的理解，它在前端中有哪些应用场景呢？ #
	随机不只是Math.random
	https://juejin.im/post/5d285648f265da1b942176d8
	 