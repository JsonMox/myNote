# 2020-06-11 各大网站前端界面中的 `<meta>` 标签 #
	
>Meat对象代表HTML的一个<meta>元素，提供HTML元素的元信息，比如描述、关键字、刷新频率。对象属性：

>content 设置或返回<meta>元素的content属性

>httpEquiv 把content属性连接到一个HTTP头部

>name 把content属性连接到某个名称

>scheme 设置或返回用于解释content属性的格式

- 百度主页
- 阿里主页
- 美团主页
- 滴滴主页
- 字节跳动
- 淘宝主页
- 京东主页
- 华为主页
- 微软官网 

## 百度主页 ##
	<meta http-equiv="Content-Type" content="text/html;charset=utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
    <meta content="always" name="referrer">
    <meta name="theme-color" content="#2932e1">
    <meta name="description" content="全球最大的中文搜索引擎、致力于让网民更便捷地获取信息，找到所求。百度超过千亿的中文网页数据库，可以瞬间找到相关的搜索结果。">

## 阿里主页 ##
	<meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
	<meta name="ahot-aplus" content="1">
	<meta name="aplus-rate-ahot" content="0.5">
	<title>阿里云-上云就上阿里云</title>
	
	<!-- TRACK 埋点-->
	<meta name="data-spm" content="5176" />
	<meta name="description" content="230万用户正享用阿里云提供的云服务器、云数据库、云存储、CDN、大数据等服务，7x24小时售后支持，专业快速备案，助企业无忧上云。">
	<meta name="keyword" content="阿里云，云数据库，云服务器，云计算，域名注册">
	
	<!-- SHARE 分享-->
	<meta property="og:title" content="阿里云-上云就上阿里云" />
	<meta property="og:description" content="230万用户正享用阿里云提供的云服务器、云数据库、云存储、CDN、大数据等服务，7x24小时售后支持，专业快速备案，助企业无忧上云。" />
	<meta property="og:image" content="https://img.alicdn.com/tfs/TB1qNVdXlGw3KVjSZFDXXXWEpXa-620-620.png" />

## 美团主页 ##
	<meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>美团网-美食_团购_外卖_酒店_旅游_电影票_吃喝玩乐全都有</title>
    <meta name="description" content="美团网:美食攻略,外卖网上订餐,酒店预订,旅游团购,飞机票火车票,电影票,ktv团购吃喝玩乐全都有!店铺信息查询,商家评分/评价一站式生活服务网站">
    <meta name="keywords" content="美食,团购,外卖,网上订餐,酒店,旅游,电影票,火车票,飞机票">
    <meta name="format-detection" content="telephone=no">
    <meta name="format-detection" content="address=no">
    <meta name="lx:category" content="group">
    <meta name="lx:cid" content="">
    <meta name="lx:appnm" content="mtpc">
    <meta name="lx:autopv" content="off"> 

## 滴滴官网 ##
	<meta charset="utf-8">
	<meta name="baidu-site-verification" content="9YtFhXJtQL" />
	<meta name="viewport" content="width=device-width,initial-scale=1,shrink-to-fit=no">
	<meta name="theme-color" content="#000000">
	<link rel="manifest" href="https://website.didiglobal.com/manifest.json">
	<link rel="shortcut icon" href="https://website.didiglobal.com/DDlogo.ico">
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
	<meta name="viewport" content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no">
	<meta http-equiv="Content-Security-Policy" content="default-src 'self' https://common.diditaxi.com.cn https://view.officeapps.live.com ">
	<meta http-equiv="pragma" content="no-cache">
	<meta http-equiv="Cache-Control:no-cache" content="max-age=0">
	<meta http-equiv="expires" content="0">
	<meta name="apple-mobile-web-app-capable" content="yes"> //从桌面icon启动IOS Safari是否进入全屏状态（APP模式）
	<meta name="renderer" content="webkit">  //双核浏览的渲染方式设定
	<meta name="HandheldFriendly" content="true">  // 手持设备优化
	<meta name="screen-orientation" content="portrait"> //uc强制竖屏
	<meta name="x5-orientation" content="portrait"> //QQ强制竖屏
	<meta name="full-screen" content="yes"> // 强制全屏
	<meta name="x5-fullscreen" content="true"> //QQ强制全屏
	<meta name="browsermode" content="application"> //浏览模式
	<meta name="x5-page-mode" content="app">  //QQ应用模式
	<meta name="msapplication-tap-highlight" content="no"> //移动端winphone系统a、input标签被点击时产生的半透明灰色背景是否去掉，点击无高光
	<meta name="format-detection" content="telephone=no"> //指定是否将网页内容中的手机号码显示为拨号的超链接。
	<meta name="apple-touch-fullscreen" content="yes"> // apple 触摸进入，是否进入全屏
	<title>首页-滴滴官网</title>
	<meta name="description" content="滴滴出行，滴滴打车，滴滴打车官网 ">
	<meta name="Keywords" ontent="滴滴出行,滴滴打车,滴滴打车官网,滴滴打车官方网站 ">

