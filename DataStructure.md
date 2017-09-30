这里至只记录语言内置的一些高级数据类型。

# 列表

**列表** 由一系列按特定顺序排列的元素组成。你可以创建包含字母表中所有字母、数字 0~9 或所有家庭成员姓名的列表;也可以将任何东西加入列表中,其中的元素之间可以没有
任何关系。鉴于列表通常包含多个元素,给列表指定一个表示复数的名称(如 letters 、 digits 或 names )是个不错的主意。

### python中的列表

在 Python 中,用方括号( [] )来表示列表,并用逗号来分隔其中的元素。

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
```
