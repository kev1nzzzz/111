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

