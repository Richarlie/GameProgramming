# The Foundermantal Knowledges of JAVA
### "That is what I've learned"
## 一. 基础语法知识

### 1.输入输出
``` java
import java.util.Scanner;
Scanner scanner = new Scanner(System.in);
int kkk = scanner.NextInt();
```
学了面向对象的内容后，我才发现这其实就是先通过import引入一个scanner库，然后再新建一个scanner对象，接着要输入时就通过这个对象对应的类中的成员函数进行实现

### 2.形参实参
**形参**：函数中声明的参数（有副本的意味）
**实参**：方法调用传入的参数
**值传递**：直接传值，修改也是改变值而已
**引用传递**：直接传地址，修改后地址对应的数据也改了

## 二.面向对象
### 1.概念
**类**：对一类事物的抽象
**对象**：真实存在的事物

### 2.封装、继承、多态
| 名词 |意思|
|:--:|:--:|
|封装|对内隐藏细节，对外暴露接口|
|继承|子类继承父类的内容|
|多态|在继承的基础上有了多种表现形态|

- **继承**和**多态**的区别在于：**有无在子类中对父类的成员函数进行重写，并且通过父类引用调用该函数。**
- 1.子类继承 2.方法重写 3.父类调用
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
class Dog extends Animal {
    @Override  // 关键：重写了父类方法  
    public void makeSound() {
        System.out.println("汪汪汪");
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

>好似一般都会声明父类类型的变量，然后让其指向一个新建的子类对象，在调用时可以有巧思，非常牛的
``` java
abstract class Animal {
    // 在父类中定义通用行为
    public abstract void play();
    public abstract void groom();
}

class Cat extends Animal {
    @Override
    public void play() {
        scratchFurniture();  // 猫的玩耍方式
    }
    
    @Override 
    public void groom() {
        selfClean();         // 猫的美容方式
    }
    
    // 特有方法变成私有或受保护的
    private void scratchFurniture() {
        System.out.println("抓家具");
    }
    
    private void selfClean() {
        System.out.println("自我清洁");
    }
}

// 使用：不再需要类型转换！
Animal animal = new Cat();
animal.play();   // ✅ 输出"抓家具"
animal.groom();  // ✅ 输出"自我清洁"
```

### 3. 类
同一个文件夹中的多个类可以互相调用，但不能直接用（相当于图纸），要先实例化
**类里面只能有方法和属性，关于操作什么的只能写在方法中**

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1OTI1Njc0MjcsLTkxNTI3OTIwNywtMj
U0NzI3NDg1LC0xODY2NTI0OTA1LDMxNTk4NTg0MSwtMTY4Nzg1
NzIxOCwtMTA2Nzk1ODc0NCwtMTcwMzMwMzMxNF19
-->