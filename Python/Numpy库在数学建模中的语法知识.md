# Numpy库在数学建模中的语法知识
1. **tile函数**：
在 Python 的 NumPy 库中，  np.tile   函数用于将输入数组沿指定的轴重复指定次数，从而构造一个新的数组
``` python
numpy.tile(A, reps)
```
>**A**：输入数组，可以是列表、元组或 NumPy 数组。 **reps**：表示重复次数的整数或整数元组。
>如果是一个整数，则表示沿第一个轴重复该次数；
>如果是元组，则表示沿每个轴的重复次数。

**例**：
①一维数组：
``` python
import numpy as np
# 一维数组
a = np.array([1, 2, 3])
b = np.tile(a, 3)  # 沿第一个轴重复 3 次
print(b)
```
>输出结果：[1 2 3 1 2 3 1 2 3]

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUxNTkxMDI1OSwtNzAzNjA5NzQyXX0=
-->