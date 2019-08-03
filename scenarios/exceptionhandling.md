# **高级教程**

## **异常错误处理**

编程时难免出现错误，也许用户提供了错误的输入，也许网络资源不可用，也许程序内存不足，或者程序员甚至可能犯了错误。

但是Python的错误解决方案是例外。

例如：

```r
print(a)

#error
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'a' is not defined
</module></stdin>
```

这儿的错误是忘了为'a'变量赋值。

但有时你不希望发生异常错误时完全停止程序。引发异常时，您可能希望执行一些特殊操作。这是在try / except块中完成的。

这是一个简单的例子：假设你在列表上进行迭代。您需要迭代超过20个数字，但列表是由用户输入组成的，并且可能没有20个数字。到达列表末尾后，您只需将其余数字解释为0.以下是您可以这样做的方法：

```r
def do_stuff_with_number(n):
        print(n)

the_list = (1, 2, 3, 4, 5)

for i in range(20):
    try:
        do_stuff_with_number(the_list[i])
    except IndexError: # Raised when accessing a non-existing index of a list
        do_stuff_with_number(0)
```

输出结果：

```r
1
2
3
4
5
0
0
0
0
0
0
0
0
0
0
0
0
0
0
0
```

## **练习**

处理原代码中的所有异常。

原代码：

```r
# Handle all the exceptions!
#Setup
actor = {"name": "John Cleese", "rank": "awesome"}

#Function to modify, should return the last name of the actor - think back to previous lessons for how to get it
def get_last_name():
    return actor["last_name"]

#Test code
get_last_name()
print("All exceptions caught! Good job!")
print("The actor's last name is %s" % get_last_name())
```

修改完的代码：

```r
actor = {"name": "John Cleese", "rank": "awesome"}

def get_last_name():
    return actor["name"].split()[1]

get_last_name()
print("All exceptions caught! Good job!")
print("The actor's last name is %s" % get_last_name())
```

输出结果：

```r
<script.py> output:
    All exceptions caught! Good job!
    The actor's last name is Cleese
```
