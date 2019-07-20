# **基础知识学习**

## **类和对象**

### **Python面向对象**

Python从设计之初就已经是一门面向对象的语言，正因为如此，在Python中创建一个类和对象是很容易的。本章节我们将详细介绍Python的面向对象编程。
如果你以前没有接触过面向对象的编程语言，那你可能需要先了解一些面向对象语言的一些基本特征，在头脑里头形成一个基本的面向对象的概念，这样有助于你更容易的学习Python的面向对象编程。
接下来我们先来简单的了解下面向对象的一些基本特征。

#### **面向对象技术简介**

**类(Class)**: 用来描述具有相同的属性和方法的对象的集合。它定义了该集合中每个对象所共有的属性和方法。对象是类的实例。
**类变量**：类变量在整个实例化的对象中是公用的。类变量定义在类中且在函数体之外。类变量通常不作为实例变量使用。
**数据成员**：类变量或者实例变量, 用于处理类及其实例对象的相关的数据。
**方法重写**：如果从父类继承的方法不能满足子类的需求，可以对其进行改写，这个过程叫方法的覆盖（override），也称为方法的重写。
**局部变量**：定义在方法中的变量，只作用于当前实例的类。
**实例变量**：在类的声明中，属性是用变量来表示的。这种变量就称为实例变量，是在类声明的内部但是在类的其他成员方法之外声明的。
**继承**：即一个派生类（derived class）继承基类（base class）的字段和方法。继承也允许把一个派生类的对象作为一个基类对象对待。例如，有这样一个设计：一个Dog类型的对象派生自Animal类，这是模拟"是一个（is-a）"关系（例图，Dog是一个Animal）。
**实例化**：创建一个类的实例，类的具体对象。
**方法**：类中定义的函数。
**对象**：通过类定义的数据结构实例。对象包括两个数据成员（类变量和实例变量）和方法。

### **创建类(class)**

一个非常基本的类看起来像这样：

```r
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")
```

我们将解释为什么你必须稍后将“self”作为参数包含在内。首先，要将上述类（模板）分配给对象，您将执行以下操作：

```r
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
```

现在，变量“myobjectx”包含“MyClass”类的对象，该对象包含变量和名为“MyClass”的类中定义的函数。

### **访问对象变量**

要访问新创建的对象“myobjectx”中的变量，您可以执行以下操作：

```r
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.variable
```

输出结果如下：

```r
Out[1]: 'blah'
```

例如下面会输出字符串“blah”：

```r
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

print(myobjectx.variable)
```

您可以创建多个具有相同类的不同对象（定义相同的变量和函数）。但是，每个对象都包含类中定义的变量的独立副本。例如，如果我们使用“MyClass”类定义另一个对象，然后更改上面变量中的字符串：

如下所示：

```r
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
myobjecty = MyClass()

myobjecty.variable = "yackity"

# Then print out both values
print(myobjectx.variable)
print(myobjecty.variable)
```

输出结果如下：

```r
blah
yackity
```

### **访问对象功能**

要访问对象内部的函数，需要使用与访问变量类似的符号：

```r
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.function()
```

输出结果如下：

```r
This is a message inside the class.
```

## **练习**

我们有一个为车辆定义的类。创建两个名为car1和car2的新车。将car1设置为价值60,000.00美元的红色敞篷车，名称为Fer，而car2则是名为Jump的蓝色面包车价值$ 10,000.00。

在下面的代码中写入正确的代码段：

```r
# define the Vehicle class
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def description(self):
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str
# your code goes here

# test code
print(car1.description())
print(car2.description())
```

正确的代码段示范：

```r
# define the Vehicle class
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def description(self):
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str

# your code goes here
car1 = Vehicle()
car1.name = "Fer"
car1.color = "red"
car1.kind = "convertible"
car1.value = 60000.00

car2 = Vehicle()
car2.name = "Jump"
car2.color = "blue"
car2.kind = "van"
car2.value = 10000.00

# test code
print(car1.description())
print(car2.description())
```

输出结果如下：

```r
<script.py> output:
    Fer is a red convertible worth $60000.00.
    Jump is a blue van worth $10000.00.
```

