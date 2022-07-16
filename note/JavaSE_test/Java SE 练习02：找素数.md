# Java SE 练习02：找素数

## 问题描述：

> 判断101-200之间有多少个素数，并输出所有素数

## 什么是素数：

- 除了1和它本身以外，不能被其他正整数整除，就叫素数。

## 分析：

- 101-200之间的数据可以采用循环依次拿到; 每拿到一个数，判断该数是否是素数。
- 判断规则是：从2开始遍历到该数的一半的数据，看是否有数据可以整除它，有则不是素数，没有则是素数。
- 如果最终判定是素数，即可输出展示。

## 代码实现：

```java
package Demo;

public class Test2 {
    public static void main(String[] args) {
        //遍历101-200的数
        for (int i = 101; i <= 200; i++) {
            //定义一个标记位
            boolean flag = true;
            //通过循环判断是否能整除
            for (int j = 2; j <= i / 2; j++) {
                if (i % j == 0) {
                    flag = false;
                    break;
                }
            }
            //通过判断flag来确定是否是素数
            if (flag) {
                System.out.print(i + "\t");
            }
        }
    }
}

```

