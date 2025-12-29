# LZ秘传之期末Java代码速通
## 1- Java语言入门
**01-考试成绩分析**
​相关知识点
**选择结构
循环结构
二维数组**

任务描述
某个专业共有 n 个班，每个班有人数不同的学生。
某门课程考试结束后，需要统计分析每个班的平均分、最高分和最低分。
编程要求
创建 Java Application 项目，程序中自行定义类名，程序中所有类放在与项目名相同的包中。

**输入数据说明**
输入数据由多行构成：
第1行，1个正整数，表示该专业的班数
第2行开始每一行表示一个班的成绩数据
第1个是正整数 n，表示该班有n个学生
后面有 n 个 [0,100] 之间的实数，表示各个学生的成绩

**输出数据说明**
输出数据有多行组成，每行表示一个班的数据，按各班的输入数据排列。

每行有3个实数，依次是：平均分 最高分 最低分，数据保留2位小数，中间用空格分隔。

提交说明
将所有源程序文件压缩成zip文件提交。直接把项目目录下的 src 目录压缩成 zip 文件即可。

测试说明
测试样例1:

测试输入:

3

5 90 80 70 50 60

3 95 75 85

6 93 88 65 75 85 80

预期输出:

70.00 90.00 50.00

85.00 95.00 75.00

81.00 93.00 65.00

​

``` Java
package examscoreanalysis;

import java.util.Scanner;

/**
 * 考试成绩分析程序
 * 功能：统计每个班的平均分、最高分和最低分
 */
public class ExamScoreAnalyzer {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // 读取班级数量
        int classCount = scanner.nextInt();
        // 创建二维数组存储每个班的数据
        ClassData[] classes = new ClassData[classCount];
        // 处理每个班级的数据
        for (int i = 0; i < classCount; i++) {
            // 读取班级人数
            int studentCount = scanner.nextInt();
            // 创建班级数据对象
            classes[i] = new ClassData(studentCount);
            // 读取每个学生的成绩
            for (int j = 0; j < studentCount; j++) {
                double score = scanner.nextDouble();
                classes[i].addScore(j, score);
            }
        }
        scanner.close();
        // 输出每个班级的统计数据
        for (int i = 0; i < classCount; i++) {
            classes[i].calculateStatistics();
            classes[i].printStatistics();
        }
    }
}
/**
 * 班级数据类
 * 用于存储和处理单个班级的成绩数据
 */
class ClassData {
    private double[] scores;      // 学生成绩数组
    private int studentCount;     // 学生人数
    private double average;       // 平均分
    private double maxScore;      // 最高分
    private double minScore;      // 最低分
    /**
     * 构造函数
     * @param count 学生人数
     */
    public ClassData(int count) {
        this.studentCount = count;
        this.scores = new double[count];
        this.average = 0.0;
        this.maxScore = 0.0;
        this.minScore = 100.0;
    }
    /**
     * 添加学生成绩
     * @param index 学生索引
     * @param score 成绩
     */
    public void addScore(int index, double score) {
        if (index >= 0 && index < studentCount) {
            scores[index] = score;
        }
    }
    /**
     * 计算统计信息（平均分、最高分、最低分）
     */
    public void calculateStatistics() {
        if (studentCount == 0) {
            return;
        }
        double sum = 0.0;
        maxScore = scores[0];
        minScore = scores[0];
        // 遍历所有成绩，计算总和并找出最高分和最低分
        for (int i = 0; i < studentCount; i++) {
            double score = scores[i];
            sum += score;
            // 使用选择结构判断最高分
            if (score > maxScore) {
                maxScore = score;
            }
            // 使用选择结构判断最低分
            if (score < minScore) {
                minScore = score;
            }
        }
        // 计算平均分
        average = sum / studentCount;
    }
    /**
     * 输出统计结果
     */
    public void printStatistics() {
        // 保留两位小数输出
        System.out.printf("%.2f %.2f %.2f%n", average, maxScore, minScore);
    }
    // Getter方法（如果需要）
    public double getAverage() {
        return average;
    }
    public double getMaxScore() {
        return maxScore;
    }
    public double getMinScore() {
        return minScore;
    }
    public int getStudentCount() {
        return studentCount;
    }
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1ODgxNzY4MzEsLTEwNjA3MzA0MzNdfQ
==
-->