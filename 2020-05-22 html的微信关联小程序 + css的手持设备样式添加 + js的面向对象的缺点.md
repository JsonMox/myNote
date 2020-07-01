# 2020-05-22 题目来源：http://www.h-camel.com/index.html

# [html] 微信公众号如何打开关联的小程序？
	
	登录微信公众平台，再左侧菜单栏中点击“小程序管理”，添加关联小程序。

# [css] 怎么给手持设备添加特殊样式
	
	就是一个html再不同终端下引入不同的css样式的问题。
	思路：判断时pc端还是移动终端，然后分别在js中插入相应的css样式文件即可。
 	<script type="text/javascript">
	    /*根据不同的客户端(这里指移动端和pc端)引入样式*/
	    var includeLinkStyle = function (url) {
	      var link = document.createElement('link');
	      link.rel = 'stylesheet';
	      link.type = 'text/css';
	      link.href = url;
	      document.getElementsByTagName('head')[0].appendChild(link);
	    };
	    var browserRedirect = function () {
	      /* 判断是pc端还是移动端  网上有很多，我只用其中一种演示*/
	      var sUserAgent = navigator.userAgent.toLowerCase();
	      var bIsIpad = sUserAgent.match(/ipad/i) == "ipad";
	      var bIsIphoneOs = sUserAgent.match(/iphone os/i) == "iphone os";
	      var bIsMidp = sUserAgent.match(/midp/i) == "midp";
	      var bIsUc7 = sUserAgent.match(/rv:1.2.3.4/i) == "rv:1.2.3.4";
	      var bIsUc = sUserAgent.match(/ucweb/i) == "ucweb";
	      var bIsAndroid = sUserAgent.match(/android/i) == "android";
	      var bIsCE = sUserAgent.match(/windows ce/i) == "windows ce";
	      var bIsWM = sUserAgent.match(/windows mobile/i) == "windows mobile";
	      /* 根据不同的客户端引入样以及加载页面 */
	      if (bIsIpad || bIsIphoneOs || bIsMidp || bIsUc7 || bIsUc || bIsAndroid || bIsCE || bIsWM) {
	        console.log("phone");
	        /*includeLinkStyle("样式地址");*/
	        includeLinkStyle("mobile.css");
	        $('body').load('mobile-index.html');
	      } else {
	        console.log("pc");
	        includeLinkStyle("pc.css");
	        $('body').load('pc-index.html');
	      }
	    };
	    browserRedirect();
  	</script>

# [js] 举例说明面向对象编程有什么缺点？
	 
	优点
	(1)是一种全新的系统分析设计方法（对象、类、结构属性、方法）。
	(2)适用于各类信息系统的开发。
	(3)实现了对客观世界描述到软件结构的直接转换 ，大大减少后续软件开发量。
	(4)开发工作的重用性、继承性高，降低重复工作量。
	(5)缩短了开发周期。

	缺点：
	(1)需要一定的软件支持环境。
	(2)不太适宜大型的MIS开发，若缺乏整体系统设计划分，易造成系统结构不合理、各部分关系失调等问题。
	(3)只能在现有业务基础上进行分类整理，不能从科学管理角度进行理顺和优化。
	(4)初学者不易接受、难学。
 
# [软技能] 举例说明有哪些场景会用到很强的数学知识？
	
 	数据结构、算法、数学建模