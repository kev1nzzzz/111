# **高级教程**

## **set()函数**

set() 函数创建一个无序不重复元素集，可进行关系测试，删除重复数据，还可以计算交集、差集、并集等，并返回新的集合对象。

假设您要找出一句话中的所有不重复的单词，例如"my name is Eric and Eric is my name"这句话：

```r
print(set("my name is Eric and Eric is my name".split()))
```

输出结果：

```r
{'and', 'name', 'Eric', 'my', 'is'}
```

**计算交集**

例如，假设您有事件A和B中的参与者列表：

```r
a = set(["Jake", "John", "Eric"])
print(a)
b = set(["John", "Jill"])
print(b)
```

要找出哪些成员参加了这两个活动，您可以使用“交集”方法：

```r
a = set(["Jake", "John", "Eric"])
b = set(["John", "Jill"])

print(a.intersection(b))
print(b.intersection(a))
```

输出结果如下：

```r
{'John'}
{'John'}
```

**symmetric_difference**

要找出哪些成员只参加了其中一个事件，可以使用“symmetric_difference”方法：

```r
a = set(["Jake", "John", "Eric"])
b = set(["John", "Jill"])

print(a.symmetric_difference(b))
print(b.symmetric_difference(a))
```

输出结果如下：

```r
{'Eric', 'Jake', 'Jill'}
{'Eric', 'Jake', 'Jill'}
```

**计算差集**

要找出哪些成员只参加了一个事件而不是另一个事件，请使用“差集”方法：

```r
a = set(["Jake", "John", "Eric"])
b = set(["John", "Jill"])

print(a.difference(b))
print(b.difference(a))
```

输出结果如下：

```r
{'Eric', 'Jake'}
{'Jill'}
```

**计算并集**

要接收所有参与者的列表，请使用“union”方法：

```r
a = set(["Jake", "John", "Eric"])
b = set(["John", "Jill"])

print(a.union(b))
```

输出结果如下：

```r
{'John', 'Eric', 'Jake', 'Jill'}
```

## **练习**

在下面的练习中，使用给定的列表输出一个包含来自事件A但未参加事件B的所有参与者的集合。

给定列表：

```r
a = ["Jake", "John", "Eric"]
b = ["John", "Jill"]
```

修改完成参考：

```r
a = ["Jake", "John", "Eric"]
b = ["John", "Jill"]

A = set(a)
B = set(b)

print(A.difference(B))
```

输出结果：

```r
<script.py> output:
    {'Eric', 'Jake'}
```
