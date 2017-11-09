# 常用数据结构

### python
相较于其他语言，python的做法更加简单粗暴。python将一些高级的数据结构内置为语言特性。例如列表，序列，字典。这些特性使python的编码更加快捷和简洁。

##### 列表
######　列表定义
列表是有顺序的数据几何，列表内可以存放任何数据类型，包括列表本身。python使用[] 来创建列表，用逗号分隔其中的元素。
```python
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
print(bicycles)
```
python直接输出列表会输出列表中的所有内容，以及格式。
```python
['trek', 'cannondale', 'redline', 'specialized']
```
###### 访问列表元素
python 使用索引访问列表元素，索引从０开始
```python
print(bicycles[0])
```
python 对索引的访问做了一个其他语言少有的功能用负数表示从后向前的位置的元素。－1表示倒数第一个元素。注意从后向前索引不在从０开始。
```python
print(bicycles[-1])
```
###### 修改
```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
motorcycles[0] = 'ducati'
print(motorcycles)
```
######



