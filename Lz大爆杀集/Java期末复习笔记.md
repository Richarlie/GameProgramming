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
- **teshu**

<!--stackedit_data:
eyJoaXN0b3J5IjpbNjA3ODY0MDE2LDc3MzEzNjc2NSwxMjE0Mj
EzMTgyLDk4MzgwNTkyM119
-->