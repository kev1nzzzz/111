# **高级教程**

## **偏函数(partial function)**

您可以使用functools库中的partial函数在python中创建偏函数。
偏函数允许将具有x参数的函数导出到具有较少参数的函数，并且为更有限的函数设置固定值。

需要输入：

```r
from functools import partial
```

请看下面的例子：

```r
from functools import partial

def multiply(x,y):
        return x * y

# create a new function that multiplies by 2
dbl = partial(multiply,2)
print(dbl(4))
```

输出结果：

```r
8
```

重要提示：默认值将从左侧开始替换变量。2将取代x。当调用dbl（4）时，y将等于4。它在这个例子中没有什么区别，但它在下面的例子中有所不同。

## **练习**

通过调用partial（）编辑函数并替换func（）中的前三个变量。然后使用新的偏函数仅使用一个输入变量进行输出，以使输出等于60。

需要修改的代码：

```r
#Following is the exercise, function provided:
from functools import partial
def func(u,v,w,x):
    return u*4 + v*3 + w*2 + x
#Enter your code here to create and print with your partial function
```

完成的代码参考：

```r
from functools import partial
def func(u,v,w,x):
    return u*4 + v*3 + w*2 + x

p = partial(func,5,6,7)
print(p(8))
```

输出结果：

```r
<script.py> output:
    60
```
