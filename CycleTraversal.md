# 循环遍历

循环控制用于对一组数据进行逐个操作，这种操作是建立在遍历的基础上的。

### python
Python 中也有 for 循环，只是 for 循环的机制与其他编译型语言有些不同，这使得他的样子也有些不同。
```python
for 元素　in 列表:　＃ 注意这里的冒号“：”，这是循环体开始的标志
    ＃ 对元素进行具体操作
    
magicians = ['alice', 'david', 'carolina']
for magician in magicians:
  print(magician)
```
python 使用缩进进行逻辑块的整理。如果想要在 for 循环之后继续进行一下操作。只需要讲缩进与 for 开始的地方对其，而不是与其子块对其就行了
```python
magicians = ['alice', 'david', 'carolina']
for magician in magicians:
  print(magician.title() + ", that was a great trick!")
  print("I can't wait to see your next trick, " + magician.title() + ".\n")

print("Thank you, everyone. That was a great magic show!")
```
##### 在循环中使用索引访问列表
python 的循环只能使用 in 来遍历列表中的所有元素，没有对某一元素逐渐加一，达到某一临界值结束循环的控制。要想使用索引访问列表，就要自己创建一个索引的
列表，用在　for 的控制结构中,幸运的是 python 提供了快速生成数字列表的方式 range():
range有多种不同的生成方式：
```python
# 从某个数开始，到某个数之前的所有整数
for value in range(1,5):
  print(value)
```
```
1
2
3
4
```
##### 使用 range() 创建数字列表
要创建数字列表,可使用函数 list() 将 range() 的结果直接转换为列表。如果将 range() 作为 list() 的参数,输出将为一个数字列表。
在前一节的示例中,我们打印了一系列数字。要将这些数字转换为一个列表,可使用 list() :
```python
numbers = list(range(1,6))
print(numbers)
```
使用 range 还可以指定步长。
```python
even_numbers = list(range(2,11,2))
print(even_numbers)
```

##### 列表解析
列表解析将 for 循环和创建新元素的代码合成在一起
```python
squares = [value**2 for value in range(1,11)]
print(squares)

# 如下等价的方法
squares = []
for value in range(1,11):
  squares.append(value**2)
```
列表解析允许将一个 for 循环表达式放在列表的方括号中，用于生成你要存储到列表中的值。表达式后跟一个 for 循环来为表达式提供值。这里表达式为value**2，
使用for value in range(1,11)为value提供值，表达式的结果将作为新创建列表的元素。




