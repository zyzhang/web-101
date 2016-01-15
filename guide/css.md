# CSS - Cascading Style Sheets

## 什么是CSS？

* 层叠样式表 (Cascading Style Sheets)。

> HTML 标签原本被设计为用于定义文档内容。通过使用 `<h1>` `<p>` 这样的标签，HTML 的初衷是表达“这是标题”、“这是段落”之类的信息。同时文档布局由浏览器来完成，而不使用任何的格式化标签。

> 由于两种主要的浏览器（Netscape 和 Internet Explorer）不断地将新的 HTML 标签和属性（比如字体标签和颜色属性）添加到 HTML 规范中，创建文档内容清晰地独立于文档表现层的站点变得越来越困难。	

> 为了解决这个问题，万维网联盟（W3C），这个非营利的标准化联盟，肩负起了 HTML 标准化的使命，并在 HTML 4.0 之外创造出样式（Style）。	

HTML负责文档内容和结构，CSS负责表现。

#### 一个简单的例子

	<html>
	<head>
		<title>Basic HTML</title>
		<meta charset="UTF-8">
	</head>
	<body>

	<!-- Headings -->
	<h1>My First Heading 1</h1>
	<h2>My First Heading 2</h2>
	<h3>My First Heading 3</h3>

	<!-- Paragraphs -->
	<p>My first paragraph.</p>

	<p>
		<!-- Unordered list -->
		Good Tutorial:
		<ul>
			<li><a href="http://www.w3school.com.cn">W3School (Chinese)</a></li>
			<li><a href="http://www.w3schools.com/html/default.asp">W3School (English)</a></li>
		</ul>
	</p>

	</body>
	</html>

打开[链接](./samples/basic.html)查看效果。

要点：
* 标签
* 注释
* 文档结构
* 标签嵌套
* 属性（Attribute）

## Tips

#### HTML字符集

字符集简介：
* ASCII
* ISO-8859-1 （HTML默认编码）
* UTF-8
* GBK

声明字符集：

	For HTML4:
	<meta http-equiv="Content-Type" content="text/html;charset=ISO-8859-1">

	For HTML5:
	<meta charset="UTF-8">

需转义的特殊字符：

	'<' -> &lt;
	'>' -> &gt;

#### 浏览器解释HTML文档时会忽略空白符

* 换行
* 空格

换行可以用<br>，标签间空格可以通过转义字符 `&nbsp;`, 但不建议使用。一般通过CSS样式控制.

## 练习

* 自己编写一个HTML文件，在浏览器中查看效果。尝试[[W3C School - Tags](http://www.w3school.com.cn/tags/index.asp)中的标签，例如：a，p，div，img，input，ul，ol。
* tmux-intro：编写html页面，展现下图内容

![tmux](./html-exercise1/html-exercise1.png)


## References

* [W3C School - 英文](http://www.w3schools.com/)
* [W3C School - 中文](http://www.w3school.com.cn)