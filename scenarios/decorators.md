# **高级教程**

## **函数装饰器(Decorators)**

装饰器(Decorators)是 Python 的一个重要部分。简单地说：他们是修改其他函数的功能的函数。他们有助于让我们的代码更简短，也更Pythonic（Python范儿）。

它的语法是：

```r
@decorator
def functions(arg):
    return "value"
```

这相当于：

```r
def function(arg):
    return "value"
function = decorator(function) # this passes the function to the decorator, and reassigns it to the functions

正如您可能已经看到的那样，装饰器只是另一个函数，它接受一个函数并返回一个函数。例如，你可以这样做：

def repeater(old_function):
    def new_function(*args, **kwds): # See learnpython.org/page/Multiple%20Function%20Arguments for how *args and **kwds works
        old_function(*args, **kwds) # we run the old function
        old_function(*args, **kwds) # we do it twice
    return new_function # we have to return the new_function, or it wouldn't reassign it to the value
	
这将使函数重复两次。
	
```r
>>> @repeater
def multiply(num1, num2):
    print(num1 * num2)

>>> multiply(2, 3)
6
6
```

您也可以更改输出.

```r
def double_out(old_function):
    def new_function(*args, **kwds):
        return 2 * old_function(*args, **kwds) # modify the return value
    return new_function
```

也可以改变输入：

```r
def double_Ii(old_function):
    def new_function(arg): # only works if the old function has one argument
        return old_function(arg * 2) # modify the argument passed
    return new_function
```

并做检查:

```r
def check(old_function):
    def new_function(arg):
        if arg < 0: raise (ValueError, "Negative Argument") # This causes an error, which is better than it doing the wrong thing
        old_function(arg)
    return new_function
```

假设您想将输出乘以可变量。您可以定义装饰器并按如下方式使用它：

```r
def multiply(multiplier):
    def multiply_generator(old_function):
        def new_function(*args, **kwds):
            return multiplier * old_function(*args, **kwds)
        return new_function
    return multiply_generator # it returns the new generator

# Usage
@multiply(3) # multiply is not a generator, but multiply(3) is
def return_num(num):
    return num

# Now return_num is decorated and reassigned into itself
return_num(5) # should return 15
```

输出结果：

```r
Out[1]: 15
```

## **练习**

制作一个decorator factory，它返回一个用一个参数装饰函数的装饰器。decorator factory应该接受一个参数，一个类型，然后返回一个装饰器，使函数检查输入是否是正确的类型。如果它是错误的，它应该输出（“Bad Type”）（实际上，它应该引发错误，但是本教程中没有提高错误）。看看教程代码和预期输出，看看它是什么，如果你感到困惑,使用isinstance（object，type_of_object）或类型（对象）可能有所帮助。

script.py:

```r
def type_check(correct_type):
    #put code here

@type_check(int)
def times2(num):
    return num*2

print(times2(2))
times2('Not A Number')

@type_check(str)
def first_letter(word):
    return word[0]

print(first_letter('Hello World'))
first_letter(['Not', 'A', 'String'])
```

solution.py:

```r
def type_check(correct_type):
    def check(old_function):
        def new_function(arg):
            if (isinstance(arg, correct_type)):
                return old_function(arg)
            else:
                print("Bad Type")
        return new_function
    return check

@type_check(int)
def times2(num):
    return num*2

print(times2(2))
times2('Not A Number')

@type_check(str)
def first_letter(word):
    return word[0]

print(first_letter('Hello World'))
first_letter(['Not', 'A', 'String'])
```

输出结果：

```r
<script.py> output:
    4
    Bad Type
    H
    Bad Type
```
