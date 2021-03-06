# 2020-06-17 题目来源：http://www.h-camel.com/index.html #

# [html] websocket是如何做心跳检测、数据加密、身份验证的？ #
	心跳检测： 这里由于websocket是长连接，如果网络断开，服务器没有触发onclose，
			  还是会向客户端发送多余的数据，这样会造成数据的丢失。心跳机制，可以检测当网络连接断开时，采取重连等措施。
			  关于实现可以参考 https://blog.csdn.net/mayuan2011/article/details/85785383

	数据加密： 主要是对发送的数据进行加密 
			  可以参考 https://www.cnblogs.com/JinMuBaoBao/articles/10268956.html

	身份验证： 对于用户身份验证，可以使用websocket拦截器，在连接前进行用户的身份验证。
			  https://blog.csdn.net/weixin_41973131/article/details/84875191
	
	
# [css] 使用css如何设置背景虚化？ #
	这里主要用到filter滤镜的属性进行设置，注意: 滤镜通常使用百分比 (如：75%), 当然也可以使用小数来表示 (如：0.75)。
>filter: none | blur() | brightness() | contrast() | drop-shadow() | grayscale() | hue-rotate() | invert() | opacity() | saturate() | sepia() | url();
	
	详细使用效果可以查看 https://blog.csdn.net/vampire10086/article/details/106800523

>Filter	描述
>none	默认值，没有效果。
>blur(px)  给图像设置高斯模糊。

>brightness(%)	给图片应用一种线性乘法，使其看起来更亮或更暗。

>contrast(%)  调整图像的对比度。

>drop-shadow(h-shadow v-shadow blur spread color)	给图像设置一个阴影效果。阴影是合成在图像下面，可以有模糊度的。

>hue-rotate(deg)  给图像应用色相旋转。

>invert(%)	反转输入图像。值定义转换的比例

>opacity(%)	转化图像的透明程度。

>saturate(%)  转换图像饱和度。

>sepia(%)  将图像转换为深褐色。
	
# [js] js源代码压缩都有哪些方法？它们的压缩原理分别是什么？ #
	js的源码压缩、混淆，是为了减小js文件大小，避免网站源码被他人盗取的一种辅助开发手段。

	压缩：删除 Javascript 代码中所有注释、跳格符号、换行符号及无用的空格，从而压缩 JS 文件大小。
	混淆：经过编码将变量和函数原命名改为毫无意义的命名，以防止他人窥视和窃取 Javascript 源代码。
	
	js压缩的原理：
	去掉注释、换行符、空格等，
	通常我们手写js时，变量、函数名等参数是有一定意义的，便于理解，例如 let conuter = 100; 但是这对于计算机来说和 let a=100; 是没有区别的。
	所以，深度压缩js会尽量缩短变量名，这样压缩后的js代码就会大量的充斥着26个单字母，大量又重复的变量足以让人不知所云。

	压缩注意：
	1. 压缩前的代码一定要规范。因为去掉空格和换行后，语句就变为一行，如果压缩前不规范，像是少分号，那么压缩后整个文件就会发生错误；
	2. 注意要备份原文件；
	3. 借助压缩工具。

	总结自： http://jo2.org/javascript-compress-and-tools/

# [软技能] 对于用户的隐私你是如何看待的？ #
	首先，我们在日常生活中正在有意无意的泄漏自己的隐私信息，究其原因，用户本身不够重视、或者说没有这个意识。
	主动泄漏的有：
	1. 外卖订单
	2. app使用前的注册，app对本机的信息访问权限
	3. 各种快递单，快递包装上面的个人信息
	4. 各种交通工具的车票，以及订购车票使用的app、小程序等
	5. 等等
	
	企业将用户隐私泄漏的有：
	1. 企业通过app获取手机通信录的权限，从而窃取隐私
	2. 购物软件的日常浏览习惯，喜爱偏好
	3. 娱乐软件的变相利诱
	4. 等等
	
	对于用户而言。我们应该保护好自己的隐私数据。对于企业来说。更应该有责任保护好用户的隐私数据！

	web的安全策略及漏洞：
	1. 同源策略
		浏览器的同源策略，限制了来自不同源的document或脚本，对当前document读取或设置某些属性。从一个域上加载的脚本不允许访问另外一个域的文档属性。
		如果没有同源限制存在，浏览器中的cookie等其他数据可以任意读取，不同域下DOM可以任意操作，ajax可以任意请求。如果浏览了恶意网站那么就会泄漏这些隐私数据
	2. 跨站脚本注入
		手动或利用工具扫描网站说有网页，注入编写的脚本。
	    防御：*禁止js通过document.cookie获取cookie，
			*输入校验，过滤不合法的字符，可以采用正则表达式，过滤、净化不必要的html标签和js事件，
			*转义特殊字符，采用htmlencode编码
			*浏览器的安全设置
	3. SQL注入
		编写恶意字符串，测试目标网站上涉及到数据库操作的地方
		防御：*禁止使用字符串拼接方式对数据库进行操作
			*数据库的权限控制，减少不必要的数据库抛出错误信息
			*转义特殊字符，采用htmlcode编码
			*净化、过滤不必要的sql保留字，例如 where or exec等
	4. CSRF 跨站请求伪造
		攻击者冒用用户的名义，向目标站点发送请求
		防御：*在客户端进行cookie的hashing，并在服务端进行hash认证
			*提交请求时需要填写验证码
			*使用one time tokens 为不同的表单创建不同的伪随机值