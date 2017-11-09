这里至只记录语言内置的一些高级数据类型。

# 列表

**列表** 由一系列按特定顺序排列的元素组成。你可以创建包含字母表中所有字母、数字 0~9 或所有家庭成员姓名的列表;也可以将任何东西加入列表中,其中的元素之间可以没有
任何关系。鉴于列表通常包含多个元素,给列表指定一个表示复数的名称(如 letters 、 digits 或 names )是个不错的主意。

### python中的列表

在 Python 中,用方括号( [] )来表示列表,并用逗号来分隔其中的元素。超出列表长度将引起索引越界错误。

```python
bicycles = ['trek', 'cannondale', 'redline', 'specialized']
print(bicycles)
```

如果你让 Python 将列表打印出来, Python 将打印列表的内部表示,包括方括号:

> ['trek', 'cannondale', 'redline', 'specialized']

也可以只打印某个元素, 索引从 0 而不是 1 开始.
> print(bicycles[0])

python为从后向前访问元素做了优化，使用-n表示直接访问从后向前数的第n个元素。
```python
print(bicycles[-1])
```
python中的列表是动态的元素，这意味着程序运行中可以动态的修改、添加、删除元素。

###### 修改
bicycles[0] = 'ducati'
###### 添加
- .append(元素) 末尾添加
- .insert(0, 'ducati') 插入元素
###### 删除
使用 del 语句删除元素
如果知道要删除的元素在列表中的位置,可使用 del 语句。
```python
del motorcycles[1]
```
方法 pop() 可删除列表末尾的元素,并让你能够接着使用它。术语弹出 ( pop )源自这样的类比:列表就像一个栈,而删除列表末尾的元素相当于弹出栈顶元素。
```python
popped_motorcycle = motorcycles.pop()
# 实际上,你可以使用 pop() 来删除列表中任何位置的元素,只需在括号中指定要删除的元素的索引即可。
first_owned = motorcycles.pop(0)
```
根据值删除元素
```python
motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']
print(motorcycles)
motorcycles.remove('honda')

too_expensive = 'ducati'
motorcycles.remove(too_expensive)
```
注意  方法 remove() 只删除第一个指定的值。如果要删除的值可能在列表中出现多次,就需要使用循环来判断是否删除了所有这样的值。

##### 排序
使用方法 sort() 对列表进行永久性排序,再也无法恢复到原来的排列顺序:
```
# 按字母表排序
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort()
print(cars)
# 倒叙　只需向 sort() 方法传递参数 reverse=True
cars.sort(reverse=True)
```
使用函数 sorted() 对列表进行临时排序。函数 sorted() 让你能够按特定顺序显示列表元素,同时不影响它们在列表中的原始排
列顺序。
```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
print("Here is the original list:")
print(cars)
print("\nHere is the sorted list:")
print(sorted(cars))
print("\nHere is the original list again:")
print(cars)
```
也可向函数 sorted() 传递参数 reverse=True 。

注意  在并非所有的值都是小写时,按字母顺序排列列表要复杂些。决定排列顺序时,有多种解读大写字母的方式,要指定准确的排列顺序,可能比我们这里所做的
要复杂。然而,大多数排序方式都基于本节介绍的知识。

##### 倒着打印列表
要反转列表元素的排列顺序,可使用方法 reverse() 。假设汽车列表是按购买时间排列的,可轻松地按相反的顺序排列其中的汽车:
```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
print(cars)
cars.reverse()
print(cars)
```
方法 reverse() 永久性地修改列表元素的排列顺序,但可随时恢复到原来的排列顺序,为此只需对列表再次调用 reverse() 即可。

##### 确定列表的长度
使用函数 len() 可快速获悉列表的长度。
```python
len(cars)
```