## 字节跳动 ##
	<meta charSet="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no" />
	<meta name="applicable-device" content="pc,mobile" /> //应用设备
	<meta name="robots" content="index, follow" /> //搜索引擎抓取
	<meta name="google" content="notranslate" /> //谷歌翻译
	<meta name="format-detection" content="telephone=no" /> //指定是否将网页内容中的手机号码显示为拨号的超链接。

## 淘宝主页 ##
	<meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
    <meta name="renderer" content="webkit" />
    <title>淘宝网 - 淘！我喜欢</title>
    <meta name="spm-id" content="a21bo" />
    <meta name="description"
        content="淘宝网 - 亚洲较大的网上交易平台，提供各类服饰、美容、家居、数码、话费/点卡充值… 数亿优质商品，同时提供担保交易(先收货后付款)等安全交易保障服务，并由商家提供退货承诺、破损补寄等消费者保障服务，让你安心享受网上购物乐趣！" />
    <meta name="aplus-xplug" content="NONE">
    <meta name="keyword"
        content="淘宝,掏宝,网上购物,C2C,在线交易,交易市场,网上交易,交易市场,网上买,网上卖,购物网站,团购,网上贸易,安全购物,电子商务,放心买,供应,买卖信息,网店,一口价,拍卖,网上开店,网络购物,打折,免费开店,网购,频道,店铺" />

## 京东官网 ##
	<meta charset="utf8" version='1'/>
    <title>京东(JD.COM)-正品低价、品质保障、配送及时、轻松购物！</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes"/>
    <meta name="description"
          content="京东JD.COM-专业的综合网上购物商城,销售家电、数码通讯、电脑、家居百货、服装服饰、母婴、图书、食品等数万个品牌优质商品.便捷、诚信的服务，为您提供愉悦的网上购物体验!"/>
    <meta name="Keywords" content="网上购物,网上商城,手机,笔记本,电脑,MP3,CD,VCD,DV,相机,数码,配件,手表,存储卡,京东"/>

## 华为官网 ##
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <meta http-equiv="Content-Language" content="zh-cn" />
    <title>【华为商城超级618】</title>
    <meta name="keywords" content="华为商城、618、华为商城618、华为618、荣耀618、Vmall、 华为、荣耀、5G、5G手机、华为5G、荣耀5G、华为5G手机、荣耀5G手机、折叠屏、华为MateXs、华为Mate30、华为Mate30 Pro、华为P40、华为P40 Pro、畅享Z、n华为nova 7、华为nova 7Pro、华为P30、华为P30 Pro、华为 Mate 20、华为P20、华为 Mate10、华为保时捷、HUAWEI Mate RS 保时捷设计、华为nova 5、华为nova 5Pro、华为nova 5i、nova 5iPro、nova 5Z、华为nova 4、华为nova 4e、华为畅享 10Plus、华为畅享 10、华为畅享 10S、华为畅享 9、华为畅享 9e、华为畅享 9s、华为畅享9 Plus、华为畅享MAX、华为麦芒8、华为笔记本、华为平板、华为智慧屏、华为手表、华为手环、华为穿戴、华为体脂秤、华为官网、华为、华为手机、华为手机官网、华为商城官网、华为商城官方、荣耀V30、荣耀V30PRO、荣耀20、荣耀20、荣耀20PRO、荣耀9X、荣耀9X PRO、荣耀V20、荣耀20青春、荣耀20S、荣耀20i、荣耀Magic2、荣耀Play3、荣耀10青春、荣耀NOTE 10、荣耀8X、荣耀智慧屏、荣耀MagicBook、智慧屏、荣耀笔记本、荣耀商城、荣耀官网、荣耀商城、荣耀手机、荣耀手环、荣耀手表" />
    <meta name="description" content="HUAWEI 华为商城是华为公司旗下自营电商平台，提供华为5G手机(华为P40系列、Mate30系列、荣耀30系列、荣耀V30系列、荣耀30S等)、华为笔记本、华为平板、华为穿戴、华为智慧屏、华为配件、华为智能家居等全场景智慧生活产品和服务" />
    <meta name="mobile-agent" content="format=xhtml;url=http://m.vmall.com/"> //移动端代理

