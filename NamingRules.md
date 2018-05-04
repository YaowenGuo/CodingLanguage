# 简单数据类型
## 字符串
### python
python中没有单个字符的数据结构，即使单个字符也是以字符串的方式存储的。所以Python不在区分单引号和双引号，用引号括起来的都是字符串。
```python
"This is a string."
'This is also a string.'
```
这种灵活性能够在字符串中直接插入引号和撇号。
```python
'I told my friend, "Python is my favorite language!"'
"The language 'Python' is named after Monty Python, not the snake."
"One of Python's strengths is its diverse and supportive community."
```

- 合并拼接字符串 +
- .title() 将字符串每个单词的首字母大写
- .upper() 全部大写
- .lower() 全部小写
- 制表符\t 换行\n 
- lstrip()删除左侧空白，rstrip()删除右侧空白，strip()删除右侧空白。

## 数字

#### java script 只有一种数字，是64位的浮点数，所以1.0 和1 是相同的。 
### python
python3中两个整数相除能够得到一个浮点数。但在python2中侧和c语言保持一致。

## 数组
#### javascript
我们创建数组的同时，还可以为数组指定长度，长度可任意指定。

var myarray= new Array(8); //创建数组，存储8个数据。
document.write("数组的第一个值："+myarr[0]); // 输出是 undefined。
注意：
1.创建的新数组是空数组，没有值，如输出，则显示undefined。
2.虽然创建数组时，指定了长度，但实际上数组都是变长的，也就是说即使指定了长度为8，仍然可以将元素存储在规定长度以外。

myarray.length; //获得数组myarray的长度
1. 二维数组的表示: myarray[ ][ ]
 二维数组的定义方法一

var myarr=new Array();  //先声明一维 
for(var i=0;i<2;i++){   //一维长度为2
   myarr[i]=new Array();  //再声明二维 
   for(var j=0;j<3;j++){   //二维长度为3
   myarr[i][j]=i+j;   // 赋值，每个数组元素的值为i+j
   }
 }
 
2. 二维数组的定义方法二

var Myarr = [[0 , 1 , 2 ],[1 , 2 , 3]]

动态添加使用push 和动态删除pop。
# 注释
puthon使用#来作为注释符号。

Java Script 同java 和 c 一样。但是java script的块注释/**/字符也可能出现在正则表达式中，所以用快注释来注释代码是不安全的，建议使用// 代替。例如：
```javascript
/*
var rm_a = /a*/.match(s);
```



