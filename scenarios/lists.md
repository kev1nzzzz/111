# **基础知识学习**

## **Python列表**

List（列表） 是 Python 中使用最频繁的数据类型。
列表可以完成大多数集合类的数据结构实现。它支持字符，数字，字符串甚至可以包含列表（即嵌套）。列表与数组非常相似。列表也可以以非常简单的方式迭代。以下是如何构建列表的示例。

```r
mylist = []
mylist.append(1)
mylist.append(2)
mylist.append(3)
print(mylist[0]) # prints 1
print(mylist[1]) # prints 2
print(mylist[2]) # prints 3

# prints out 1,2,3
for x in mylist:
    print(x)
```

显示结果为：
```r
1
2
3
1
2
3
```

如果访问不存在的索引会生成异常（错误）。如下所示：
```r
mylist = [1,2,3]
print(mylist[10])
```
结果会显示列表索引超出范围的错误。

## **练习**

在本次练习中，您需要使用“append”列表方法将数字和字符串添加到正确的列表中。您必须将数字1,2和3添加到“数字”列表中，并将“hello”和“world”添加到strings变量中。

您还必须使用括号运算符在名称列表中使用第二个名称填充变量second_name []。请注意，索引从零开始，因此如果要访问列表中的第二项，则其索引将为1。

需要进行添加修改的代码段为：

```r
numbers = []
strings = []
names = ["John", "Eric", "Jessica"]

# write your code here
second_name = None


# this code should write out the filled arrays and the second name in the names list (Eric).
print(numbers)
print(strings)
print("The second name on the names list is %s" % second_name)
```

修改之后为：

```r
numbers = []
strings = []
names = ["John", "Eric", "Jessica"]

# write your code here
numbers.append(1)
numbers.append(2)
numbers.append(3)

strings.append("hello")
strings.append("world")

second_name = names[1]

# this code should write out the filled arrays and the second name in the names list (Eric).
print(numbers)
print(strings)
print("The second name on the names list is %s" % second_name)
```

正确结果显示为：

```r
<script.py> output:
    [1, 2, 3]
    ['hello', 'world']
    The second name on the names list is Eric
```
