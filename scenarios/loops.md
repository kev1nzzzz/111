# **基础知识学习**

## **python中的循环语句**

python和c,c++类似，有两种类型的循环，分别是for和while。但是python中没有do while循环。

### **"for"循环**

for循环迭代给定的序列。这是一个例子：

```r
primes = [2, 3, 5, 7]
for prime in primes:
    print(prime)
```

输出结果为：

```r
2
3
5
7
```

For循环可以使用“range”和“xrange”函数迭代一系列数字。range和xrange之间的区别在于range函数返回一个包含指定范围数的新列表，而xrange返回一个更有效的迭代器。（Python 3使用范围函数，其作用类似于xrange）。请注意，范围函数基于零。

例子如下：

```r
# Prints out the numbers 0,1,2,3,4
for x in range(5):
    print(x)

# Prints out 3,4,5
for x in range(3, 6):
    print(x)

# Prints out 3,5,7
for x in range(3, 8, 2):
    print(x)
```

输出结果为：

```r
0
1
2
3
4
3
4
5
3
5
7
```

### **"while"循环"

while循环中会给定某个条件，在给定的判断条件为 true 时执行循环体，否则退出循环体。

例子如下：

```r
# Prints out 0,1,2,3,4

count = 0
while count < 5:
    print(count)
    count += 1  # This is the same as count = count + 1
```

输出结果如下：

```r
0
1
2
3
4
```

### **"break"&"continue"**

在python中，break用于退出for循环或while循环，而continue用于跳过当前块，并返回“for”或“while”语句。如下所示：

```r
# Prints out 0,1,2,3,4

count = 0
while True:
    print(count)
    count += 1
    if count >= 5:
        break

# Prints out only odd numbers - 1,3,5,7,9
for x in range(10):
    # Check if x is even
    if x % 2 == 0:
        continue
    print(x)
```

输出结果如下：

```r
0
1
2
3
4
1
3
5
7
9
```

可以看出前一个语句(1-8行)，即输出每次count的值后执行+1操作，直到count>=5则退出循环；而后面一部分语句则表示如果x是偶数，则跳过，重新执行循环。即输出奇数部分。

**可以使用"else"子句进行循环吗**

与C，CPP等语言不同，我们可以使用else for循环。当“for”或“while”语句的循环条件失败时，执行“else”中的代码部分。如果在for循环内执行break语句，则跳过“else”部分。请注意，即使存在continue语句，也会执行“else”部分。

这里有一些例子：

```r
# Prints out 0,1,2,3,4 and then it prints "count value reached 5"

count=0
while(count<5):
    print(count)
    count +=1
else:
    print("count value reached %d" %(count))

# Prints out 1,2,3,4
for i in range(1, 10):
    if(i%5==0):
        break
    print(i)
else:
    print("this is not printed because for loop is terminated because of break but not due to fail in condition")
```

输出结果如下：

```r
0
1
2
3
4
count value reached 5
1
2
3
4
```

## **练习**

按照收到的顺序循环并输出数字列表中的所有偶数。不要输出序列中237之后的任何数字。	

列表如下：

```r
numbers = [
    951, 402, 984, 651, 360, 69, 408, 319, 601, 485, 980, 507, 725, 547, 544,
    615, 83, 165, 141, 501, 263, 617, 865, 575, 219, 390, 984, 592, 236, 105, 942, 941,
    386, 462, 47, 418, 907, 344, 236, 375, 823, 566, 597, 978, 328, 615, 953, 345,
    399, 162, 758, 219, 918, 237, 412, 566, 826, 248, 866, 950, 626, 949, 687, 217,
    815, 67, 104, 58, 512, 24, 892, 894, 767, 553, 81, 379, 843, 831, 445, 742, 717,
    958, 609, 842, 451, 688, 753, 854, 685, 93, 857, 440, 380, 126, 721, 328, 753, 470,
    743, 527
]
```

修改后的参考：

```r
numbers = [
    951, 402, 984, 651, 360, 69, 408, 319, 601, 485, 980, 507, 725, 547, 544,
    615, 83, 165, 141, 501, 263, 617, 865, 575, 219, 390, 984, 592, 236, 105, 942, 941,
    386, 462, 47, 418, 907, 344, 236, 375, 823, 566, 597, 978, 328, 615, 953, 345,
    399, 162, 758, 219, 918, 237, 412, 566, 826, 248, 866, 950, 626, 949, 687, 217,
    815, 67, 104, 58, 512, 24, 892, 894, 767, 553, 81, 379, 843, 831, 445, 742, 717,
    958, 609, 842, 451, 688, 753, 854, 685, 93, 857, 440, 380, 126, 721, 328, 753, 470,
    743, 527
]

# your code goes here
for number in numbers:
    if number == 237:
        break

    if number % 2 == 1:
        continue

    print(number)
```

输出结果如下：

```r
<script.py> output:
    402
    984
    360
    408
    980
    544
    390
    984
    592
    236
    942
    386
    462
    418
    344
    236
    566
    978
    328
    162
    758
    918
```

这里用到break语句，当数字达到237时跳出循环；用continue语句，当数字是奇数时，跳过语句块，重新执行循环语句。

