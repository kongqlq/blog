# Java SE 练习03：随机验证码

## 问题描述

> 定义方法实现随机产生一个指定位数的验证码，每位可能是数字、大写、小写字母

## 分析：

- 定义一个String类型的变量存储验证码字符。
- 定义一个for循环，循环n次。
- 随机生成0|1|2的数据，依次代表当前位置要生成数字|大写字母|小写字母（这样使生成数字、大写字母、小写字母的概率相同）。
- 把0、1、2交给switch生成对应类型的随机字符，把字符交给String变量。
- 循环结束后，返回String类型的变量即是所求的验证码结果。

## 代码实现

```java
package Demo;

import java.util.Random;

public class Test3 {
    public static void main(String[] args) {
        String code = code(6);
        System.out.println("随机验证码 " + code);
    }

    //这里的形参 num 是需要生成验证码的位数
    public static String code(int num) {
        Random random = new Random();
        String code = "";
        for (int i = 0; i < num; i++) {
            int type = random.nextInt(3);
            switch (type) {
                case 0:
                    char ch = (char) (random.nextInt(26) + 65);
                    //随机大写字母
                    code += ch;
                    break;
                case 1:
                    char ch1 = (char) (random.nextInt(26) + 97);
                    //随机小写字母
                    code += ch1;
                    break;
                case 2:
                    code += random.nextInt(10);
                    //随机数字
                    break;
            }
        }
        return code;
    }
}

```

