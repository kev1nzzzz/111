# **基础知识学习**

## **字符串格式化**

Python 支持格式化字符串的输出 。Python使用C风格的字符串格式来创建新的格式化字符串。“％”运算符用于格式化包含在“元组”（固定大小列表）中的一组变量，以及格式字符串，其中包含普通文本和“参数说明符”，特殊符号如“％s”和“％d”。

假设有一个名为“name”的变量，其中包含您的用户名，然后您可以打印（向该用户发出问候语。）如下所示：

```r
# This prints out "Hello, John!"
name = "John"
print("Hello, %s!" % name)
```

结果显示如下：

```r
Hello, John!
```

要使用两个或更多参数说明符，可以使用元组（括号），如下所示：

```r
# This prints out "John is 23 years old."
name = "John"
age = 23
print("%s is %d years old." % (name, age))
```

结果显示如下：

```r
John is 23 years old.
```

另外，任何非字符串的对象也可以使用％s运算符进行格式化。从该对象的“repr”方法返回的字符串被格式化为字符串。例如：

```r
# This prints out: A list: [1, 2, 3]
mylist = [1,2,3]
print("A list: %s" % mylist)
```

结果如下：

```r
A list: [1, 2, 3]
```

以下是应该了解的一些基本参数说明符：
%s - 字符串（或任何具有字符串表示形式的对象，如数字）

%d - 整数

%f - 浮点数

%.<number of digits>f - 在点右边有固定位数的浮点数。

%x/%X - 十六进制表示的整数（小写/大写）


## **练习**

尝试编写一个格式字符串，使用以下语法打印出数据： Hello John Doe. Your current balance is $53.44.

在下面代码段上进行修改：

```r
data = ("John", "Doe", 53.44)
format_string = "Hello"

print(format_string % data)
```

修改完成的代码段如下：

```r
data = ("John", "Doe", 53.44)
format_string = "Hello %s %s. Your current balance is $%s."

print(format_string % data)
```

输出结果如下：

```r
<script.py> output:
    Hello John Doe. Your current balance is $53.44.
```
