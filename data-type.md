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
Python字符串拼接的几种方法整理

第一种 通过加号(+)的形式
```
print('第一种方式通过加号形式连接 ：' + 'love'+'Python' + '\n')
```
第二种 通过逗号(,)的形式。逗号并不会拼接字符串，返回的是一个逗号分隔元素的元组。这是print输出时将元组拼接成了字符串。
```
print('第二种方式通过逗号形式连接 ：' + 'love', 'Python' + '\n')
```
第三种 直接连接 中间有无空格均可
```
print('第三种方式通过直接连接形式连接 (一) ：' + 'love''Python' + '\n')
print('第三种方式通过直接连接形式连接 (二) ：' + 'love'  'Python' + '\n')
```
第四种 格式化
```
print('第四种方式通过格式化形式连接 ：' + '%s %s' % ('love', 'Python') + '\n')
```
第五种 join方式连接
```
str_list = ['love', 'Python']
print('第五种方式通过join形式连接 ：' + ''.join(str_list) + '\n')
```

第六种 format 方法是 Python 2.6 中出现的一种代替 % 操作符的字符串格式化方法，同样可以用来连接字符串。
```
print('{}{}'.format('hello', ' world')
```

第七种，使用f-string方式。

Python 3.6 中引入了 Formatted String Literals（字面量格式化字符串），简称 f-string，f-string 是 % 操作符和 format 方法的进化版，使用 f-string 连接字符串的方法和使用 %操作符、format 方法类似。
```
>>> aa, bb = 'hello', 'world'
>>> f'{aa} {bb}'
'hello world'
```

第八种，使用*操作符。
```
>>> aa = 'hello '
>>> aa * 3
'hello hello hello '
```
以上方式中，二、三很鸡肋，因为这种形式不允许使用变量，谁会愿意多敲一些字符来添加拼接。这种方式也不能应用于换行，毕竟换行等于一条心的语句。
方法四和方法一差不多，但是方法四显然没有方法一的语义性要好。推荐使用方法一。
方法五是无法替代的，主要是用来很方便的拼接一个列表成一个字符串，不用for循环，代码更简洁。

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
