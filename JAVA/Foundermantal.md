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
- **继承**：
``` java
class Animal {
    public void makeSound() {
        System.out.println("动物发出声音");
    }
}

class Cat extends Animal {
    // 没有重写makeSound方法，直接继承父类的实现
}

public class Test {
    public static void main(String[] args) {
        Animal myCat = new Cat();  // 向上转型
        myCat.makeSound(); // 输出："动物发出声音"
        // 这里没有多态，因为调用的始终是Animal类的makeSound方法
    }
}
```
- **多态**：
``` java
class Animal {
    public void makeSound() {
        System.out.println("动物发出声音");
    }
}

class Cat extends Animal {
    @Override  // 关键：重写了父类方法
    public void makeSound() {
        System.out.println("喵喵喵");
    }
}

public class Test {
    public static void letAnimalSound(Animal animal) {
        animal.makeSound(); // 多态发生在这里！
    }
    
    public static void main(String[] args) {
        letAnimalSound(new Cat()); // 输出："喵喵喵"
        letAnimalSound(new Dog()); // 输出："汪汪汪"
        // 同一个调用，不同结果 - 这就是多态！
    }
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1ODg4NjQ4MTMsLTE2ODc4NTcyMTgsLT
EwNjc5NTg3NDQsLTE3MDMzMDMzMTRdfQ==
-->