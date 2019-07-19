# **基础知识学习**

## **基本字符串操作**

字符串是文本的一部分。它们可以定义为引号之间的任何内容，如下所示：

```r
astring = "Hello world!"
astring2 = 'Hello world!'
```

如大家所见，您学到的第一件事就是输出一个简单的句子。这句话由Python存储为字符串。但是，我们不会立即输出字符串，而是会探索您可以对它们执行的各种操作。您还可以使用单引号分配字符串。但是，如果要分配的值本身包含单引号，则会遇到问题。例如，要在这些括号中指定字符串（单引号为''），您需要使用双引号，如下所示：

### **输出字符串长度**
```r
astring = "Hello world!"
print("single quotes are ' '")

print(len(astring))
```

结果如下：

```r
single quotes are ' '
12
```

结果为12，因为“Hello world！” 长度为12个字符，包括标点符号和空格。

### **输出字符串某个字符的位置**

请看下面的例子：

```r
astring = "Hello world!"
print(astring.index("o"))
```

显示结果如下：

```r
4
```

输出值为4，因为第一次出现的字母“o”的位置是第一个字符的4个字符。注意短语中实际上有两个o - 这个方法只识别第一个。

那么为什么输出结果不是5？字符串中的第五个字符不是“o”吗？那是因为为了使事情变得更简单，Python（以及大多数其他编程语言）从0开始而不是1.所以“o”的索引是4。

### **输出字符串字符数量**
请大家再看一个例子：

```r
astring = "Hello world!"
print(astring.count("l"))
```

输出结果如下：

```r
3
```

该代码计算字符串中l的数量。因此，它应该输出3。

### **输出一串固定长度的字符串**

请看下面的例子：

```r
astring = "Hello world!"
print(astring[3:7])
```

这会输出一串字符串，从索引3开始，到索引6结束。但为什么6而不是7？同样，大多数编程语言都这样做 - 它使得在这些括号内的数学更容易。

如果括号中只有一个数字，它将为您提供该索引处的单个字符。如果省略第一个数字但保留冒号，它将输出从开头到你留下的数字的一串字符串。如果省略第二个数字，它将会输出从第一个数字到索引处的字符串。

你甚至可以在括号内加上负数。它们是一种简单的方法，从字符串的末尾开始，而不是从头开始。这样，-3表示“从最后开始的第3个字符”。

请大家看下面的例子：

```r
astring = "Hello world!"
print(astring[3:7:2])
```

输出结果为：

```r
l 
```

这将输出一个字符从3到7的字符串跳过一个字符。这是扩展字符串语法。一般形式是[start：stop：step]。

### **反转字符串**

实例如下：

```r
astring = "Hello world!"
print(astring[::-1])
```

输出结果如下：

```r
!dlrow olleH
```

### **转换字母大小写**

使用upper()和lower()函数实现将字符串转换成大写和小写形式。

如下所示：

```r
astring = "Hello world!"
print(astring.upper())
print(astring.lower())
```

输出结果如下：

```r
HELLO WORLD!
hello world!
```

字符串还有很多其他的操作，比如可以确定字符串是以某事开头还是以某事结束。返回true或false.

如下所示：

```r
astring = "Hello world!"
print(astring.startswith("Hello"))
print(astring.endswith("asdfasdfasdf"))
```

输出结果如下：

```r
True
False
```

第一个将打印True，因为字符串以“Hello”开头。第二个将打印False，因为字符串肯定不会以“asdfasdfasdf”结尾。


再比如可以将字符串拆分为一组在列表中组合在一起的字符串。如下所示：

```r
astring = "Hello world!"
afewwords = astring.split(" ")
```

由于此示例在空格处分割，因此列表中的第一项将为“Hello”，第二项将为“world！”。

## **练习**

尝试通过更改字符串来修复代码以打印出正确的信息。

需要修改的代码如下：

```r
s = "Hey there! what should this string be?"
# Length should be 20
print("Length of s = %d" % len(s))

# First occurrence of "a" should be at index 8
print("The first occurrence of the letter a = %d" % s.index("a"))

# Number of a's should be 2
print("a occurs %d times" % s.count("a"))

# Slicing the string into bits
print("The first five characters are '%s'" % s[:5]) # Start to 5
print("The next five characters are '%s'" % s[5:10]) # 5 to 10
print("The thirteenth character is '%s'" % s[12]) # Just number 12
print("The characters with odd index are '%s'" %s[1::2]) #(0-based indexing)
print("The last five characters are '%s'" % s[-5:]) # 5th-from-last to end

# Convert everything to uppercase
print("String in uppercase: %s" % s.upper())

# Convert everything to lowercase
print("String in lowercase: %s" % s.lower())

# Check how a string starts
if s.startswith("Str"):
    print("String starts with 'Str'. Good!")

# Check how a string ends
if s.endswith("ome!"):
    print("String ends with 'ome!'. Good!")

# Split the string into three separate strings,
# each containing only a word
print("Split the words of the string: %s" % s.split(" "))
```

修改后参考代码为：

```r
s = "Strings are awesome!"
# Length should be 20
print("Length of s = %d" % len(s))

# First occurrence of "a" should be at index 8
print("The first occurrence of the letter a = %d" % s.index("a"))

# Number of a's should be 2
print("a occurs %d times" % s.count("a"))

# Slicing the string into bits
print("The first five characters are '%s'" % s[:5]) # Start to 5
print("The next five characters are '%s'" % s[5:10]) # 5 to 10
print("The thirteenth character is '%s'" % s[12]) # Just number 12
print("The characters with odd index are '%s'" %s[1::2]) #(0-based indexing)
print("The last five characters are '%s'" % s[-5:]) # 5th-from-last to end

# Convert everything to uppercase
print("String in uppercase: %s" % s.upper())

# Convert everything to lowercase
print("String in lowercase: %s" % s.lower())

# Check how a string starts
if s.startswith("Str"):
    print("String starts with 'Str'. Good!")

# Check how a string ends
if s.endswith("ome!"):
    print("String ends with 'ome!'. Good!")

# Split the string into three separate strings,
# each containing only a word
print("Split the words of the string: %s" % s.split(" "))
```

输出正确结果为：

```r
<script.py> output:
    Length of s = 20
    The first occurrence of the letter a = 8
    a occurs 2 times
    The first five characters are 'Strin'
    The next five characters are 'gs ar'
    The thirteenth character is 'a'
    The characters with odd index are 'tig r wsm!'
    The last five characters are 'some!'
    String in uppercase: STRINGS ARE AWESOME!
    String in lowercase: strings are awesome!
    String starts with 'Str'. Good!
    String ends with 'ome!'. Good!
    Split the words of the string: ['Strings', 'are', 'awesome!']
```

即s的长度应该为20.








