# LZ秘传之期末Java代码速通
## 1- Java语言入门
**01-考试成绩分析**
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
eyJoaXN0b3J5IjpbLTE4MDk5NzQ4MTgsLTEwNjA3MzA0MzNdfQ
==
-->