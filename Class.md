# 类
类是面向对象设计中的一个重要概念，是对自然世界的一类实物的划分。然后将其映射到程序设计中。


### python

##### 创建类
python 也是使用关键字 calss 来创建类。
```python
class ClassName():
    def __init__(self, parm1, parm2, ...):
        '''构造函数, 创建对象时自动调用'''
        # initlize class
        
    def function1(self, parm1, parm2, ....):
        # function
        
     ...
     
 # 实际定义
❶ class Dog():
     """ 一次模拟小狗的简单尝试 """
❷    def __init__(self, name, age):
         """ 初始化属性 name 和 age"""
❸       self.name = name
         self.age = age
❹    def sit(self):
         """ 模拟小狗被命令时蹲下 """
         print(self.name.title() + " is now sitting.")
❺    def roll_over(self):
         """ 模拟小狗被命令时打滚 """
         print(self.name.title() + " rolled over!")
         
❶ my_dog = Dog('willie', 6)
❷
❸ print("My dog's name is " + my_dog.name.title() + ".")
  print("My dog is " + str(my_dog.age) + " years old.")

 ```
 __init__方法的名称中,开头和末尾各有两个下划线,这是一种约定,旨在避免 Python 默认方法与普通方法发生名称冲突。
 
形参 self 必不可少,还必须位于其他形参的前面。为何必须在方法定义中包
含形参 self 呢?因为 Python 调用这个 __init__() 方法来创建 Dog 实例时,将自动传入实参 self 。每个与类相关联的方法调用都自动传递实参 self ,它是一个指向实例本身
的引用,让实例能够访问类中的属性和方法。我们创建 Dog 实例时, Python 将调用 Dog 类的方法 __init__() 。我们将通过实参向 Dog() 传递名字和年龄; self 会自动传递,因此我们不需要传递它。每当我们根据 Dog 类创建实例时,都只需给最后两个形参( name 和 age )提供值。

❹处定义的两个变量都有前缀 self 。以 self 为前缀的变量都可供类中的所有方法使用,我们还可以通过类的任何实例来访问这些变量。 self.name = name 获取存储在形
参 name 中的值,并将其存储到变量 name 中,然后该变量被关联到当前创建的实例。 self.age = age 的作用与此类似。像这样可通过实例访问的变量称为属性 。
Dog 类还定义了另外两个方法: sit() 和 roll_over() (见❺)。由于这些方法不需要额外的信息,如名字或年龄,因此它们只有一个形参 self 。我们后面将创建的实例能
够访问这些方法,换句话说,它们都会蹲下和打滚。当前, sit() 和 roll_over() 所做的有限,它们只是打印一条消息,指出小狗正蹲下或打滚。但可以扩展这些方法以模拟
实际情况:如果这个类包含在一个计算机游戏中,这些方法将包含创建小狗蹲下和打滚动画效果的代码。如果这个类是用于控制机器狗的,这些方法将引导机器狗做出蹲下和打
滚的动作。
