# 2020-06-04 题目来源：http://www.h-camel.com/index.html

# [html] webp与jpg、png比较，它有什么优劣势？如何选择？
	webp是一种新兴的图片格式，优势体现在它具有更优的图像数据压缩算法，能带来更小的图片体积，而且拥有肉眼识别无差异的图像质量；
	同时具备了无损和有损的压缩模式、Alpha 透明以及动画的特性，在 JPEG 和 PNG 上的转化效果都非常优秀、稳定和统一。
	webp的优点：
	1. 同等质量但是图片更小
	2. 压缩后质量无明显变化
	3. 完美支持无损图像
 
	webp的缺点：
	1. 相比于jpg 编码速度慢10倍，解码速度慢1.5倍，但是由于文件体积的减少，加载速度会变快，渲染速度也变快了。
	2. 支持性上面，目前桌面浏览器chrome和opera浏览器，手机支持原生android和android系统上的chrome浏览器。
	3. 目前不被任何操作系统原生支持。
	
	webp应用：
	1. 浏览器场景
	javascript能力检测，对支持webp的用户输出webp图片
	使用webp支持插件
	2. app场景
	3. 后台场景(Webp的转换)

# [css] 父元素下有子元素，子元素也有高度但父元素的高度为何为0呢？分析下可能出现的原因及解决方法
  	
  	1. 父级无高度，子级自适应(经过测试，这种方式父级还是存在有高度值)
       .container {
           position: relative;
           height: 0;
           padding-top: 20%; /* reason */
           background-color: rosybrown;
           border: 1px solid skyblue;
       }
       .subDiv {
           position: absolute;
           width: 50%;
           height: 100%;
           top: 0;
           background-color: rebeccapurple;
       } 

	 <div class="container">
         <div class="subDiv"></div>
     </div>

	2. 浮动原因 父级div的属性样式不会生效，原因就是子级元素设置为浮动，父级元素并没清除浮动
	  <div style="width:300px;background:#ccc;">
        <div style="width:100px;height:100px;float:left;background:Green;"></div>
        <div style="width:100px;height:100px;float:right;background:Red;"></div>
      </div>

	  https://blog.csdn.net/qq_15096707/article/details/50493998 这里讲的很详细
# [js] 写一个方法，实时验证input输入的值是否满足金额如：3.56(最多只有两位小数且只能数字和小数点)的格式，其它特殊字符禁止输入
	$("#price").on('input  propertychange', function () {
        //如果输入非数字，则替换为''
        this.value = this.value.replace(/[^\d\.]/g, '');
        //必须保证第一个为数字而不是.     
        this.value = this.value.replace(/^\./g, '');
        //保证只有出现一个.而没有多个.     
        this.value = this.value.replace(/\.{2,}/g, '.');
        //保证.只出现一次，而不能出现两次以上     
        this.value = this.value.replace('.', '$#$').replace(/\./g, '').replace('$#$', '.');
        //只能输入两位小数
        this.value = this.value.replace(/^(\-)*(\d+)\.(\d\d).*$/, '$1$2.$3');
   })
 
	这里说的很清楚：https://blog.csdn.net/wl_Honest/article/details/81629026
		

# [软技能] 晋升体系何为
	when u say nothing at all
	虽然存在，但也只是摆着当样子，就和协同工具一样，成事在人。