# Javascript

## Javascript简介

#### 历史

From [Wikipedia](https://zh.wikipedia.org/zh-cn/JavaScript):

> 在1995年时，由网景公司的布兰登·艾克，在网景导航者浏览器上首次设计实现而成。因为网景公司与昇阳公司的营销合作，加上网景公司管理层希望它外观看起来像Java，因此取名为JavaScript。但实际上它的语义与Self及Scheme较为接近[4]。

> 为了获取技术优势，微软推出了JScript，与JavaScript同样可在浏览器上运行。为了统一规格，1997年，在ECMA（欧洲计算机制造商协会）的协调下，由网景、昇阳、微软和Borland公司组成的工作组确定统一标准：ECMA-262。因为JavaScript兼容于ECMA标准，因此也称为ECMAScript.


#### 什么是Javascript

* 解释性脚本语言
* 动态类型
* 基于原型(prototype)
* 解释器被称为JavaScript引擎，浏览器内置
* 几乎所有的浏览器均支持

#### Javascript在浏览器端的常见用途：

* 嵌入动态文本于HTML页面
* 对浏览器事件作出响应
* 读写HTML元素
* 在数据被提交到服务器之前验证数据
* 检测访客的浏览器信息
* 控制cookies，包括创建和修改等

#### Javascript的实现

* ECMAScript，描述了该语言的语法和基本对象
* 文档对象模型（DOM），描述处理网页内容的方法和接口
* 浏览器对象模型（BOM），描述与浏览器进行交互的方法和接口

## Hello World

	<html>
		<head>
			<script type="text/javascript">
			alert("Hello World");
			</script>
		</head>
	<body></body>
	</html>

## 基本语法

* 变量声明
* 数据类型
* 表达式 & 运算符
* 控制流程

#### 变量声明

	var s = "Hello World";
	console.log(s);

#### 数据类型

* 字符串 - String, 单引号和双引号均可
* 数字 - Number（不细分int, float, double等）
* 布尔 - Boolean
* 数组 - Array
* 对象 - Object
* Null
* Undefined

	// String
	var s1 = “Hello”;
	var s2 = new String(“World");

	// Number
	var n1 = 100;
	var n2 = 100.01
	var n3 = -100;

	// Boolean
	var b1 = true;
	var b2 = false;

	// 数组
	var arr1 = [];
	var arr2 = [1, 2];
	var arr3 = [1, "hello"];

	// 对象
	var obj1 = {
		name: "Zhenyu",
		age: 18,
		children: [
			{name: "Dudu", age: 2}
		],
		sayHello: function(){console.log("Hello")}
	} 
	console.log(obj.name);
	console.log(obj['name']);
	obj.sayHello();

	var obj2 = new Object();
	obj2.name = "Zhenyu";

	// Null, undefined
	var a = null;
	var b;

#### 表达式 & 运算符

	var a = 1;
	var b = 2;
	var sum = a + b;

	var e = a == b;
	var less = 1 < 2;

	var s = "hello " + "world!";

详细内容参见[文档](http://www.w3school.com.cn/js/js_operators.asp)

#### 控制流程 - if

	var s = "Zhenyu";
	if(s == "Zhenyu") {
		console.log("Hansome!!");
	} else if (s == "Zhiyong") {
		console.log("WoW....");
	} else {
		console.log("Who are you?");
	}

#### 控制流程 - Loop

	var i = 0;
	while(i<10) {
		console.log(i);
		i++;
	}

	var arr = [1, 2, 3, 5, 8];
	for (var i=0; i<arr.length; i++) {
		console.log(arr[i]);
	}

循环中还涉及到`continue`和`break`, 请自行查阅。

## 练习

#### 计算字符串中字母`a`的个数

	'Leonardo Pisano ,Fibonacci, Leonardo Bigollo'

控制台计算结果应为4.

字符串具有哪些方法请参见[Reference](http://www.w3school.com.cn/jsref/jsref_obj_string.asp).

## Javascript 函数

语法：

	function add (a, b) {
		return a + b;
	}

	var add = function(a, b) {
		return a + b;
	}

	var add = new Function("a", "b", "return a+b");
	
	// 调用函数
	var result = add(1, 2);
	console.log(result);

#### 函数练习1

编写一个函数输出斐波那契数列，参数是一个数字，代表数列中元素个数，输出结果为一个数组，例如：
* 输入参数为`5`
* 输出为`[1, 2, 3, 5, 8]`

#### Higher-order Functions / First-class Functions

	function compare(a, b) {
		return a-b;
	}

	var arr = [9, 4, 2, 3];

	console.log(arr);
	arr.sort(compare);
	console.log(arr);

	// Return function
	var count = (function () {
    	var counter = 0;
    	return function () {return counter += 1;}
	})();

	console.log(count());
	console.log(count());
	console.log(count());

延伸阅读：
* [Functional Programming](https://en.wikipedia.org/wiki/Functional_programming)
* [First-class Function](https://en.wikipedia.org/wiki/First-class_function)
* [Higher-order Function](https://en.wikipedia.org/wiki/Higher-order_function)

#### 函数练习2

实现`map`函数：

	map(arr, transformer)

例如：

	var result = map([1, 2, 3], function(item) {
		return item*item;
	});
	console.log(result); // print [1, 4, 9];

## Prototype

	function Employee(name, birth) {
		this.name = name;
		this.birth = birth;
	}
	Employee.prototype.age = function(){
		var now = new Date();
		return now.getFullYear() - this.birth.getFullYear();
	};

	var zhenyu = new Employee('Zhenyu', new Date(1983, 2, 15));
	console.log(zhenyu.age());

## 一些Trick

#### `0`, `''`, `undefined`, `null` 会被当做false处理

	var a = ''; 
	if (a) {
		console.log("true...");
	} else {
		console.log("false...");
	}

#### 函数默认返回值为`undefined`

#### `&&`和`||`的特别用法

	var s1 = '';
	var s2 = "Hello";
	var s3 = "World";
	console.log(s1 || s2 || s3);
	console.log(s1 && s2 && s3);
	console.log(s2 && s3);

## BOM (Browser Object Model)

	window.location
	window.close()
	window.innerHeight
	window.history.back()
	window.navigator.userAgent

## DOM (Document Object Model)

![](./images/pic_htmltree.gif)

#### HTML DOM 编程接口

* 所有HTML元素(element)都被定义为对象
* 每一个对象都有property和method

#### 示例

	<html>
	<body>

	<p id="demo"></p>

	<script>
	document.getElementById("demo").innerHTML = "Hello World!";
	</script>

	</body>
	</html>

#### Reference

[DOM Document](http://www.w3schools.com/js/js_htmldom_document.asp)

获取元素：
* document.getElementById(id)
* document.getElementsByTagName(name)
* document.getElementsByClassName(name)
* document.querySelectorAll(selector)

修改元素：
* element.innerHTML =  new html content
* element.attribute = new value	

添加/删除元素：
* document.createElement(element)
* document.removeChild(element)
* document.appendChild(element)
* document.replaceChild(element)
* document.write(text)

## 事件（Events）

#### 以click事件为例：

定义在标签中：

	<button onclick="alert('You did that!')">Click Me</button>

Javascript定义：

	<script>
	var btn = document.getElementById("myBtn");
	btn.onclick = function(){
		alert(1);
	};

	btn.addEventListener("click", function(e){
		alert(1);
	});
	</script>

#### [事件列表](http://www.w3schools.com/jsref/dom_obj_event.asp)

#### `onload`事件

示例`samples/js-basic.html`：

* `onload`事件
* 匿名立即执行函数
* getElementById
* event listener

## DOM & Event 练习