## 微软官网 ##
	<meta charset="UTF-8" />

    <meta http-equiv="x-ua-compatible" content="ie=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Microsoft - Official Home Page</title>
    
    <meta name="twitter:url" content="https://www.microsoft.com/zh-cn" />
    <meta property="og:url" content="https://www.microsoft.com/zh-cn" />
    <meta name="twitter:title" content="Microsoft - Official Home Page" />
    <meta property="og:title" content="Microsoft - Official Home Page" />
    <meta name="twitter:description" content="At Microsoft our mission and values are to help people and businesses throughout the world realize their full potential." />
    <meta property="og:description" content="At Microsoft our mission and values are to help people and businesses throughout the world realize their full potential." />
    <meta name="twitter:card" content="summary" />
    <meta property="og:type" content="website" />

## 总结 ##
	<meta> 有2个属性 http-equiv 和 name
### http-equiv ###
	1. Content-Type 设定网页字符集，说明网页制作所用语言和文字，浏览器会据此调用。
		<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />   //旧的HTML，不推荐
		<meta charset="UTF-8" >   //HTML5设定网页字符集的方式

	2. X-UA-Compatible 告知浏览器以何种方式渲染当前页面
		<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />   //优先使用IE最新版本和Chrome

	3. pragma Cache-Control expires 各种http强缓存方式，优先级p>c>e
		<meta http-equiv="Pragma" content="no-cache" />
		<meta http-equiv="Cache-Control:no-cache" content="max-age=0"> //不缓存
		<meta http-equiv="Cache-Control" content="max-age=7200"> // 7200s后缓存内容失效
		<meta http-equiv="expires" contect="Mon,12 May 2001 00:20:00 GMT"> //网页到期时间，GMT格式，过期后必须到服务器上重新调用 
		<meta http-equiv="Pragma" contect="no-cache"> //禁止浏览器从本地缓存中调取信息，一旦离开页面就无法从Cache中再调用
	
	4. refresh 让网页在一定时间内刷新，或者一定时间后跳转到其他页面
		<meta http-equiv="refresh" content="30" >   //30s后刷新自己
		<meta http-equiv="Refresh" contect="n;url=http://yourlink">定时让网页在指定的时间n内，跳转到页面http://yourlink；

	5. Cache-Control 避免百度等浏览器打开网页时可能对其进行转码，比如 贴广告等
		<meta http-equiv="Cache-Control" content="no-siteapp" />   //先发送请求，与服务器确认该资源是否被更改，未被更改则使用缓存

	6. Content-Security-Policy 内容安全策略，指定浏览器智能加载content中的js代码，其他所有均拒绝
		<meta http-equiv="Content-Security-Policy" content="default-src https://cdn.example.net; child-src 'none'; object-src 'none'">

		base-uri: 用于限制可在页面的 <base> 元素中显示的网址。
		child-src: 用于列出适用于工作线程和嵌入的帧内容的网址。例如：child-src https://youtube.com 将启用来自 YouTube（而非其他来源）的嵌入视频。 使用此指令替代已弃用的 frame-src 指令。
		connect-src: 用于限制可（通过 XHR、WebSockets 和 EventSource）连接的来源。
		font-src: 用于指定可提供网页字体的来源。Google 的网页字体可通过 font-src https://themes.googleusercontent.com 启用。
		form-action: 用于列出可从 <form> 标记提交的有效端点。
		frame-ancestors: 用于指定可嵌入当前页面的来源。此指令适用于 <frame>、<iframe>、<embed> 和 <applet> 标记。此指令不能在 <meta> 标记中使用，并仅适用于非 HTML 资源。
		frame-src: 已弃用。请改用 child-src。
		img-src: 用于定义可从中加载图像的来源。
		media-src: 用于限制允许传输视频和音频的来源。
		object-src: 可对 Flash 和其他插件进行控制。 
		plugin-types: 用于限制页面可以调用的插件种类。

		指定一个 default-src 指令替换大部分指令的默认行为:
		<meta http-equiv="Content-Security-Policy"
                content="default-src 'self' https://common.diditaxi.com.cn https://view.officeapps.live.com ">
        其他指令服从default-scr的规则，还有4个关键字：
		none 表示不执行任何匹配。
		self'表示与当前来源（而不是其子域）匹配。
		unsafe-inline表示允许使用内联 JavaScript 和 CSS。
		unsafe-eval 表示允许使用类似 eval 的 text-to-JavaScript 机制。 

	7. date 原始服务器消息发出的时间
		<meta http-equiv="date" content="Wed, 16 Feb 2011 22:34:13 GMT">

	8. location 用来重定向接收方到非请求URL的位置来完成请求或标识新的资源
		<meta http-equiv="location" content="URL=http://www.runoob.com">

