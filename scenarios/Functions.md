# **基础知识学习**

## **python中的函数(function)**

### **什么是函数？**

函数是将代码划分为有用块的便捷方式，允许我们对代码进行排序，使其更具可读性，重用代码并节省时间。函数也是定义接口的关键方法，因此程序员可以共享代码。

### **如何用Python编写函数？**

正如我们在之前的教程中看到的那样，Python使用了块。

块是以下列格式编写的代码区域：

```r
block_head:
    1st block line
    2nd block line
    ...
```

一个块行是更多的python代码（甚至是另一个块），并且块头的格式如下：block_keyword block_name（argument1，argument2，…）您已经知道的block关键字是“if”、“for”和“while”。

python中的函数使用块关键字“def”定义，然后使用函数的名称作为块的名称。例如：

```r
def my_function():
    print("Hello From My Function!")
```

函数也可以接收参数（从调用者传递给函数的变量）。例如：

```r
def my_function_with_args(username, greeting):
    print("Hello, %s , From My Function!, I wish you %s"%(username, greeting))
```

函数可以使用keyword-'return'将值返回给调用者。例如：

```r
def sum_two_numbers(a, b):
    return a + b
```

### **如何在Python中调用函数？**

只需编写函数的名称后跟（），将任何必需的参数放在括号内。例如，我们可以调用上面写的函数（在前面的例子中）：

```r
# Define our 3 functions
def my_function():
    print("Hello From My Function!")

def my_function_with_args(username, greeting):
    print("Hello, %s , From My Function!, I wish you %s"%(username, greeting))

def sum_two_numbers(a, b):
    return a + b

# print(a simple greeting)
my_function()

#prints - "Hello, John Doe, From My Function!, I wish you a great year!"
my_function_with_args("John Doe", "a great year!")

# after this line x will hold the value 3!
x = sum_two_numbers(1,2)
```

输出结果如下：

```r
Hello From My Function!
Hello, John Doe , From My Function!, I wish you a great year!
```

## **练习**

在本练习中，使用现有函数，并在添加自己的函数时创建一个功能齐全的程序。

1.添加一个名为的函数list_benefits()，返回以下字符串列表：“更有组织的代码”，“更易读的代码”，“更轻松的代码重用”，“允许程序员共享和连接代码”

2.添加一个名为的函数build_sentence(info)，它接收一个包含字符串的参数，并返回一个以给定字符串开头并以字符串“是函数的好处！”结尾的句子。

3.运行并查看所有功能一起工作！

在下面代码中修改：

```r
# Modify this function to return a list of strings as defined above
def list_benefits():
    pass

# Modify this function to concatenate to each benefit - " is a benefit of functions!"
def build_sentence(benefit):
    pass

def name_the_benefits_of_functions():
    list_of_benefits = list_benefits()
    for benefit in list_of_benefits:
        print(build_sentence(benefit))

name_the_benefits_of_functions()
```

修改结果如下：

```r
# Modify this function to return a list of strings as defined above
def list_benefits():
    return "More organized code", "More readable code", "Easier code reuse", "Allowing programmers to share and connect code together"

# Modify this function to concatenate to each benefit - " is a benefit of functions!"
def build_sentence(benefit):
    return "%s is a benefit of functions!" % benefit


def name_the_benefits_of_functions():
    list_of_benefits = list_benefits()
    for benefit in list_of_benefits:
        print(build_sentence(benefit))

name_the_benefits_of_functions()
```

输出结果如下：

```r
<script.py> output:
    More organized code is a benefit of functions!
    More readable code is a benefit of functions!
    Easier code reuse is a benefit of functions!
    Allowing programmers to share and connect code together is a benefit of functions!
```