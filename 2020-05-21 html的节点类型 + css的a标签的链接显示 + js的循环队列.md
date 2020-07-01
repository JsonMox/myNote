# 2020-05-21 题目来源：http://www.h-camel.com/index.html

# [html] DOM节点的种类有哪些?
	
	元素 nodeType === 1
	节点 nodeType === 3
	属性 nodeType === 2
 
	校验方式：if(someNode.nodeType === 1)...

# [css] 如何使用css显示a链接的url？
	
	<a href='http://www.baidu.com' id='a1'>RPG</a>

  	1.js的获取： var obj = document.getElementById("a1"); var str = obj.getAttribute("href");

	2.css的显示：  利用attr()   a::after{ content: "("attr(href)")"; }
	

# [js] 使用js实现一个循环队列
	 
	基本队列的方法有：
	1）向队尾添加元素（enqueue） 2）从对头删除元素（dequeue） 3）查看队列头部元素（front）
	4）查看队列是否为空（isEmpty） 5）查看队列的长度（size） 6）查看队列（print）
 	一个队列的基本方法：
	function Queue(){
		//使用数组初始化队列
		var items=[];
		//向队列插入元素
		this.enqueue=function(elem){
			items.push(elem);
		}
		//从队头删除元素
		this.dequeue=function(){
			return items.shift();
		}
		//查看对头元素
		this.front=function(){
			return items[0];
		}
		//判断队列是否为空
		this.isEmpty=function(){
			return items.length==0;	
		}
		//查看队列的长度
		this.size=function(){
			return items.length;	
		}
		//查看队列
		this.print=function(){
			return items.toString();	
		}
	}
	//循环队列：每次循环的时候从队列头部弹出一个元素，然后把这个元素添加到队尾，循环n次，循环停止时弹出队列头部的元素被淘汰，直至队列中剩下一个元素。
	function circularQueue(arr,n){
		//实例化一个队列
		var queue=new Queue();
		//将孩子加入到对列中
		for(var i=0;i<arr.length;i++){
			queue.enqueue(arr[i]);
		}
		当队列的长度大于1时执行循环
		while(queue.size()>1){
			//将第n个前面的数依次从对队尾插入
			for(var j=0;j<n-1;j++){
				queue.enqueue(queue.dequeue());	
			}	
			//删除n个数
			queue.dequeue();
		}
		//返回剩余的一个数
		return queue.dequeue();
	}


# [软技能] ...... 
	
 