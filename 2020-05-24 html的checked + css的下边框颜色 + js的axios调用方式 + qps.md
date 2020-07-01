# 2020-05-24 题目来源：http://www.h-camel.com/index.html

# [html] 如何扩大CheckBox点击区域？
	
	:checked伪元素选择器
	
	input:checked{ width: 100px; height:100px; }	
	
	<form action="">
		<input type="radio" checked="checked" value="male" name="gender" /> Male<br>
		<input type="radio" value="female" name="gender" /> Female<br>
		<input type="checkbox" checked="checked" value="Bike" /> I have a bike<br>
		<input type="checkbox" value="Car" /> I have a car
	</form>


# [css] 判断如下边框的颜色，并解释为什么[代码]？
	
	border-bottom: 1px solid red;
	box-shadow: 2px 2px 0px 0px skyblue;

# [js] axios为什么可以使用对象和函数两种方式调用？是如何实现的？

 	<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
	axios
	  .get('http://rap2api.taobao.org/app/mock/23080/resources/search',{
	      params: {
	         id: 5
	      }
	   })
	  .then(res => {
	    console.log('数据是:', res);
	  })
	  .catch((e) => {
	    console.log('获取数据失败');
	  });
	//////////////////////////////////
	axios({
	  url: 'http://rap2api.taobao.org/app/mock/121145/post',
	  method: 'post',
	  data: {
	    name: '小月'
	  }
	}).then(res => {
	  console.log('请求结果：', res);
	});
 
# [软技能] 你有没有关注过qps？qps是多少呢？
	
	每秒查询率（QPS，Queries-per-second）是对一个特定的查询服务器在规定时间内所处理流量多少的衡量标准。
	计算公式：QPS = 并发量 / 平均响应时间。