# **高级教程**

## **多函数参数(Multiple Function Arguments)**

如果正常声明，Python中的每个函数都会收到预定义数量的参数，如下所示：

```r
def myfunction(first, second, third):
    # do something with the 3 variables
    ...
```

可以使用以下语法声明接收可变数量参数的函数：

```r
def foo(first, second, third, *therest):
    print("First: %s" % first)
    print("Second: %s" % second)
    print("Third: %s" % third)
    print("And all the rest... %s" % list(therest))
```

“therest”变量是一个变量列表，它接收在前3个参数之后赋予“foo”函数的所有参数。所以foo(1,2,3,4,5)会输出出来：

```r
def foo(first, second, third, *therest):
    print("First: %s" %(first))
    print("Second: %s" %(second))
    print("Third: %s" %(third))
    print("And all the rest... %s" %(list(therest)))

foo(1,2,3,4,5)
```

也可以通过关键字发送函数参数，以便参数的顺序无关紧要，使用以下语法。以下代码生成以下输出： The sum is: 6 Result: 1

```r
def bar(first, second, third, **options):
    if options.get("action") == "sum":
        print("The sum is: %d" %(first + second + third))

    if options.get("number") == "first":
        return first

result = bar(1, 2, 3, action = "sum", number = "first")
print("Result: %d" %(result))
```

“bar”函数接收3个参数。如果收到一个额外参数，并且它指示总结数字，则输出总和。或者，如果传递给函数的“number”参数的值等于“first”，则函数也知道它必须返回第一个参数。

## **练习**

填写foo和bar函数，以便它们可以接收可变数量的参数（3个或更多），foo函数必须返回接收的额外参数数量。如果关键字magicNumber的参数值为7，则必须返回true，否则返回false。

原代码如下：

```r
# edit the functions prototype and implementation
def foo(a, b, c):
    pass

def bar(a, b, c):
    pass


# test code
if foo(1,2,3,4) == 1:
    print("Good.")
if foo(1,2,3,4,5) == 2:
    print("Better.")
if bar(1,2,3,magicnumber = 6) == False:
    print("Great.")
if bar(1,2,3,magicnumber = 7) == True:
    print("Awesome!")
```

修改完代码如下：

```r
# edit the functions prototype and implementation
def foo(a, b, c, *args):
    return len(args)

def bar(a, b, c, **kwargs):
    return kwargs["magicnumber"] == 7


# test code
if foo(1,2,3,4) == 1:
    print("Good.")
if foo(1,2,3,4,5) == 2:
    print("Better.")
if bar(1,2,3,magicnumber = 6) == False:
    print("Great.")
if bar(1,2,3,magicnumber = 7) == True:
    print("Awesome!")
```

输出结果：

```r
<script.py> output:
    Good.
    Better.
    Great.
    Awesome!
```
