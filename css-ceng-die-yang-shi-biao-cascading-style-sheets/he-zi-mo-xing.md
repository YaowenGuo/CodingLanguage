#### 标签分类

元素分类
在讲解CSS布局之前，我们需要提前知道一些知识，在CSS中，html中的标签元素大体被分为三种不同的类型：块状元素、内联元素(又叫行内元素)和内联块状元素。

常用的块状元素有：
```html
<div>、<p>、<h1>...<h6>、<ol>、<ul>、<dl>、<li>、<table>、<address>、<blockquote> 、<form>
```
常用的内联元素有：
```html
<a>、<span>、<br>、<i>、<em>、<strong>、<label>、<q>、<var>、<cite>、<code>
```
常用的内联块状元素有：
```html
<img>、<input>
```


#### 块级元素

块级元素特点：

1. 每个块级元素都从新的一行开始，并且其后的元素也另起一行。（真霸道，一个块级元素独占一行）
2. 元素的高度、宽度、行高以及顶和底边距都可设置。
3. 元素宽度在不设置的情况下，是它本身父容器的100%（和父元素的宽度一致），除非设定一个宽度。



display:inline

inline:内联元素{

1，不能设置width和height；

2，多个行内元素排成一行，直到一行排不下，才会换新一行；

3，只可以设置水平方向的边距，如：margin-left,margin-right,padding-left,padding-right.

}

block:块级元素{

1，块级元素独占一行；

2，可以设置width和height，默认宽度为一整行，除非单独设置宽度；

3，可以设置margin和padding属性。

}

inline-block{

简而言之就是让元素既可以在一行内显示，又可以设置宽高边距等。

}








