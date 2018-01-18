#### 标签分类

元素分类
在讲解CSS布局之前，我们需要提前知道一些知识，在CSS中，html中的标签元素大体被分为三种不同的类型：块状元素、内联元素(又叫行内元素)和内联块状元素。

常用的块状元素有：

<div>、<p>、<h1>...<h6>、<ol>、<ul>、<dl>、<table>、<address>、<blockquote> 、<form>

常用的内联元素有：

<a>、<span>、<br>、<i>、<em>、<strong>、<label>、<q>、<var>、<cite>、<code>

常用的内联块状元素有：

<img>、<input>


我们可以将JavaScript代码放在html文件中任何位置，但是我们一般放在网页的head或者body部分。
放在<head>部分
最常用的方式是在页面中head部分放置<script>元素，浏览器解析head部分就会执行这个代码，然后才解析页面的其余部分。
放在<body>部分
JavaScript代码在网页读取到该语句的时候就会执行。


网站性能优化-将Script放到HTML文件中尽量靠近尾部（将Script放在页面底部）

注意：Button的Click事件需要调用js文件中的某个函数，如果Script都被放到HTML文件的最后的话，button这个element会在script下载完成之前被render出来，如果此时用户点击了这个button，就一定会出现一个Script error。

解决方法：

1，将Script放在合适的，尽量靠近尾部的地方；

2，为所有的js文件中需要被调用的函数，在HTML中实现一个空函数（放在靠前的位置），这样当页面需要的js文件没有download完成时，用户点击按钮等操作之后出发一个空函数