### name ###
	1. keywords 告诉搜索引擎网页关键字
		<meta name="Keywords" ontent="滴滴出行,滴滴打车,滴滴打车官网,滴滴打车官方网站 ">

	2. description 网站的描述，告诉搜索引擎网站的主要内容
		<meta name="description" content="滴滴出行，滴滴打车，滴滴打车官网 ">
	
	3. author 标注作者
	
	4. viewport 用于移动端显示页面，将网页宽度设置为视口宽度，设置缩放比例，是否允许用户缩放等。
		<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no"> //用户不能缩放
		<meta name="viewport" content="width=device-width, initial-scale=1 shrink-to-fit=no"> //网页宽度自适应手机屏幕宽度
		但在iOS9中要想起作用，得加上"shrink-to-fit=no"

	5. renderer:双核浏览器的渲染方式，用于指定双核浏览器默认以何种方式渲染页面
		<meta name="renderer" content="webkit/ie-comp/ie-stand" /> //默认webkit内核/默认IE兼容模式/默认IE标准模式

	6. referrer 引用页信息 4个参数：
		never：删除http head中的referer；
		default：如果当前页面使用的是https协议，而正要加载资源使用的是普通的http协议，则将http header中额referer置为空；
		origin：只发送origin部分；
		always：不改变http header中的referer的值；
		
		百度首页的 <meta content="always" name="referrer"> A页面值为always的时候，B页面能取得他是从哪个页面来的。

	7. theme-color 浏览器地址栏变色
		百度首页 <meta name="theme-color" content="#2932e1">

	8. Generator
		<meta name="Generator" contect="">用以说明生成工具（如Microsoft FrontPage 4.0）等；
	
	9. <meta name="Robots" contect= "all|none|index|noindex|follow|nofollow">
		all：文件将被检索，且页面上的链接可以被查询； 
		none：文件将不被检索，且页面上的链接不可以被查询； 
		index：文件将被检索； 
		follow：页面上的链接可以被查询； 
		noindex：文件将不被检索，但页面上的链接可以被查询； 
		nofollow：文件将不被检索，页面上的链接可以被查询。

	10. revisit-after (重访)  通知浏览器多少天访问一次
		<meta name="revisit-after" CONTENT="7 days" > 

	11. coperight 版权
		<meta name="coprright" content="版权"> 
