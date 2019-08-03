# **高级教程**

## **列表生成器(List Comprehensions)**

List Comprehensions是一个非常强大的工具，它在一个可读行中基于另一个列表创建一个新列表。

例如，假设我们需要创建一个整数列表，它指定某个句子中每个单词的长度，但前提是该单词不是单词“the”。

正常表示如下：

```r
sentence = "the quick brown fox jumps over the lazy dog"
words = sentence.split()
word_lengths = []
for word in words:
      if word != "the":
          word_lengths.append(len(word))
print(words)
print(word_lengths)
```

输出结果如下：

```r
['the', 'quick', 'brown', 'fox', 'jumps', 'over', 'the', 'lazy', 'dog']
[5, 5, 3, 5, 4, 4, 3]
```

使用列表生成器，我们可以将此过程简化为此表示法：

```r
sentence = "the quick brown fox jumps over the lazy dog"
words = sentence.split()
word_lengths = [len(word) for word in words if word != "the"]
print(words)
print(word_lengths)
```

## **练习**

使用列表生成器，从列表“数字”中创建一个名为“newlist”的新列表，该列表仅包含列表中的正数，作为整数。

列表“数字”：

```r
numbers = [34.6, -203.4, 44.9, 68.3, -12.2, 44.6, 12.7]
newlist = []
print(newlist)
```

创建的新列表参考如下：

```r
numbers = [34.6, -203.4, 44.9, 68.3, -12.2, 44.6, 12.7]
newlist = [int(x) for x in numbers if x > 0]
print(newlist)
```

输出结果如下：

```r
<script.py> output:
    [34, 44, 68, 44, 12]
```
