document.write() 可用于直接向 HTML 输出流写内容。简单的说就是直接在网页中输出内容。

<script type="text/javascript">
  document.write("I love JavaScript！"); //内容用""括起来，""里的内容直接输出。
  var mystr="hello world!";
  document.write(mystr);
  document.write(mystr+"I love JavaScript");
</script>


#### 提示窗口

alert("提示内容");

#### 确认对话框

confirm 消息对话框通常用于允许用户做选择的动作，如：“你对吗？”等。弹出对话框(包括一个确定按钮和一个取消按钮)。

str：在消息对话框中要显示的文本
返回值: Boolean值

```
<script type="text/javascript">
    var mymessage=confirm("你喜欢JavaScript吗?");
    if(mymessage==true)
    {   document.write("很好,加油!");   }
    else
    {  document.write("JS功能强大，要学习噢!");   }
</script>
```
注: 消息对话框是排它的，即用户在点击对话框按钮前，不能进行任何其它操作。

#### 提问（prompt 消息对话框）
prompt弹出消息对话框,通常用于询问一些需要与用户交互的信息。弹出消息对话框（包含一个确定按钮、取消按钮与一个文本输入框）。

语法:

prompt(str1, str2);
参数说明：

str1: 要显示在消息对话框中的文本，不可修改
str2：文本框中的内容，可以修改
返回值:

1. 点击确定按钮，文本框中的内容将作为函数返回值
2. 点击取消按钮，将返回null
看看下面代码:
```
var myname=prompt("请输入你的姓名:");
if(myname!=null)
  {   alert("你好"+myname); }
else
  {  alert("你好 my friend.");  }
```

#### 打开新窗口（window.open）
语法：

window.open([URL], [打开方式], [参数字符串])
参数说明:

URL：可选参数，在窗口中要显示网页的网址或路径。如果省略这个参数，或者它的值是空字符串，那么窗口就不显示任何文档。
窗口名称：可选参数，被打开窗口的名称。
    1.该名称由字母、数字和下划线字符组成。
    2."_top"、"_blank"、"_self"具有特殊意义的名称。
       _blank：在新窗口显示目标网页
       _self：在当前窗口显示目标网页
       _top：框架网页中在上部窗口中显示目标网页
    3.相同 name 的窗口只能创建一个，要想创建多个窗口则 name 不能相同。
   4.name 不能包含有空格。
参数字符串：可选参数，设置窗口参数，各参数用逗号隔开。

参数表:



例如:打开http://www.imooc.com网站，大小为300px * 200px，无菜单，无工具栏，无状态栏，有滚动条窗口：

<script type="text/javascript"> window.open('http://www.imooc.com','_blank','width=300,height=200,menubar=no,toolbar=no, status=no,scrollbars=yes')
</script>


#### 关闭窗口（window.close）
close()关闭窗口

用法：

window.close();   //关闭本窗口
或

<窗口对象>.close();   //关闭指定的窗口
例如:关闭新建的窗口。

<script type="text/javascript">
   var mywin=window.open('http://www.imooc.com'); //将新打的窗口对象，存储在变量mywin中
   mywin.close();
</script>
注意:上面代码在打开新窗口的同时，关闭该窗口，看不到被打开的窗口。


## Dom 模型
文档对象模型DOM（Document Object Model）定义访问和处理HTML文档的标准方法。DOM 将HTML文档呈现为带有元素、属性和文本的树结构（节点树）。

HTML文档可以说由节点构成的集合，三种常见的DOM节点:

1. 元素节点：上图中<html>、<body>、<p>等都是元素节点，即标签。

2. 文本节点:向用户展示的内容，如<li>...</li>中的JavaScript、DOM、CSS等文本。

3. 属性节点:元素属性，如<a>标签的链接属性href="http://www.imooc.com"。

看下面代码:

<a href="http://www.imooc.com">JavaScript DOM</a>


#### 通过ID获取元素
html标签可以定义id属性，如果一个标签定义了id属性，此时javascript可以通过id得到文档对象。
 document.getElementById(“id”) 
 
#### 替换内容

innerHTML 属性用于获取或替换 HTML 元素的内容。
```html
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>innerHTML</title>
</head>
<body>
<h2 id="con">javascript</H2>
<p> JavaScript是一种基于对象、事件驱动的简单脚本语言，嵌入在HTML文档中，由浏览器负责解释和执行，在网页上产生动态的显示效果并实现与用户交互功能。</p>
<script type="text/javascript">
  var mychar=document.getElementById('con');
  document.write("原标题:"+mychar.innerHTML+"<br>"); //输出原h2标签内容
  mychar.innerHTML = "Hello world!"
  document.write("修改后的标题:"+mychar.innerHTML); //输出修改后h2标签内容
</script>
</body>
</html>
```
#### 改变 HTML 样式
HTML DOM 允许 JavaScript 改变 HTML 元素的样式。如何改变 HTML 元素的样式呢？

语法:

Object.style.property=new style;
注意:Object是获取的元素对象，如通过document.getElementById("id")获取的元素。

看看下面的代码:

改变 <p> 元素的样式，将颜色改为红色，字号改为20,背景颜色改为蓝：

<p id="pcon">Hello World!</p>
<script>
   var mychar = document.getElementById("pcon");
   mychar.style.color="red";
   mychar.style.fontSize="20";
   mychar.style.backgroundColor ="blue";
</script>

#### 显示和隐藏

网页中经常会看到显示和隐藏的效果，可通过display属性来设置。

语法：

Object.style.display = value
注意:Object是获取的元素对象，如通过document.getElementById("id")获取的元素。

none : 不显示
block : 显示为块级元素。

#### 控制类名（className 属性）
className 属性设置或返回元素的class 属性。

语法：

object.className = classname
作用:

1.获取元素的class 属性

2. 为网页内的某个元素指定一个css样式来更改该元素的外观

看看下面代码，获得 <p> 元素的 class 属性和改变className：

//定义"取消设置"的函数
```javascript
function cancel() {
    var iscannel = confirm("取消设置");
        
    if (iscannel == true) {
        var obj = document.getElementById("con");
        obj.style = false;
    }
}
```