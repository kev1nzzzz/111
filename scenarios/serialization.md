# **高级教程**

## **序列化(serialization)**

Python提供了内置的JSON库来编码和解码JSON。
在Python 2.5中，使用simplejson模块，而在Python 2.7中，使用json模块。由于这个解释器使用Python 2.7，我们将使用json。
要使用json模块，必须先导入它：

```r
import json
```

JSON数据有两种基本格式。在字符串或对象数据结构中。Python中的对象数据结构由彼此嵌套的列表和字典组成。对象数据结构允许使用python方法（用于列表和字典）来添加，列出，搜索和从数据结构中删除元素。String格式主要用于将数据传递到另一个程序或加载到数据结构中。

要将JSON加载回数据结构，请使用“loads”方法。此方法接受一个字符串并将其转回json对象数据结构：

```r
import json 
print(json.loads(json_string))
```

要将数据结构编码为JSON，请使用“dumps”方法。此方法接受一个对象并返回一个String：

```r
import json
json_string = json.dumps([1, 2, 3, "a", "b", "c"])
print(json_string)
```

输出结果：

```r
[1, 2, 3, "a", "b", "c"]
```

Python支持名为pickle的Python专有数据序列化方法（以及称为cPickle的更快的替代方法）。

您可以完全相同的方式使用它。

```r
import pickle
pickled_string = pickle.dumps([1, 2, 3, "a", "b", "c"])
print(pickle.loads(pickled_string))
```

输出结果：

```r
[1, 2, 3, 'a', 'b', 'c']
```

## **练习**

本练习的目的是输出带有键值对“Me”的JSON字符串：800添加到它。

原代码：

```r
import json

# fix this function, so it adds the given name
# and salary pair to salaries_json, and return it
def add_employee(salaries_json, name, salary):
    # Add your code here

    return salaries_json

# test code
salaries = '{"Alfred" : 300, "Jane" : 400 }'
new_salaries = add_employee(salaries, "Me", 800)
decoded_salaries = json.loads(new_salaries)
print(decoded_salaries["Alfred"])
print(decoded_salaries["Jane"])
print(decoded_salaries["Me"])
```

修改后代码参考：

```r
import json

# fix this function, so it adds the given name
# and salary pair to salaries_json, and return it
def add_employee(salaries_json, name, salary):
    salaries = json.loads(salaries_json)
    salaries[name] = salary

    return json.dumps(salaries)

# test code
salaries = '{"Alfred" : 300, "Jane" : 400 }'
new_salaries = add_employee(salaries, "Me", 800)
decoded_salaries = json.loads(new_salaries)
print(decoded_salaries["Alfred"])
print(decoded_salaries["Jane"])
print(decoded_salaries["Me"])
```

输出结果：

```r
<script.py> output:
    300
    400
    800
```
