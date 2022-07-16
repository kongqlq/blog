# Java SE 练习06：数字加密

## 需求

> 某系统的数字密码：比如1983，采用加密方式进行传输，规则如下：先得到每位数，然后每位数都加上5 , 再对10求余，最后将所有数字反转，得到一串新数。

## 分析

- 将每位数据存入到数组中去，遍历数组每位数据按照规则进行更改，把更改后的数据从新存入到数组中。
- 将数组的前后元素进行交换，数组中的最终元素就是加密后的结果。

## 源代码

```java
package Demo;

import java.util.Scanner;
/**
 需求：某系统的数字密码，比如1983，采用加密方式进行传输，规则如下：先得到每位数，
 然后每位数都加上5再对10求余，最后将所有数字反转，得到一串新数。

 */
public class Test6_1 {
    public static void main(String[] args) {
        // 1.定义一个数组存储需要加密的数据
        System.out.println("请您输入需要加密的数字个数：");
        Scanner scanner = new Scanner(System.in);
        int length = scanner.nextInt();
        int[] arr = new int[length];

        // 2.录入需要加密的数字
        for (int i = 0; i < arr.length; i++) {
            System.out.println("请您输入第" + (i + 1) + "个数字：");
            arr[i] = scanner.nextInt();
        }

        // 3.打印数组内容
        printArray(arr);

        // 4.遍历数组中的每个数据，按照规则进行修改
        for (int i = 0; i < arr.length; i++) {
            arr[i] = (arr[i] + 5) % 10;
        }

        // 5.把数组中的元素进行反转操作。
        for (int i = 0, j = arr.length - 1; i < j; i++, j--) {
            // 交换 i 和 j位置处的值，即可反转
            int temp = arr[j];
            arr[j] = arr[i];
            arr[i] = temp;
        }
        printArray(arr);
    }
    public static void printArray(int[] arr){
        System.out.print("[");
        for (int i = 0; i < arr.length; i++) {
            System.out.print(i == arr.length - 1 ? arr[i] : arr[i] + ",");
        }
        System.out.println("]");
    }
}
```

### 控制台

```
请您输入需要加密的数字个数：
4
请您输入第1个数字：
1
请您输入第2个数字：
9
请您输入第3个数字：
8
请您输入第4个数字：
3
[1,9,8,3]
[8,3,4,6]
```



## 改进后

> 实现了直接输入数字即可加密

```java
package Demo;

import java.util.Scanner;

public class Test6 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入需要加密的数字：");
        //2.录入需要加密的数字
        int num = scanner.nextInt();
        int length = 0;
        int t1 = num;
        //通过求余数判断位数
        for (int i = 0; t1 > 10; i++) {
            t1 = t1 / 10;
            length = i++;
        }
        t1 = num;
        int[] arr1 = new int[length];
        for (int i = 0, j = length; i < length; i++, j--) {
            arr1[i] = num / (int) Math.pow(10, j - 1);
            num %= (int) Math.pow(10, j - 1);
            //当num<10代表仅剩最后个位数字,则直接跳出循环
            if (num < 10) {
                arr1[i + 1] = num;
                break;
            }
        }
        //3.打印数组内容
        System.out.println("加密前：");
        printArray(arr1);
        int[] arr2 = key1(arr1);
        System.out.println("加密后：");
        printArray(arr2);
    }

    public static int[] key1(int[] arr) {
        //4.加密
        for (int i = 0; i < arr.length; i++) {
            arr[i] = (arr[i] + 5) % 10;
        }
        //5.反转
        for (int i = 0, j = arr.length - 1; i < j; i++, j--) {
            int t2 = arr[j];
            arr[j] = arr[i];
            arr[i] = t2;
        }
        return arr;
    }

    public static void printArray(int[] arr) {
        System.out.print("[");
        for (int i = 0; i < arr.length; i++) {
            System.out.print(i == arr.length - 1 ? arr[i] : arr[i] + ",");
        }
        System.out.println("]");
    }
}

```

### 控制台

```
请输入需要加密的数字：
1983
加密前：
[1,9,8,3]
加密后：
[8,3,4,6]
```

能够看出改进后的很方便