# 2020-05-31 题目来源：http://www.h-camel.com/index.html

# [html] 你有使用过html5的rt标签吗？它有什么应用场景？
	
	<ruby>标签定义为 注释(中文音标或字符)。将 <rp> 标签与 <ruby> 和 <rt> 标签一起使用：

	<ruby>
	  汉 <rp>(</rp><rt>Han</rt><rp>)</rp>
	  字 <rp>(</rp><rt>zi</rt><rp>)</rp>
	</ruby>
	
# [css] 用css画一个平行四边形
	CSS的40种常见图形绘制：：：http://www.webhek.com/post/40-css-shapes.html
	
	#parallelogram {
	    width: 150px;
	    height: 100px;
	    -webkit-transform: skew(20deg);
	       -moz-transform: skew(20deg);
	         -o-transform: skew(20deg); /* skew(x-angle, y-angle) 沿着x-angle， y-angle 2D倾斜 */
	    background: red;
	}

# [js] 写一个方法粘贴复制的图片并显示出来
	<div> 标签要设置为 conteneditable = "true"; 
	监听 paste 事件：
	document.addEventListener('paste', function (event) { 
	  console.log(event) 
	})

# [软技能] 什么是cookie伪造？如何防止伪造？
	cookie欺骗是指用户在登陆的时候容易被获取权限，植入浏览器中，从而访问后台数据。
	
	防伪造： 可以为cookie多添加一个userKey字段，该值为userId或者固定的字符串，
			经过MD5加密，MD5(userId + "mysite") 或 MD5(userName + "mysite")
			服务端在判断权限时，先判断userKey是否正确。
	或者多重加密混合使用。