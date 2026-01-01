# Richarlie的Java期末复习笔记
## 一、Java语言概述
### 1. Java技术体系和Java平台
#### · 平台
1. Java SE（Standard Edition）
2. Java EE（Enterprise Edition）
3. Java ME（Micro Edition）
### 2. Java开发环境
集成开发环境 (IDE, Integrated Development Environment)
<br>
## 二、Java语言基础
### 1. Java Application结构 & 源程序结构
![Java Application基本结构](/imgs/2026-01-01/WfWrfPlcFYfVSXCt.png)
![源程序结构](/imgs/2026-01-01/pmKWUpfFmGrGmJiU.png)
### 2. Java语法的一些要点
#### 1. main方法
``` java
public static main(String[] args)
```
#### 2. 骆驼命名法 (camel case)
类名通常以大写字母开头的名词。若名字由多个单词组成，每个单词的第一个字母都应大写。  例如：**FirstApp**、**FileInputStream**
#### 3. 注释
• 单行注释: 从 "//" 开始到本行结尾都是注释。 • 多行注释: 以 "/\*" 开始到 "\*/" 结束的中间内容全部是注释。
 • 文档注释: 以 "/\*\*" 开始到 "\*/" 结束的中间内容全部是注释。这种注释用于自动生成 文档。
注意：**Java 的 "/\* \*/" 注释不能嵌套，即不能在 "/\* \*/" 中间再添加 "/\*" 或 "*/"。**

**关于文档注释：**
![输入图片说明](/imgs/2026-01-01/caaqz3S34xHcgaWO.png)
``` Java
/**
 * 表示一个简单的学生类。
 * <p>这个类存储学生的基本信息，包括姓名和年龄。</p>
 * 
 * @author     张三
 * @version    1.0
 * @since      1.8
 */
public class Student {
    private String name;
    private int age;
```
#### 4. 数据类型
- **4种整数类型、2种浮点类型、1种字符类型、1种布尔类型**

|数据类型|存储需求|
|--|--|
|byte|1字节|
|short|2字节|
|int|4字节|
|long|8字节|
|float|4字节|
|double|8字节|

- **关于整数类型：**
• 长整型数值有一个后缀 "L" 或 "l", 如 400000000L 
• 十六进制前缀 "0x" 或 "0X", 如 0XCAFE" 
• 八进制前缀 "0", 如 010 对应十进制的 8 
• 二进制前缀 "0b" 或 "0B", 如 0b1001 对应十进制的 9

- **关于浮点数类型：**
• float 数值需要后缀 "F" 或 "f", 如 3.14F 。无后缀的实数数值是 double 类型。

- **3个特殊的浮点数值：**
• 正无穷大, 常量 `Double.POSITIVE_INFINITY`
 • 负无穷大, 常量`Double.NEGATIVE_INFINITY`
  • 不是数值, 常量 `Double.NaN`

- **关于字符类型char：** 采用**Unicode**编码

- **关于布尔类型：** Java语言的整型值和布尔值之间不能进行类型相互转换
#### 5. Java中的标识符风格约定
![输入图片说明](/imgs/2026-01-01/axPHTMXrhUbfYGIZ.png)
#### 6.变量和常量
1. **局部变量**
![输入图片说明](/imgs/2026-01-01/7oJMIj1LfLg20VdZ.png)
2. **常量定义**
![输入图片说明](/imgs/2026-01-01/lqziodLvHe0Z5KTk.png)
#### 7.运算符与表达式
1. **自动类型转换——“小阶对大阶”** 
![输入图片说明](/imgs/2026-01-01/qiDwYPeUOi7Unzc5.png)
2. **隐性强制类型转换**
![输入图片说明](/imgs/2026-01-01/xT8Eqb0Qwbs23uDE.png)
#### 8.字符串
Java没有字符串类型，标准Java类库中提供了一个预定义类String
String类没有提供任何方法来修改字符串中的每个字符，故在Java文档中将String类的对象称为是**不可变的**

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MzI3MzU0NjYsNzczMTM2NzY1LDEyMT
QyMTMxODIsOTgzODA1OTIzXX0=
-->