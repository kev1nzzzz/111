# **高级教程**

## **代码自省(Code Introspection)**

代码内省是检查类，函数和关键字以了解它们是什么，它们做什么以及它们知道什么的能力。

Python为代码内省提供了几个函数和实用程序。

```r
help()
dir() 
hasattr() 
id() 
type() 
repr() 
callable() 
issubclass() 
isinstance() 
__doc__ 
__name__
```

通常最重要的是帮助功能，因为您可以使用它来查找其他功能的功能。

## **练习**

输出给定Vehicle对象的所有属性的列表。

```r
# Use the help function to see what each function does.
# Delete this when you are done.
help(dir)
help(hasattr)
help(id)

# Define the Vehicle class.
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def description(self):
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str

# Print a list of all attributes of the Vehicle class.
# Your code goes here
```

修改完代码如下：

```r
# Define the Vehicle class
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def description(self):
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str

# Print a list of all attributes of the Vehicle class.
print(dir(Vehicle))
```

输出结果如下：

```r
<script.py> output:
    ['__class__', '__delattr__', '__dict__', '__dir__', 
	'__doc__', '__eq__', '__format__', '__ge__', 
	'__getattribute__', '__gt__', '__hash__', '__init__', 
	'__le__', '__lt__', '__module__', '__ne__', '__new__', 
	'__reduce__', '__reduce_ex__', '__repr__', 
	'__setattr__', '__sizeof__', '__str__', 
	'__subclasshook__', '__weakref__', 'color', 
	'description', 'kind', 'name', 'value']
```
