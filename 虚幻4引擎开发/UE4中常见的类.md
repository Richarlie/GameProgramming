# UE4中常见的类
引擎中创建蓝图类就需要选择基类，基类通常是常见的一些类
## 1. Actor系列
Actor：可以放在地图中的物体——普通物体
Pawn：可以被持有和接受信号控制的Actor——有信号的物体
Character：是可以走动的Pawn——角色、NPC等
层层继承：Actor→Pawn→Character

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI4MzAxNzk3NF19
-->