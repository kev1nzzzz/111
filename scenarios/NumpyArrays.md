# **数据科学教程**

## **Numpy Arrays**

Numpy数组是Python列表的绝佳替代品。Numpy数组的一些主要优点是它们快速，易于使用，并为用户提供了在整个数组上执行计算的机会。

### **创建Numpy数组**

首先创建两个Python列表。然后，您将导入numpy包并从新创建的列表中创建numpy数组。实例如下：

```r
# Create 2 new lists height and weight
height = [1.87,  1.87, 1.82, 1.91, 1.90, 1.85]
weight = [81.65, 97.52, 95.25, 92.98, 86.18, 88.45]

# Import the numpy package as np
import numpy as np

# Create 2 numpy arrays from height and weight
np_height = np.array(height)
np_weight = np.array(weight)
```

### **输出np_height的类型**

```r
print(type(np_height))
```

### **元素计算**

现在我们可以对高度和重量进行逐元素计算。例如，您可以采用上述所有6个高度和重量观测值，并使用单个方程计算每个观测值的BMI。这些操作非常快速且计算效率高。当数据中有1000个观察值时，它们特别有用。

```r
# Calculate bmi
bmi = np_weight / np_height ** 2

# Print the result
print(bmi)
```

### **子集**

Numpy阵列的另一个重要特性是子集的能力。例如，如果您想知道我们的BMI数组中的哪些观察结果高于23，我们可以快速对其进行分组以找出结果。

```r
# For a boolean response
bmi > 23

# Print only those observations above 23
bmi[bmi > 23]
```

## **练习**

首先，将权重列表从列表转换为Numpy数组。然后，将所有重量从千克转换为磅。使用每公斤2.2磅的标量转换来进行转换。最后，以磅为单位打印生成的权重数组。

**需要修改的代码**

```r
weight_kg = [81.65, 97.52, 95.25, 92.98, 86.18, 88.45]

import numpy as np

# Create a numpy array np_weight_kg from weight_kg
    

# Create np_weight_lbs from np_weight_kg

# Print out np_weight_lbs
```

**修改后的代码参考**

```r
weight_kg = [81.65, 97.52, 95.25, 92.98, 86.18, 88.45]

import numpy as np

# Create a numpy array np_weight_kg from weight_kg
np_weight_kg = np.array(weight_kg)

# Create np_weight_lbs from np_weight_kg
np_weight_lbs = np_weight_kg * 2.2

# Print out np_weight_lbs
print(np_weight_lbs)
```

**输出结果如下**

```r
<script.py> output:
    [ 179.63   214.544  209.55   204.556  189.596  194.59 ]
```