### name 的分类汇总 ###
	1. <!-- SEO -->
		<meta name="keywords" content="your, tags"/>
		<meta name="description" content="150 words"/>
		<meta name="subject" content="your website's subject">
		<meta name="copyright"content="company name">
		 
		<meta name="language" content="ES">
		<meta name="robots" content="index,follow" />
		<meta name="revised" content="Sunday, July 18th, 2010, 5:15 pm" />
		<meta name="abstract" content="">
		<meta name="topic" content="">
		<meta name="summary" content="">
		<meta name="Classification" content="Business">
		<meta name="author" content="name, email@hotmail.com">
		<meta name="designer" content="">
		<meta name="copyright" content="">
		<meta name="reply-to" content="email@hotmail.com">
		<meta name="owner" content="">
		<meta name="url" content="http://www.websiteaddrress.com">
		<meta name="identifier-URL" content="http://www.websiteaddress.com">
		<meta name="directory" content="submission">
		<meta name="category" content="">
		<meta name="coverage" content="Worldwide">
		<meta name="distribution" content="Global">
		<meta name="rating" content="General">
		<meta name="revisit-after" content="7 days">
		 
		<meta http-equiv="Expires" content="0">
		<meta http-equiv="Pragma" content="no-cache">
		<meta http-equiv="Cache-Control" content="no-cache">

	2. 为提高传播效率，通过Open Graph(开放图景协议)把其他社交网站建构的网络给连接起来
		<meta name="og:title" content="The Rock"/>
		<meta name="og:type" content="movie"/>
		<meta name="og:url" content="http://www.imdb.com/title/tt0117500/"/>
		<meta name="og:image" content="http://ia.media-imdb.com/rock.jpg"/>
		<meta name="og:site_name" content="IMDb"/>
		<meta name="og:description" content="A group of U.S. Marines, under command of..."/>
		 
		<meta name="fb:page_id" content="43929265776" />
		 
		<meta name="og:email" content="me@example.com"/>
		<meta name="og:phone_number" content="650-123-4567"/>
		<meta name="og:fax_number" content="+1-415-123-4567"/>
		 
		<meta name="og:latitude" content="37.416343"/>
		<meta name="og:longitude" content="-122.153013"/>
		<meta name="og:street-address" content="1601 S California Ave"/>
		<meta name="og:locality" content="Palo Alto"/>
		<meta name="og:region" content="CA"/>
		<meta name="og:postal-code" content="94304"/>
		<meta name="og:country-name" content="USA"/>
		 
		<meta property="og:type" content="game.achievement"/>
		<meta property="og:points" content="POINTS_FOR_ACHIEVEMENT"/>
		 
		<meta property="og:video" content="http://example.com/awesome.swf" />
		<meta property="og:video:height" content="640" />
		<meta property="og:video:width" content="385" />
		<meta property="og:video:type" content="application/x-shockwave-flash" />
		<meta property="og:video" content="http://example.com/html5.mp4" />
		<meta property="og:video:type" content="video/mp4" />
		<meta property="og:video" content="http://example.com/fallback.vid" />
		<meta property="og:video:type" content="text/html" />
		 
		<meta property="og:audio" content="http://example.com/amazing.mp3" />
		<meta property="og:audio:title" content="Amazing Song" />
		<meta property="og:audio:artist" content="Amazing Band" />
		<meta property="og:audio:album" content="Amazing Album" />
		<meta property="og:audio:type" content="application/mp3" />

	3. 公司/服务 标签
		<meta name="microid" content="mailto+http:sha1:e6058ed7fca4a1921cq91d7f1f3b8736cd3cc1g7" />

		APPLE META TAGS::
		<!-- 从桌面icon启动IOS Safari是否进入全屏状态（APP模式） -->
		<meta name="apple-mobile-web-app-capable" content="yes">
		 
		<!-- 添加到主屏幕“后，全屏显示 -->
		<meta name="apple-touch-fullscreen" content="yes" >
		 
		<!-- 指定状态栏的颜色 -->
		<meta name="apple-mobile-web-app-status-bar-style" content="black">
		 
		<!-- ios设备上禁止将数字识别为可点击的telephone link -->
		<meta name="format-detection" content="telephone=no">
		 
		<!-- 页面CSS计算时使用宽度为320，初始缩放比例2.3， 不允许用户缩放, 最大缩放因子为1 -->
		<meta name="viewport" content="width = 320, initial-scale = 2.3, user-scalable = no, maximum-scale=1 ">
		 
		<!-- 页面CSS计算时使用的宽度根据设备给定值自适应 -->
		<meta name= "viewport" content = "width = device-width">

		INTERNET EXPLORER META TAGS 网络扩展元标记标签：
		<meta http-equiv="Page-Enter" content="RevealTrans(Duration=2.0,Transition=2)" />
		<meta http-equiv="Page-Exit" content="RevealTrans(Duration=3.0,Transition=12)" />
		<meta name="mssmarttagspreventparsing" content="true">
		 
		<!-- 告诉IE浏览器以什么模式展示网页 -->
		<meta http-equiv="X-UA-Compatible" content="chrome=1">
		 
		<meta name="msapplication-starturl" content="http://blog.reybango.com/about/"/>
		<meta name="msapplication-window" content="width=800;height=600"/>
		<meta name="msapplication-navbutton-color" content="red"/>
		<meta name="application-name" content="Rey Bango Front-end Developer"/>
		<meta name="msapplication-tooltip" content="Launch Rey Bango's Blog"/>
		<meta name="msapplication-task" content="name=About;action-uri=/about/;icon-uri=/images/about.ico" />
		<meta name="msapplication-task" content="name=The Big List;action-uri=/the-big-list-of-javascript-css-and-html-development-tools-libraries-projects-and-books/;icon-uri=/images/list_links.ico" />
		<meta name="msapplication-task" content="name=jQuery Posts;action-uri=/category/jquery/;icon-uri=/images/jquery.ico" />
		<meta name="msapplication-task" content="name=Start Developing;action-uri=/category/javascript/;icon-uri=/images/script.ico" />
		 
		<!-- Tab标签icon -->
		<link rel="shortcut icon" href="/images/favicon.ico" />
		
