# **数据科学教程**

## **Pandas基础知识**

Pandas是Python的一个大数据处理模块。Pandas使用一个二维的数据结构DataFrame来表示表格式的数据，相比较于Numpy，Pandas可以存储混合的数据结构，同时使用NaN来表示缺失的数据，而不用像Numpy一样要手工处理缺失的数据，并且Pandas使用轴标签来表示行和列。

它建立在Numpy包之上，其关键数据结构称为DataFrame。DataFrames允许您在观察行和变量列中存储和操作表格数据。

**DataFrame类**

DataFrame有四个重要的属性： 
index：行索引。 
columns：列索引。 
values：值的二维数组。 
name：名字。

### **创建Dataframe**

有几种方法可以创建DataFrame。一种方法是使用字典。例如：

```r
dict = {"country": ["Brazil", "Russia", "India", "China", "South Africa"],
       "capital": ["Brasilia", "Moscow", "New Dehli", "Beijing", "Pretoria"],
       "area": [8.516, 17.10, 3.286, 9.597, 1.221],
       "population": [200.4, 143.5, 1252, 1357, 52.98] }

import pandas as pd
brics = pd.DataFrame(dict)
print(brics)
```

正如您在新的bricsDataFrame中看到的那样，Pandas为每个国家/地区指定了一个键，数字值为0到4.如果您希望使用不同的索引值，例如两个字母的国家/地区代码，您也可以轻松地执行此操作。

```r
# Set the index for brics
brics.index = ["BR", "RU", "IN", "CH", "SA"]

# Print out brics with new index values
print(brics)
```

输出结果：

```r
<script.py> output:
          area    capital       country  population
    BR   8.516   Brasilia        Brazil      200.40
    RU  17.100     Moscow        Russia      143.50
    IN   3.286  New Dehli         India     1252.00
    CH   9.597    Beijing         China     1357.00
    SA   1.221   Pretoria  South Africa       52.98
```

创建DataFrame的另一种方法是使用Pandas导入csv文件。现在，cars.csv存储csv 并可以使用pd.read_csv以下方法导入：

```r
# Import pandas as pd
import pandas as pd

# Import the cars.csv data: cars
cars = pd.read_csv('cars.csv')

# Print out cars
print(cars)
```

输出结果：

```r
<script.py> output:
      Unnamed: 0  cars_per_cap        country drives_right
    0         US           809  United States         True
    1        AUS           731      Australia        False
    2        JAP           588          Japan        False
    3         IN            18          India        False
    4         RU           200         Russia         True
    5        MOR            70        Morocco         True
    6         EG            45          Egypt         True
```

### **索引DataFrames**

有几种方法可以索引Pandas DataFrame。最简单的方法之一是使用方括号表示法。

在下面的示例中，您可以使用方括号来选择carsDataFrame的一列。您可以使用单个支架或双支架。单支架输出Pandas系列，而双支架输出Pandas DataFrame。

```r
# Import pandas and cars.csv
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Print out country column as Pandas Series
print(cars['cars_per_cap'])

# Print out country column as Pandas DataFrame
print(cars[['cars_per_cap']])

# Print out DataFrame with country and drives_right columns
print(cars[['cars_per_cap', 'country']])
```

输出结果：

```r
<script.py> output:
    US     809
    AUS    731
    JAP    588
    IN      18
    RU     200
    MOR     70
    EG      45
    Name: cars_per_cap, dtype: int64
         cars_per_cap
    US            809
    AUS           731
    JAP           588
    IN             18
    RU            200
    MOR            70
    EG             45
         cars_per_cap        country
    US            809  United States
    AUS           731      Australia
    JAP           588          Japan
    IN             18          India
    RU            200         Russia
    MOR            70        Morocco
    EG             45          Egypt
```

方括号也可用于从DataFrame访问观察（行）。例如：

```r
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Print out first 4 observations
print(cars[0:4])

# Print out fifth, sixth, and seventh observation
print(cars[4:6])
```

输出结果如下：

```r
<script.py> output:
         cars_per_cap        country drives_right
    US            809  United States         True
    AUS           731      Australia        False
    JAP           588          Japan        False
    IN             18          India        False
         cars_per_cap  country drives_right
    RU            200   Russia         True
    MOR            70  Morocco         True
```

您还可以使用loc和iloc执行几乎任何数据选择操作。loc是基于标签的，这意味着您必须根据行和列标签指定行和列。iloc是基于整数索引的，因此您必须按其整数索引指定行和列，就像您在上一个练习中所做的那样。

实例如下：

```r
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Print out observation for Japan
print(cars.iloc[2])

# Print out observations for Australia and Egypt
print(cars.loc[['AUS', 'EG']])
```
