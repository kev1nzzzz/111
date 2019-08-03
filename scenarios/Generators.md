# **高级教程**

## **生成器(Generators)**

**什么是generator？**

generator是一种特殊的函数，和一般的函数不同，一般的函数调用一次，总会结束返回；generator却可以执行到某个位置停住，通过yield让出执行权，下次再调用时，从上一次yield后面的地方开始执行。

当使用for语句开始对一组项目的迭代时，将运行generator。一旦generator函数代码达到“yield”语句，生成器就会将其执行返回到for循环，从集合中返回一个新值。生成器函数可以生成任意数量的值（可能是无限的），从而产生每个值。

下面是一个generator函数的简单实例，它返回7个随机整数：

```r
import random

def lottery():
    # returns 6 numbers between 1 and 40
    for i in range(6):
        yield random.randint(1, 40)

    # returns a 7th number between 1 and 15
    yield random.randint(1,15)

for random_number in lottery():
       print("And the next number is... %d!" %(random_number))
```

输出结果如下：

```r
And the next number is... 36!
And the next number is... 39!
And the next number is... 40!
And the next number is... 16!
And the next number is... 40!
And the next number is... 27!
And the next number is... 10!
```

此函数决定如何自己生成随机数，并一次执行一个yield语句，暂停之间以将执行返回到main for循环。

**generator函数和普通函数的区别**

1.generator函数包含一个以上的yield声明.
2.generator函数被调用的时候，会返回一个iterator对象，但是函数并不会立即开始执行.
3.__iter__()和__next__()方法被自动实现，所以可以使用next()函数对返回的此iterator对象进行迭代.
4.一旦一个generator 执行到yield语句，generator函数暂停，程序控制流被转移到调用方.
5.在对generator的连续调用之间，generator的本地变量和状态会被保存.
6.最终，generator函数终止，再调用generator会引发StopIteration异常.

## **练习**

编写一个返回Fibonacci系列的生成函数。它们使用以下公式计算：系列的前两个数字始终等于1，并且返回的每个连续数字是最后两个数字的总和。提示：在generator函数中只能使用两个变量吗？请记住，分配可以同时完成。

下面的代码将同时切换a和b的值：

```r
a = 1
b = 2
a, b = b, a
print(a,b)
```

需要修改的代码如下：

```r
# fill in this function
def fib():
    pass #this is a null statement which does nothing when executed, useful as a placeholder.

# testing code
import types
if type(fib()) == types.GeneratorType:
    print("Good, The fib function is a generator.")

    counter = 0
    for n in fib():
        print(n)
        counter += 1
        if counter == 10:
            break
```

修改参考结果如下：

```r
# fill in this function
def fib():
    a, b = 1, 1
    while 1:
        yield a
        a, b = b, a + b

# testing code
import types
if type(fib()) == types.GeneratorType:
    print("Good, The fib function is a generator.")

    counter = 0
    for n in fib():
        print(n)
        counter += 1
        if counter == 10:
            break
```

输出结果：

```r
<script.py> output:
    Good, The fib function is a generator.
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55
```
