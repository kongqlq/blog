# Java SE 练习05：评委打分

## 需求

> 在唱歌比赛中，有6名评委给选手打分，分数范围是[0 - 100]之间的整数。选手的最后得分为：去掉最高分、最低分后的4个评委的平均分，请完成上述过程并计算出选手的得分。

## 分析

- 把6个评委的分数录入到程序中去 ----> 使用数组

 ```java
  int[] scores = new int[6];
 ```

- 遍历数组中每个数据，进行累加求和，并找出最高分、最低分。

- 按照分数的计算规则算出平均分。

```java
package Demo;

import java.util.Scanner;

public class Test5 {
    public static void main(String[] args) {
        //定义一个动态初始化的数组，用于后期录入6个评委的分数
        int[] arr = new int[6];

        //录入6各评委的分数
        Scanner scanner = new Scanner(System.in);
        for (int i = 0; i < arr.length; i++) {
            System.out.println("请输入第" + (i + 1) + "位评委的分数");
            //把分数存到数组的对应位置中
            arr[i] = scanner.nextInt();
        }
        //遍历数组中的元素，选出最大值，最小值，以及总分
        int max = arr[0];
        int min = arr[0];
        int sum = 0;
        //因为下边要统计总分，所以这里的i取0
        for (int i = 0; i < arr.length; i++) {
            if (max < arr[i]) {
                //替换最大值变量存储的数据
                max = arr[i];
            }
            if (min > arr[i]) {
                //替换最小值变量存储的数据
                min = arr[i];
            }
            //统计总分
            sum += arr[i];
        }
        System.out.println("最高分为：" + max);
        System.out.println("最低分为：" + min);
        //统计平均分
        double result = (sum - max - min) * 1.0 / (arr.length - 2);
        System.out.println("选手最总得分：" + result);
    }
}
```

