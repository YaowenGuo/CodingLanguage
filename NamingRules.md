# 命名规则
所有的语言自定义标识符都不能是关键字。
### c

### c++
 
### Java

### python 变量的命名和使用

在 Python 中使用变量时,需要遵守一些规则和指南。违反这些规则将引发错误,而指南旨在让你编写的代码更容易阅读和理解。请务必牢记下述有关变量的规则。

- 变量名只能包含字母、数字和下划线。变量名可以字母或下划线打头,但不能以数字打头,例如,可将变量命名为 message_1 ,但不能将其命名为 1_message 。
- 变量名不能包含空格,但可使用下划线来分隔其中的单词。例如,变量名 greeting_message 可行,但变量名 greeting message 会引发错误。
- 不要将 Python 关键字和函数名用作变量名,即不要使用 Python 保留用于特殊用途的单词,如 print (请参见附录 A.4 )。

建议性规范
- 变量名应既简短又具有描述性。例如, name 比 n 好, student_name 比 s_n 好, name_length 比 length_of_persons_name 好。
- 慎用小写字母 l 和大写字母 O ,因为它们可能被人错看成数字 1 和 0 。
要创建良好的变量名,需要经过一定的实践,在程序复杂而有趣时尤其如此。随着你编写的程序越来越多,并开始阅读别人编写的代码,将越来越善于创建有意义的变量名。
注意  就目前而言,应使用小写的 Python 变量名。在变量名中使用大写字母虽然不会导致错误,但避免使用大写字母是个不错的主意。

### java script 
由一个字符开头，后面选择性的加上一个或多个字母、数字、下换线。 


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


# 注释
puthon使用#来作为注释符号。

Java Script 同java 和 c 一样。但是java script的块注释/**/字符也可能出现在正则表达式中，所以用快注释来注释代码是不安全的，建议使用// 代替。例如：
```javascript
/*
var rm_a = /a*/.match(s);
```



