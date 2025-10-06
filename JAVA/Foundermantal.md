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

- **继承**和**多态**的区别在于：**有无在子类中对父类的成员函数进行重写，并且通过父类引用调用该函数。**
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ0NDYzMDE0MCwtMTY4Nzg1NzIxOCwtMT
A2Nzk1ODc0NCwtMTcwMzMwMzMxNF19
-->