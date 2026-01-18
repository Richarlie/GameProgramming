# UE4中常见的类
引擎中创建蓝图类就需要选择基类，基类通常是常见的一些类
## 1.  Actor系列
Actor：可以放在地图中的物体——普通物体
Pawn：可以被持有和接受信号控制的Actor——有信号的物体
Character：是可以走动的Pawn——角色、NPC等
层层继承：Actor→Pawn→Character
## 2. Controller系列
没有物理表现的Actor,可以控制一个Pawn
子类1-PlayerController：控制玩家角色
子类2-AIController：控制PC

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NzM0Nzc1NTVdfQ==
-->