&lt;hr /&gt; horizontal ruler 横线

&lt;br /&gt; blank row 空行

hr 后面的 / 就是xhtml规定的结束标注，根本不是没有结束标志，因为html中的hr是一个空标签，在xhtml中要求空标签必须结束，所有就在前面加一个/, 其实&lt;hr/&gt;也是可以的，但是为了应对所有浏览器的兼容性，最好在“/” 前面加上一个空格.以上。

&lt;address&gt;  （比如电子邮件地址）、签名或者文档的作者身份

&lt;code&gt; 代码 在文章中一般如果要插入多行代码时不能使用&lt;code&gt;标签了。如果是多行代码，可以使用&lt;pre&gt;标签。作用是 防止浏览器误认为是要执行代码，而没显示代码。加了标签浏览器就不会执行了，而是像文本一样显示出来

`<pre>`标签不只是为显示计算机的源代码时用的，在你需要在网页中预显示格式时都可以使用它，只是`<pre>`标签的一个常见应用就是用来展示计算机的源代码。

#### 列表
```
<ul>
    <li>我的第一个列表信息</li>
    <li>我的第二个列表信息</li>
</ul>
```

li 在英文里代表 List，列表中的一项。

ol 在英文里代表 ordered list

ul 在英文里代表 unordered list

ol有序列表；ul无序列表；li列表项目

&lt;div&gt; 在网页制作过程过中，可以把一些独立的逻辑部分划分出来，放在一个`<div>`标签中，这个&lt;div&gt;标签的作用就相当于一个容器。

1.div和span，2个都是用来划分区间但是没有实际语义的标签,差别就在于div是块级元素,不会其他元素在同一行;span是内联元素~可以与其他元素位于同一行~

用`id`属性来为`<div>`提供唯一的名称，这个就像我们每个人都有一个身份证号，这个身份证号是唯一标识我们的身份的，也是必须唯一的。

创建表格的四个元素：

table、tbody、tr、th、td

```
<table>
    <caption>标题文本</caption>
    <body>
    <tr>
        <td>…</td>
        <td>…</td>
        </tr>…</table>
    <tr>
    <body>

</table>
```

摘要的内容是不会在浏览器中显示出来的。它的作用是增加表格的可读性\(语义化\)，使搜索引擎更好的读懂表格内容，还可以使屏幕阅读器更好的帮助特殊用户读取表格内容。

1、&lt;table summary="表格简介文本"&gt;…&lt;/table&gt;：整个表格以`<table>`标记开始、`</table>`标记结束。

2、&lt;tbody&gt;…&lt;/tbody&gt;：如果不加&lt;thead&gt;&lt;tbody&gt;&lt;tfooter&gt; , table表格加载完后才显示。加上这些表格结构， tbody包含行的内容下载完优先显示，不必等待表格结束后在显示，同时如果表格很长，用tbody分段，可以一部分一部分地显示。（通俗理解table 可以按结构一块块的显示，不在等整个表格加载完后显示。\)

\( tbody 防止那种因网速慢加载一点显示一点的情况，

如果把网页比作一个女士

加载样式的过程是化妆过程

那么tbody就相当于屏蔽了化妆的过程直到

女士化好妆在真正出来见人\)

3、&lt;tr&gt;…&lt;/tr&gt;：表格的一行，所以有几对tr 表格就有几行。

4、&lt;td&gt;…&lt;/td&gt;：表格的一个单元格，一行中包含几对`<td>...</td>`，说明一行中就有几列。

5、&lt;th&gt;…&lt;/th&gt;：表格的头部的一个单元格，**表格表头。**

6、表格中列的个数，取决于一行中数据单元格的个数。

1、table表格在没有添加css样式之前，在浏览器中显示是没有表格线的

2、表头，也就是th标签中的文本默认为**粗体**并且**居中**显示

```
<a  href="目标网址"  title="鼠标滑过显示的文本" arget="_blank">链接显示的文本</a>
```

title属性的作用，鼠标滑过链接文字时会显示这个属性的文本内容。这个属性在实际网页开发中作用很大，主要方便搜索引擎了解链接地址的内容（语义化更友好），如右侧案例代码（8-12行）。

href：Hypertext Reference的缩写。意思是超文本引用

标签在默认情况下，链接的网页是在当前浏览器窗口中打开，有时我们需要在新的浏览器窗口中打开。t**arget="\_blank"**

\_blank -- 在新窗口中打开链接

\_parent -- 在父窗体中打开链接

\_self -- 在当前窗体打开链接,此为默认值

\_top -- 在当前窗体打开链接，并替换当前的整个窗体\(框架页\)

