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

##### 访问属性
要访问实例的属性，可使用句点表示法。
my_dog.name

句点表示法在Python中很常用，这种语法演示了Python如何获悉属性的值。在这里，Python先找到实例my_dog ，再查找与这个实例相关联的属性name 。在Dog 类中引用这个属 性时，使用的是self.name 。

##### 调用方法
类创建实例后，就可以使用句点表示法来调用Dog 类中定义的任何方法。下面来让小狗蹲下和打滚:
要调用方法，可指定实例的名称(这里是my_dog )和要调用的方法，并用句点分隔它们。遇到代码my_dog.sit() 时，Python在类Dog 中查找方法sit() 并运行其代码。 Python以同样的方式解读代码my_dog.roll_over() 。

##### 继承
编写类时，并非总是要从空白开始。如果你要编写的类是另一个现成类的特殊版本，可使用继承 。一个类继承另一个类时，它将自动获得另一个类的所有属性和方法;原有的类称为父类 ，而新类称为子类 。子类继承了其父类的所有属性和方法，同时还可以定义自己的属性和方法。

*** python支持多继承 ***

1. 创建子类时，父类必须包含在当前文件中，且位于子类前面。
2. 定义子类时，必须在类名后的括号内指定父类的 名称。
###### 构造函数
创建子类的实例时，Python首先需要完成的任务是给父类的所有属性赋值。为此，子类的方法__init__() 需要父类施以援手。
```python
❶ class Car():
     """一次模拟汽车的简单尝试"""
     def __init__(self, make, model, year): self.make = make
        self.model = model
        self.year = year self.odometer_reading = 0
        
    def get_descriptive_name(self):
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
        
    def read_odometer(self):
        print("This car has " + str(self.odometer_reading) + " miles on it.")
        
    def update_odometer(self, mileage):
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):
        self.odometer_reading += miles
        
❷ class ElectricCar(Car):
       """电动汽车的独特之处"""
❸     def __init__(self, make, model, year):
           """初始化父类的属性"""
❹         super().__init__(make, model, year)
           self.battery_size = 70

❷     def describe_battery(self):
           """打印一条描述电瓶容量的消息"""
           print("This car has a " + str(self.battery_size) + "-kWh battery.")
           
       def fill_gas_tank():
           """电动汽车没有油箱"""
           print("This car doesn't need a gas tank!")


❺ my_tesla = ElectricCar('tesla', 'model s', 2016)
  print(my_tesla.get_descriptive_name()

###### 重写父类的方法
对于父类的方法，只要它不符合子类模拟的实物的行为，都可对其进行重写。为此，可在子类中定义一个这样的方法，即它与要重写的父类方法同名。这样，Python将不会考虑这个父类方法，而只关注你在子类中定义的相应方法。

           
      

```

❹处的super() 是一个特殊函数，帮助Python将父类和子类关联起来。这行代码让Python调用ElectricCar 的父类的方法__init__() ，让ElectricCar 实例包含父类的所 有属性。父类也称为超类 (superclass)，名称super因此而得名。

*** python 中的类名和文件名并没有绑定，可以在同一个文件中放置多个类，他们是平等的。改文件称为模块。不像java的一个文件只能包含一个主类，且类名必须和文件名一致。
###### 导入类
类的导入和方法导入一样。都是使用模块名导入类名

from car import Car, ElectrocCar
import 语句让Python打开模块car ，并导入其中的Car 类。这样我们就可以使用Car 类了，就像它是在这个文件中定义的一样。

from module_name import *

不推荐使用这种导入方式，其原因有二。首先，如果只要看一下文件开头的import 语句，就能清楚地知道程序使用了哪些类，将大有裨益;但这种导入方式没有明确地指出你 使用了模块中的哪些类。这种导入方式还可能引发名称方面的困惑。如果你不小心导入了一个与程序文件中其他东西同名的类，将引发难以诊断的错误。这里之所以介绍这种导 入方式，是因为虽然不推荐使用这种方式，但你可能会在别人编写的代码中见到它。
需要从一个模块中导入很多类时，最好导入整个模块，并使用 module_name.class_name 语法来访问类。这样做时，虽然文件开头并没有列出用到的所有类，但你清楚地知 道在程序的哪些地方使用了导入的模块;你还避免了导入模块中的每个类可能引发的名称冲突。








