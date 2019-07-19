# **基础知识学习**

## **基本变量类型介绍**

Python完全面向对象，而不是“静态类型”。在使用变量之前不需要声明变量，也不需要声明它们的类型。Python中的每个变量都是一个对象。

下面将介绍几种基本类型的变量。

### **Numbers(数字)**

数字数据类型用于存储数值。
他们是不可改变的数据类型，这意味着改变数字数据类型会分配一个新的对象。
Python支持三种类型的数字 - 整数，浮点数和复数。本节课程着重介绍如何定义整数和浮点数。

#### **整数定义**

要定义整数，可以使用以下语法：

```r
myint=7
print(myint)
```

#### **浮点数定义**

如果要定义浮点数，可以使用以下两种表示法的其中之一：

```r
myfloat=7.0
print(myfloat)

myfloat=float(7)
print(myfloat)
```

### **字符串**

字符串可以用单引号或者双引号来定义。即以下两种表示法：

```r
mystring='hello'
print(mystring)

mystring="hello"
print(mystring)
```

这两种表示法的区别在于双引号可以很容易地包含撇号（如果使用单引号，这些将终止字符串）

```r
mystring=“Don't worry about apostrophes"
print(mystring)
```

定义字符串还有其他变体，可以更容易地包含回车符，反斜杠和Unicode字符等内容。

另外还可以对数字和字符串执行简单的运算符：

```r
one = 1
two = 2
three = one + two
print(three)

hello = "hello"
world = "world"
helloworld = hello + " " + world
print(helloworld)
```

还可以在同一行上"同时"对多个变量进行分配，如下所示：

```r
a, b = 3, 4
print(a,b)
```

但是python并不支持在数字和字符串之间混合运算符，如下：

```r
# This will not work!
one = 1
two = 2
hello = "hello"

print(one + two + hello)
```

## **练习**

此练习的目标是创建字符串，整数和浮点数。该字符串应该命名，mystring并应包含单词“hello”。浮点数应该命名myfloat并且应该包含数字10.0，并且应该命名整数myint并且应该包含数字20。

需要修改的代码如下：

```r
# change this code
mystring = None
myfloat = None
myint = None

# testing code
if mystring == "hello":
    print("String: %s" % mystring)
if isinstance(myfloat, float) and myfloat == 10.0:
    print("Float: %f" % myfloat)
if isinstance(myint, int) and myint == 20:
    print("Integer: %d" % myint)
```

修改之后代码为：

```r
# change this code
mystring = "hello"
myfloat = 10.0
myint = 20

# testing code
if mystring == "hello":
    print("String: %s" % mystring)
if isinstance(myfloat, float) and myfloat == 10.0:
    print("Float: %f" % myfloat)
if isinstance(myint, int) and myint == 20:
    print("Integer: %d" % myint)
```

输出结果为：

```r
<script.py> output:
    String: hello
    Float: 10.000000
    Integer: 20
```