一个对应的框架页的名称 -- 在对应框架页中打开

**注意：**还有一个有趣的现象不知道小伙伴们发现了没有，只要为文本加入a标签后，文字的颜色就会自动变为蓝色（被点击过的文本颜色为紫色），颜色很难看吧，不过没有关系后面我们学习了css样子就可以设置过来（a{color:\#000}\),后面会详细讲解。

`<a>`标签还有一个作用是可以链接Email地址，使用mailto能让访问者便捷向网站管理者发送电子邮件。我们还可以利用`mailto`做许多其它事情。下面一一进行讲解，请看详细图示：

Mailto后为收件人地址，cc后为抄送地址，bcc后为密件抄送地址，subject后为邮件的主题，body后为邮件的内容，如果Mailto后面同时有多个参数的话，第一个参数必须以“?”开头，后面的每一个都以“&”开头。下面是一个完整的实例:Mailto:aaa@xxx.com?cc=bbb@yyy.com&bcc=ccc@zzz.com&subject=主题&body=邮件内容

引号只有一对，代码中间不能留空

&lt;form  method="post" action="save.php"&gt;

```
账户: &lt;input type="text" name="myName"/&gt;    &lt;br&gt;

密码: &lt;input type="password" name="pass"/&gt;&lt;br&gt;

账户:  &lt;input  type="text"  name="myName" placeholder='请输入账号'/&gt;&lt;br&gt;

账户: &lt;input  type="text"  name="myName" value='请输入账号'/&gt;
```

&lt;/form&gt;

value="xxx" 应该有的比较少了吧？感觉 placeholder="xxx" 的体验更好一些。

hidden 定义隐藏输入字段

image 定义图像作为提交按钮

number 定义带有 spinner 控件的数字字段

password 定义密码字段。字段中的字符会被遮蔽

radio 定义单选按钮

range 定义带有 slider 控件的数字字段

reset 定义重置按钮。重置按钮会将所有表单字段重置为初始值

search 定义用于搜索的文本字段

submit 定义提交按钮。提交按钮向服务器发送数据

text 默认。定义单行输入字段，用户可在其中输入文本。默认是 20 个字符

url 定义用于 URL 的文本字段

```
<textarearows="行数"cols="列数">文本</textarea>
```

当用户需要在表单中输入大段文字时，需要用到文本输入域。标签的语义一定要根据单词来记忆，这样才会扎实透彻，

&lt;pre&gt;preformattde：预定义格式\(文本\)的意思，这里的&lt;textarea&gt;是多行文本区域的意思，根据意思就知道不同了，而且

&lt;textarea&gt;中的默认字样，用户可以自行更改的，&lt;pre&gt;中的内容，用户只能看不能动！要是根据他的解释来，那么所有的input标签基本都是一样的，因为大多数都可以设置value="默认显示"的。

在使用表单设计调查表时，为了减少用户的操作，使用选择框是一个好主意，html中有两种选择框，即

**单选框**和**复选框**，两者的区别是**单选框**中的选项用户只能选择一项，而**复选框**中用户可以任意选择多项，甚至全选。请看下面的例子:

```
<input   type="radio/checkbox"   value="值"    name="名称"   checked="checked"/>
```

name 相同为同一组。

当**type="radio"**时，控件为**单选框，**当**type="checkbox"**时，控件为**复选框**

下拉菜单

&lt;label&gt;爱好:&lt;/label&gt;

```
&lt;select&gt;

  &lt;option value="看书"&gt;看书&lt;/option&gt;

  &lt;option value="旅游" selected="selected"&gt;旅游&lt;/option&gt;

  &lt;option value="运动"&gt;运动&lt;/option&gt;

  &lt;option value="购物"&gt;购物&lt;/option&gt;

&lt;/select&gt;
```

下拉列表也可以进行多选操作，在&lt;select&gt;标签中设置`multiple="multiple"`属性，就可以实现多选功能，在 windows 操作系统下，进行多选时按下`Ctrl`键同时进行`单击`（在 Mac下使用Command+单击），可以选择多个选项。如下代码：

label标签不会向用户呈现任何特殊效果，它的作用是为鼠标用户改进了可用性。如果你在 label 标签内点击文本，就会触发此控件。就是说，当用户单击选中该label标签时，浏览器就会自动将焦点转到和标签相关的表单控件上（就自动选中和该label标签相关连的表单控件上）。

&lt;label for="male"&gt;男&lt;/label&gt;

&lt;input type="radio" name="gender" id="male" /&gt;

不加label的话鼠标一定要点击小圆点才能激活条目,加了label可以直接点击对应的文字来激活条目

