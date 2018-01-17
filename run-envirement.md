#### Java Script

作为轻量级的解释语言，js的运行场景并不多，但是却很广泛。任何流行的浏览器都带有js的解释器。为了运行js代码，

1，可以将js嵌入到网页中，并将其写入到&lt;script&gt;&lt;/script&gt;标签中。

```html
<!DOCTYPE html>
<html>
<head>
	<title>js测试</title>
</head>
<body>
	<pre><script type="text/javascript" > document.writeln('Hello Word!');</script></pre>

</body>
</html>
```

pre 元素可定义预格式化的文本。被包围在 pre 元素中的文本通常会保留空格和换行符。而文本也会呈现为等宽字体。

&lt;pre&gt; 标签的一个常见应用就是用来表示计算机的源代码。

2，有时候js很长，你并不想要将js直接写在一个html中，况且为了能够重用js代码，也应该讲js独立出来，这时候可以新建一个文件，将嵌入改成引入的形式

```html
<pre><script type="text/javascript" src="js的文件名.js"/></pre>

```

3，有时候你并不是想要保留代码，只是想要测试一个特性，那么你可以直接在浏览器的终端中运行。

开发者选项 -&gt; Console 直接输入代码就可以运行。如 a = 5;





