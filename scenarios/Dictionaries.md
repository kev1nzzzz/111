# **基础知识学习**

## **字典(Dictionary)**

字典是一种类似于数组的数据类型，可存储任意类型对象。但它使用键和值而不是索引。存储在字典中的每个值都可以使用键访问，键是任何类型的对象（字符串，数字，列表等），而不是使用其索引来解决它。

例如，可以使用如下字典存储电话号码数据库：

```r
phonebook = {}
phonebook["John"] = 938477566
phonebook["Jack"] = 938377264
phonebook["Jill"] = 947662781
print(phonebook)
```

输出结果如下：

```r
{'Jill': 947662781, 'John': 938477566, 'Jack': 938377264}
```

或者，可以使用以下表示法使用相同的值初始化字典：

```r
phonebook = {
    "John" : 938477566,
    "Jack" : 938377264,
    "Jill" : 947662781
}
print(phonebook)
```

输出结果如下：

```r
{'Jill': 947662781, 'John': 938477566, 'Jack': 938377264}
```

### **迭代字典**

字典可以迭代，就像列表一样。但是，与列表不同，字典不会保留存储在其中的值的顺序。要迭代键值对，请使用以下语法：

```r
phonebook = {"John" : 938477566,"Jack" : 938377264,"Jill" : 947662781}
for name, number in phonebook.items():
    print("Phone number of %s is %d" % (name, number))
```

输出结果如下：

```r
Phone number of Jill is 947662781
Phone number of John is 938477566
Phone number of Jack is 938377264
```

### **删除值**

要删除指定的索引，请使用以下其中一种表示法：

```r
phonebook = {
   "John" : 938477566,
   "Jack" : 938377264,
   "Jill" : 947662781
}
del phonebook["John"]
print(phonebook)
```

输出结果如下：

```r
{'Jill': 947662781, 'Jack': 938377264}
```

还有一种表示法是：

```r
phonebook = {
   "John" : 938477566,
   "Jack" : 938377264,
   "Jill" : 947662781
}
phonebook.pop("John")
print(phonebook)
```

输出结果如下：

```r
{'Jill': 947662781, 'Jack': 938377264}
```

## **练习**

将“Jake”添加到电话簿中，电话号码为938273443，然后从电话簿中删除Jill。

需要修改的代码如下：

```r
phonebook = {
    "John" : 938477566,
    "Jack" : 938377264,
    "Jill" : 947662781
}

# write your code here


# testing code
if "Jake" in phonebook:
    print("Jake is listed in the phonebook.")
if "Jill" not in phonebook:
    print("Jill is not listed in the phonebook.")
```

修改之后如下所示：

```r
phonebook = {
    "John" : 938477566,
    "Jack" : 938377264,
    "Jill" : 947662781
}

# write your code here
phonebook["Jake"] = 938273443
del phonebook["Jill"]

# testing code
if "Jake" in phonebook:
    print("Jake is listed in the phonebook.")
if "Jill" not in phonebook:
    print("Jill is not listed in the phonebook.")
```

输出结果如下：

```r
<script.py> output:
    Jake is listed in the phonebook.
    Jill is not listed in the phonebook.
```