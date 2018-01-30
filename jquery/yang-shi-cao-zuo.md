# 节点操作》
ht

### 属性与样式之.attr()与.removeAttr()
每个元素都有一个或者多个特性，这些特性的用途就是给出相应元素或者其内容的附加信息。如：在img元素中，src就是元素的特性，用来标记图片的地址。

操作特性的DOM方法主要有3个，getAttribute方法、setAttribute方法和removeAttribute方法，就算如此在实际操作中还是会存在很多问题，这里先不说。而在jQuery中用一个attr()与removeAttr()就可以全部搞定了，包括兼容问题

jQuery中用attr()方法来获取和设置元素属性,attr是attribute（属性）的缩写，在jQuery DOM操作中会经常用到attr()

attr()有4个表达式

attr(传入属性名)：获取属性的值
attr(属性名, 属性值)：设置属性的值
attr(属性名,函数值)：设置属性的函数值
attr(attributes)：给指定元素设置多个属性值，即：{属性名一: “属性值一” , 属性名二: “属性值二” , … … }
removeAttr()删除方法

.removeAttr( attributeName ) : 为匹配的元素集合中的每个元素中移除一个属性（attribute）

优点：

attr、removeAttr都是jQuery为了属性操作封装的，直接在一个 jQuery 对象上调用该方法，很容易对属性进行操作，也不需要去特意的理解浏览器的属性名不同的问题

注意的问题：

dom中有个概念的区分：Attribute和Property翻译出来都是“属性”，《js高级程序设计》书中翻译为“特性”和“属性”。简单理解，Attribute就是dom节点自带的属性

例如：html中常用的id、class、title、align等：

<div id="immooc" title="慕课网"></div>
而Property是这个DOM元素作为对象，其附加的内容，例如,tagName, nodeName, nodeType,, defaultChecked, 和 defaultSelected 使用.prop()方法进行取值或赋值等

获取Attribute就需要用attr，获取Property就需要用prop
```
 <script type="text/javascript">
    	//找到第一个input，通过attr设置属性value的值
    	$("input:first").attr('value','.attr( attributeName, value )')
    </script>

    <script type="text/javascript">
    	//找到第二个input，通过attr获取属性value的值
    	$("input:eq(1)").attr('value')
    </script>

    <script type="text/javascript">
    	//找到第三个input，通过使用一个函数来设置属性
    	//可以根据该元素上的其它属性值返回最终所需的属性值
    	//例如，我们可以把新的值与现有的值联系在一起：
    	$("input:eq(2)").attr('value',function(i, val){
    		return '通过function设置' + val
    	})
    </script>

    <script type="text/javascript">
    	//找到第四个input，通过使用removeAttr删除属性
    	$("input:eq(3)").removeAttr('value')
    </script>
```

