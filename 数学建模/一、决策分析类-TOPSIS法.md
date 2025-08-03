# 一、决策分析类-TOPSIS法
## 情景
![输入图片说明](/imgs/2025-08-03/79ip87SVaPHioroI.png)
## 概念
- **TOPSIS**：逼近理想解排序法/优劣解距离法
- **理想解**：各备选方案中各项属性最好的方案
- **负理想解**：各备选方案中各项属性最坏的方案
![输入图片说明](/imgs/2025-08-03/cmnLZOwqI41KrgtE.png)
## 步骤
![输入图片说明](/imgs/2025-08-03/RVW6SD1kNBUuJ9Fk.png)
- **正向化**：将指标都变成一个“越大越好”的指标
-  **标准化**：将不同指标变成同一数量级
### 1.原始矩阵正向化
几种指标类别：
![输入图片说明](/imgs/2025-08-03/BEI5MuU5ASMZK2xc.png)
**原始矩阵正向化就是把后三种指标转化成第一种指标**
如何转化？：
![输入图片说明](/imgs/2025-08-03/oFYYwV0PEmqAl1Wj.png)
### 2.正向化矩阵标准化
![输入图片说明](/imgs/2025-08-03/IetQAfBLDO15wUa4.png)
**竖向标准化：**$\frac{元素}{此列元素平方和}$
### 3.计算得分 并 归一化
![输入图片说明](/imgs/2025-08-03/4Byaq0UVt0BUvU3t.png)
**最大值**：每一列取的最大值
**最小值**：每一列取的最小值
把max和min都求出来后，按行来求**理想解距离**和**负理想解距离**，公式跟求两点距离的一样，每一行的都归一化出来就能得到最终分数
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjExNDA2OTIsNjY0NTQ3MTM3LC0xOTkzMD
A4NzAxLC0xNzM4ODQ4MjU4LDE1Mjg1NDk5NTgsMTY4MTEzMjgz
Ml19
-->