### 移动端头部标签 ### 
	<meta name=”description” content=”不超过150个字符”/>       页面描述
	
	<meta name=”keywords” content=””/>      页面关键词
	
	<meta name=”author” content=”name, email@gmail.com”/>    网页作者
	
	<meta name=”robots” content=”index,follow”/>      搜索引擎抓取
	
	<meta name=”viewport” content=”initial-scale=1, maximum-scale=3, minimum-scale=1, user-scalable=no”> 为移动设备添加 viewport
	
	<meta name=”apple-mobile-web-app-title” content=”标题”> iOS 设备 begin
	
	<meta name=”apple-mobile-web-app-capable” content=”yes”/>  添加到主屏后的标题（iOS 6 新增） 是否启用 WebApp 全屏模式，删除苹果默认的工具栏和菜单栏
	
	<meta name=”apple-itunes-app” content=”app-id=myAppStoreID, affiliate-data=myAffiliateData, app-argument=myURL”>
	添加智能 App 广告条 Smart App Banner（iOS 6+ Safari）
	
	<meta name=”apple-mobile-web-app-status-bar-style” content=”black”/> 设置苹果工具栏颜色
	
	<meta name=”format-detection” content=”telphone=no, email=no”/> 禁止将网页上的数字变为 telphone 及 email 的link
	
	<meta name=”renderer” content=”webkit”>  启用360浏览器的极速模式(webkit)
	
	<meta http-equiv=”X-UA-Compatible” content=”IE=edge”>     避免IE使用兼容模式
	
	<meta http-equiv=”Cache-Control” content=”no-siteapp” />    不让百度转码
	
	<meta name=”HandheldFriendly” content=”true”>    针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓
	
	<meta name=”MobileOptimized” content=”320″>   微软的老式浏览器
	
	<meta name=”screen-orientation” content=”portrait”>   uc强制竖屏
	
	<meta name=”x5-orientation” content=”portrait”>    QQ强制竖屏
	
	<meta name=”full-screen” content=”yes”>              UC强制全屏
	
	<meta name=”x5-fullscreen” content=”true”>       QQ强制全屏
	
	<meta name=”browsermode” content=”application”>   UC应用模式
	
	<meta name=”x5-page-mode” content=”app”>    QQ应用模式
	
	<meta name=”msapplication-tap-highlight” content=”no”>    windows phone 点击无高光