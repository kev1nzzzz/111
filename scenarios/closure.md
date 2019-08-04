# **高级教程**

## **闭包(Closure)**

Closure是一个函数对象，它记住封闭范围中的值，即使它们不在内存中也是如此。

首先，嵌套函数是在另一个函数内定义的函数。请注意，嵌套函数可以访问封闭范围的变量，这一点非常重要。但是，至少在python中，它们只是readonly。但是，可以使用“nonlocal”关键字明确地使用这些变量来修改它们。

例如：

```r
def transmit_to_space(message):
    "This is the enclosing function"
    def data_transmitter():
        "The nested function"
        print(message)

    data_transmitter()

print(transmit_to_space("Test message"))
```

输出结果：

```r
Test message
None
```

这很有效，因为'data_transmitter'函数可以访问'message'。要演示“非本地”关键字的使用，请考虑这一点.

```r
def print_msg(number):
    def printer():
        "Here we are using the nonlocal keyword"
        nonlocal number
        number=3
        print(number)
    printer()
    print(number)

print_msg(9)
```

输出结果：

```r
3
3
```

如果没有nonlocal关键字，输出将是“3 9”，但是，使用它时，我们得到“3 3”，即“number”变量的值被修改。

现在，我们如何返回函数对象而不是调用嵌套函数。（请记住，即使是函数也是对象.）

```r
def transmit_to_space(message):
    "This is the enclosing function"
    def data_transmitter():
        "The nested function"
        print(message)
    return data_transmitter
```

我们将函数调用如下：

```r
def transmit_to_space(message):
  "This is the enclosing function"
  def data_transmitter():
      "The nested function"
      print(message)
  return data_transmitter

fun2 = transmit_to_space("Burn the Sun!")
fun2()
```

输出结果：

```r
Burn the Sun!
```

即使完成了“transmit_to_space（）”的执行，该消息也得到了保留。即使在其他原始函数结束之后，数据附加到某些代码的这种技术在python中称为闭包。

优点：闭包可以避免使用全局变量并提供某种形式的数据隐藏。（例如，当类中的方法很少时，请使用闭包）。

此外，Python中的装饰器广泛使用闭包。

## **练习**

创建一个嵌套循环和一个python闭包，使函数可以使用闭包获得多个乘法函数。那就是使用闭包，可以使用闭包来创建multiply_with_5（）或multiply_with_4（）函数。

```r
# your code goes here

multiplywith5 = multiplier_of(5)
multiplywith5(9)
```

代码参考：

```r
def multiplier_of(n):
    def multiplier(number):
        return number*n
    return multiplier

multiplywith5 = multiplier_of(5)
print(multiplywith5(9))
```

输出结果：

```r
<script.py> output:
    45
```
