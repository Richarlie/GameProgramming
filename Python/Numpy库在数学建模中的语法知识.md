# Numpy库在数学建模中的语法知识
1. **tile函数**：
在 Python 的 NumPy 库中，  np.tile   函数用于将输入数组沿指定的轴重复指定次数，从而构造一个新的数组
``` python
numpy.tile(A, reps)
```
>**A**：输入数组，可以是列表、元组或 NumPy 数组。 **reps**：表示重复次数的整数或整数元组。
>如果是一个整数，则表示沿第一个轴重复该次数；
>如果是元组，则表示沿每个轴的重复次数。
>ps:
>对于二维数组
>轴0：表示行——从上到下
>轴1：表示列——从左到右
>对于三维数组
>轴 0：表示深度（或层数）
> 轴 1：表示行——从上到下
> 轴 2：表示列——从左到右

**例**：
①一维数组（单轴）：
``` python
import numpy as np
# 一维数组
a = np.array([1, 2, 3])
b = np.tile(a, 3)  # 沿第一个轴重复 3 次
print(b)
```
>输出结果：[1 2 3 1 2 3 1 2 3]

②二维数组（单轴）：
``` python
import numpy as np
# 二维数组
a = np.array([[1, 2], [3, 4]])
b = np.tile(a, 2)  # 沿第一个轴重复 2 次
print(b)
```
>输出结果：
>[[1 2 1 2]
 [3 4 3 4]]

③二维数组（多轴）：
```python

```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMTM1MjIxNzYsMTI0NzEwNTQ1MiwtOT
AxNzE1ODExLC03MDM2MDk3NDJdfQ==
-->