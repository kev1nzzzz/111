# **基础知识学习**

## **基本运算符的使用**

本节介绍如何在Python中使用基本运算符。

### **算术运算符**

与任何其他编程语言一样，python中加法，减法，乘法和除法运算符可以与数字一起使用。如下所示：

```r
number = 1 + 2 * 3 / 4.0
print(number)
```

正确结果为2.5。即python中是遵循算数基本操作顺序的。

另外一个可用的运算符是modulo（％）运算符，它返回除法的整数余数。dividend％divisor = remainder。
如下所示：

```r
remainder = 11 % 3
print(remainder)
```

正确结果为2。

另外还可以使用两个乘法符号(*)形成幂关系。如下所示：

```r
squared = 7 ** 2
cubed = 2 ** 3
print(squared)
print(cubed)
```

正确结果为：

```r
49
8
```

### **使用带字符串的运算符**

Python支持使用加法运算符连接字符串，如下所示：

```r
helloworld = "hello" + " " + "world"
print(helloworld)
```

正确结果如下：

```r
hello world
```

Python还支持将字符串相乘以形成具有重复序列的字符串,如下所示：

```r
lotsofhellos = "hello" * 10
print(lotsofhellos)
```

正确结果如下：

```r
hellohellohellohellohellohellohellohellohellohello
```

### **使用带有列表的运算符**

列表可以与加法运算符连接,如下所示：

```r
even_numbers = [2,4,6,8]
odd_numbers = [1,3,5,7]
all_numbers = odd_numbers + even_numbers
print(all_numbers)
```

正确结果如下：

```r
[1, 3, 5, 7, 2, 4, 6, 8]
```

就像在字符串中一样，Python支持使用乘法运算符形成具有重复序列的新列表,如下所示：

```r
print([1,2,3] * 3)
```

正确结果如下：

```r
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

## **练习**

这个练习的目标是创建两个列表称为x_list和y_list区，其中包含变量的10个实例x，并y分别。您还需要创建一个名为列表big_list，其中包含变量x和y，每组10次，通过连接你已经创建了两个列表。

需要修改的代码段如下：

```r
x = object()
y = object()

# TODO: change this code
x_list = [x]
y_list = [y]
big_list = []

print("x_list contains %d objects" % len(x_list))
print("y_list contains %d objects" % len(y_list))
print("big_list contains %d objects" % len(big_list))

# testing code
if x_list.count(x) == 10 and y_list.count(y) == 10:
    print("Almost there...")
if big_list.count(x) == 10 and big_list.count(y) == 10:
    print("Great!")
```

修改完成后的代码如下：

```r
x = object()
y = object()

# TODO: change this code
x_list = [x] * 10
y_list = [y] * 10
big_list = x_list + y_list

print("x_list contains %d objects" % len(x_list))
print("y_list contains %d objects" % len(y_list))
print("big_list contains %d objects" % len(big_list))

# testing code
if x_list.count(x) == 10 and y_list.count(y) == 10:
    print("Almost there...")
if big_list.count(x) == 10 and big_list.count(y) == 10:
    print("Great!")
```

正确结果如下：

```r
<script.py> output:
    x_list contains 10 objects
    y_list contains 10 objects
    big_list contains 20 objects
    Almost there...
    Great!
```

