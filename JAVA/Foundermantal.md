# The Foundermantal Knowledges of JAVA
### "That is what I've learned"
## 一. 基础语法知识

### 1.输入输出
``` java
import java.util.Scanner;
Scanner scanner = new Scanner(System.in);
int kkk = scanner.NextInt();
```
> 学了面向对象的内容后，我才发现这其实就是先通过import引入一个scanner库，然后再新建一个scanner对象，接着要输入时就通过这个对象对应的类中的成员函数进行实现

## 二.面向对象
### 1.基本内容
| 名词 |意思|
|:--:|:--:|
|封装|对内隐藏细节，对外暴露接口|
|继承|子类继承父类的内容|
|多态|在继承的基础上有了多种表现形态|
```java
// 继承：Cat "是"一种 Animal
class Animal {
    String name;
    public void eat() { System.out.println("吃东西"); }
}

class Cat extends Animal { 
    // Cat 自动拥有了 name 属性和 eat() 方法
    // 这是继承带来的代码复用
}
```
- **继承**和多态的区别在于：

<!--stackedit_data:
eyJoaXN0b3J5IjpbOTEzNDM1Nzk0LC0xNjg3ODU3MjE4LC0xMD
Y3OTU4NzQ0LC0xNzAzMzAzMzE0XX0=
-->