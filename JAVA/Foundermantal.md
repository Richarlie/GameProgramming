# The Foundermantal Knowledges of Java
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

### 3.零碎知识点
a. 主函数：作为入口执行程序
``` Java
public static void main (String[]args){
}
```
b. “%d”这种叫做通配符
c. 一个文件中只能有一个由public修饰的类，还要与java文件同名
d. Java的浮点数默认为double类型，要float类型的话得在数据后面加"l"
e. Boolean类不参与类型转换
f. **关于数据类型转换**：容量小的自动转换为容量大的
g. **关于字符编码**：C——ASCII  Java——Unicode

## 二.面向对象
### 1.概念
**类**：对一类事物的抽象
**对象**：真实存在的事物
**成员变量**：类中的变量，有默认值——基本是0相关的（所以声明后可以不赋值）
**局部变量**：类中的方法中的变量，声明后必须要赋值

### 2.封装、继承、多态
| 名词 |意思|
|:--:|:--:|
|封装|对内隐藏细节，对外暴露接口|
|继承|子类继承父类的内容|
|多态|在继承的基础上有了多种表现形态|
#### 继承
目的是为了实现代码的复用
java中只支持单继承（一个子类只能对应一个父类），但C++中可以多继承
##### 父子类继承中构造方法的调用
在调用子类构造方法之前，必须先调用父类的构造方法（默认就会这样）
如果子类没有显式地调用父类构造方法，默认会自动调用父类空参构造方法
如果子类没有显式地调用父类构造方法，且用父类无空参构造方法，会报错
>super([参数列表])


- **继承**和**多态**的区别在于：**有无在子类中对父类的成员函数进行重写，并且通过父类引用调用子类对象。**
- 1.子类继承 
- 2.方法重写
- 3.父类调用
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
#### **基本原则**
同一个文件夹中的多个类可以互相调用，但不能直接用（相当于图纸），要先实例化
**类里面只能有方法和属性，关于操作什么的只能写在方法中**
**关于堆内存和栈内存**：一般栈内存存储变量（名字），堆内存存储值或对象。
所以只要是new出来的东西，就一定在堆内存中
#### **This引用**
在一个类的方法中，如果传入的参量和类的熟悉重名的话就使"用this"来区分
>比如传入的参数是name，类内部也有一个属性名叫做name，那么在方法里面“This.name”指的就是属性的那个name
#### **Java类与数据库的联系——ORMapping（）**
一个Java类对应一张表
一个Java对象对应表中一条记录
一个属性对应表中一个字段:)

### 4.属性私有化
**在类中，属性通常用private修饰**→**只能在类内部访问**
需要访问则需要对应的set()和get()方法实现：
>比如有一个类Person中的属性名为Name，
>要对其进行设定的话则需要调用Person.setName()
>要对其进行调出取值的话需要调用Person.getName()
>以此类推

|修饰符|类内部|同一个包(其他类)|(不同包)子类|任何地方|
|:--:|:--:|:--:|:--:|:--:|
|private|yes||||
|default|yes|yes|||
|protected|yes|yes|yes||
|public|yes|yes|yes|yes|

JDK里面的快捷键**Alt+Insert**选择**Generate**中的**Getter and Setter**就可以直接在类中针对属性生成对应的set()和get()函数

体现了面向对象程序设计的“封装”呗...

### 5.构造方法
1. **构造方法是用来实例化对象的**
2. **名字与类名相同**
3. **没有返回值，不用void关键字**
>你知道吗，实际上在类外new一个对象时，实际上就是调用构造方法来实例化，只不过如果你在类里面没有写明构造方法，那么它默认是个空的（但还是会存在的），如果在这个方法里面写上一些其他的代码，那么新建一个对象的同时也会执行这个代码——有点像游戏里面角色创建成功的声明有木有！

### 6.方法重载（Overload）
**一个类**中的多个方法，方法名相同但参数不同
>While in C,it is fobbidened;
>But in Java,it is permitted!
>So it appear as "Overload"'

构造方法亦可以拿来重载，用来实现复杂的需求
#### 另：方法重写(Overwrite)、方法覆写(Override)
子类可以根据自己需要，重新改写从父类继承的方法
重写后的方法名、参数、类型要与父类一致

### 7.包(Package)
1. **基本知识**
实际上就是文件夹
层层深入，用“.”划分层次
Such as:
> src.com.project.tset
**Package语句放在类的第一行，用来说明当前类是哪个包下的**
2. **关于Import**
同一个包下的类可直接使用，其他包下的类要用import语句才能调用
但是Java.lang包下的类可以不用Import就能调用

### 8.对象转型(Casting)
一个父类的引用可以指向子类的对象（**父类引用指向子类对象**）
若一个父类的引用指向子类对象，那么该对象不能再访问子类新增的成员——**可以想象子类是父类的extension**
若一个父类的引用指向了子类对象，叫做向上转型，反之叫做向下转型——范围越大越上级呗
#### 父类引用指向子类对象 (e.g.父类——Person，子类——Student)
>Person p = new Student();
这样子的话就没办法再访问子类新增的成员了（就是不能再用Student类中的school、id等属性了）

示意图：
>Student
>>Person
#### 向下转型
> Person p = new Student();
> Student s = (Student)p;

这就叫向下转型

### 9.Abstract关键字
用abstract修饰的类叫做抽象类，用abstract修饰的方法叫做抽象方法
若一个类中有一个抽象方法，那这个类就是抽象类
抽象类不能被实例化，只能被继承
抽象方法没有方法体，只有声明
抽象类的子类必须重写其继承的抽象方法
**“说白了这像一个声明而已，抽象在于它不具体，得被具体化”**
### 10.接口(Interface)
可以看成是一个特殊的抽象类
不能被实例化，只能被实现（类——继承，接口——实现）
**“感觉像是”**
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUzNzUzMzMzNSw3NTkxMDI5NjMsLTMxOT
YzNDQ3MiwxNTg3ODYzMTc1LDE1MTcyMTIwNzQsMTc5Nzk1MjE4
NCwtMTgwMzU0NTc4NiwxMTYxOTA0NDAyLC0yNDY3NzU1ODMsMj
E4MDgxMDY0LDU1NDAwMjkzMSwtNzE5MTQ3MTAsLTE3NDE2OTUx
NiwtOTE1Mjc5MjA3LC0yNTQ3Mjc0ODUsLTE4NjY1MjQ5MDUsMz
E1OTg1ODQxLC0xNjg3ODU3MjE4LC0xMDY3OTU4NzQ0LC0xNzAz
MzAzMzE0XX0=
-->