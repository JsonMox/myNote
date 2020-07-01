# 2020-06-26 题目来源：http://www.h-camel.com/index.html #

# [html] 如何给页面添加追加右键菜单（原右键菜单功能保持不变） #
	js + css 实现页面右键菜单 https://www.cnblogs.com/elleniou/archive/2013/05/15/3079018.html
	
	// 禁用整个页面的所有浏览器默认右击事件
    document.oncontextmenu = function(){
        return false;
    }
    // 点击此div出现右键菜单
    let contextMenu = document.getElementsByClassName('app-tabs-main')[0]
    // 点击出现的菜单div
    let divCon = document.getElementsByClassName('context-menu-tab')[0];
    // 给div绑定右击事件
    contextMenu.addEventListener('contextmenu', function (event) {
        // 设置右键菜单显示
        divCon.style.display = 'block'
        // 设置右键菜单的展示位置
        divCon.style.left = event.clientX + 'px'
        divCon.style.top = event.clientY + 'px'
        // 添加页面的监听事件 - 点击页面任意一处菜单隐藏
        document.addEventListener('click', removeClickFun)
        // 隐藏掉右键菜单
        function removeClickFun () {
            // 隐藏菜单
            divCon.style.display = 'none';
            // 取消页面的监听
            document.removeEventListener('click', removeClickFun)
        }
    })

# [css] 为什么float会导致父元素塌陷？ #
	浮动元素会脱离当前的文档流，不占据空间，float会改变display的计算值，产生包裹性。但父级元素还存在于文档流中，
	如果没有浮动清除或父级没有高度值设定，就会导致父级元素的高度塌陷，不能够被浮动元素撑开，影响父级元素的同级元素。
	
	清除浮动：clear:both; //父级元素后，添加空标签
	给父元素高度：height(不是很可取)
	给父元素：display：inline-black；（问题：margin：auto失效）
	给父元素：overflow:hidden;( 在IE67需要有宽度); 
	给父元素添加伪类;:after{content：""; display:block；clear：both;} (万能)

# [js] 微信小程序实现轨迹回放，微信原生小程序，基于uniapp的小程序？ #
	使用组件map和API的MapContext+wx.getLocation来实现活动轨迹回放 https://blog.csdn.net/king0964/article/details/105413712

	https://blog.csdn.net/weixin_30920597/article/details/96404453

# [软技能] TCP为什么是有状态的？ #
	无状态： 协议对于事务处理没有记忆能力，服务器不知道客户端是什么状态。 我们给服务器发送http请求后，服务器会根据请求进行返回数据，返回之后，不会记录信息。
	1. http的无状态
		http是一个无状态协议，每个请求都是独立的。优点在于解放了服务器，每次请求不会造成不必要的连接占用；缺点是，每次连接传送数据量大。

	2. 摘自<<tcp/ip 协议族>>(第二版)第274页:
		由于需要清楚地掌握在连接建立,连接终止以及数据传送时,所发生的所有不同事件,TCP软件是以有限自动机的形式来实现的.
		有限状态机是能够经历有限数目状态的一种机器.在任何时候,这个机器处于某一个状态.
		若没有其它事件发生,这个机器就一直出于那个状态.事件可以使机器转入到一个新的状态,或者事件完成同样的动作.
		换言之,事件是加到状态上的输入.它可以改变这个状态并产生输出.