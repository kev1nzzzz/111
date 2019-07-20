# **基础知识学习**

## **python中的条件语句**

Python条件语句是通过一条或多条语句的执行结果（True或者False）来决定执行的代码块。使用布尔变量来评估条件。即比较或计算表达式时返回布尔值True和False。

如下所示：

```r
x = 2
print(x == 2) # prints out True
print(x == 3) # prints out False
print(x < 3) # prints out True
```

输出结果如下：

```r
True
False
True
```

这里需要注意的是，变量赋值是使用单个“=”运算符完成的，而两个变量之间的比较使用double equals运算符“==”完成。“not equals”运算符标记为“！=”。这里和c++是相同的。

Python 编程中 if 语句用于控制程序的执行，基本形式为：

```r
if 判断条件：
    执行语句……
else：
    执行语句……
```

其中"判断条件"成立时（非零），则执行后面的语句，而执行内容可以多行，以缩进来区分表示同一范围。
else 为可选语句，当需要在条件不成立时执行内容则可以执行相关语句。

### **布尔(boolean)运算符**

“and”和“or”布尔运算符允许构建复杂的布尔表达式，例如：

```r
name = "John"
age = 23
if name == "John" and age == 23:
    print("Your name is John, and you are also 23 years old.")

if name == "John" or name == "Rick":
    print("Your name is either John or Rick.")
```

输出结果为：

```r
Your name is John, and you are also 23 years old.
Your name is either John or Rick.
```

即如果判断需要多个条件需同时判断时，可以使用 or （或），表示两个条件有一个成立时判断条件成功；使用 and （与）时，表示只有两个条件同时成立的情况下，判断条件才成功。

### **"in"运算符**

“in”运算符可用于检查可迭代对象容器中是否存在指定对象，例如列表：

```r
name = "John"
if name in ["John", "Rick"]:
    print("Your name is either John or Rick.")
```

输出结果如下：

```r
Your name is either John or Rick.
```

由之前的课程我们知道，Python使用缩进来定义代码块，而不是括号。标准的Python缩进是4个空格，虽然标签和任何其他空间大小都可以使用，只要它是一致的。请注意，代码块不需要任何终止。

以下是使用Python的“if”语句使用代码块的示例：

```r
if <statement true="" is="">:
    <do something="">
    ....
    ....
elif <another true="" is="" statement="">: # else if
    <do something="" else="">
    ....
    ....
else:
    <do thing="" another="">
    ....
    ....
</do></do></another></do></statement>
```

例如：

```r
x = 2
if x == 2:
    print("x equals two!")
else:
    print("x does not equal to two.")
```

输出结果为：

```r
x equals two!
```

如果下列其中一项正确，则声明为真：1。给出“True”布尔变量，或使用表达式计算，例如算术比较。2.传递不被视为“空”的对象。

以下是被视为空的对象的一些示例：1。空字符串：“”2。空列表：[] 3.数字零：0 4.错误布尔变量：False


### **"is"运算符**

与double equals运算符“==”不同，“is”运算符与变量的值不匹配，但与实例本身匹配。例如：

```r
x = [1,2,3]
y = [1,2,3]
print(x == y) # Prints out True
print(x is y) # Prints out False
```

输出结果为：

```r
True
False
```

### **"not"运算符**

在布尔表达式之前使用“not”将其反转,如下所示：

```r
print(not False) # Prints out True
print((not False) == (False)) # Prints out False
```

输出结果为：

```r
True
False
```

## **练习**

更改原代码中的变量，以便每个if语句解析为True。

原代码：

```r
# change this code
number = 10
second_number = 10
first_array = []
second_array = [1,2,3]

if number > 15:
    print("1")

if first_array:
    print("2")

if len(second_array) == 2:
    print("3")

if len(first_array) + len(second_array) == 5:
    print("4")

if first_array and first_array[0] == 1:
    print("5")

if not second_number:
    print("6")
```

更改后的参考代码如下：

```r
# change this code
number = 16
second_number = 0
first_array = [1,2,3]
second_array = [1,2]

if number > 15:
    print("1")

if first_array:
    print("2")

if len(second_array) == 2:
    print("3")

if len(first_array) + len(second_array) == 5:
    print("4")

if first_array and first_array[0] == 1:
    print("5")

if not second_number:
    print("6")
```

输出的正确结果为：

```r
<script.py> output:
    1
    2
    3
    4
    5
    6
```
