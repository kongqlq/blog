# Java SE 练习04：数组元素复制

## 需求：

> 把数组中的元素复制到另一个新数组中去

## 分析

- 需要动态初始化一个数组，长度与原数组一样。
- 遍历原数组的每个元素，依次赋值给新数组。
- 输出两个数组的内容。

## 代码实现

```java
package Demo;

public class Test4 {
    public static void main(String[] args) {
        //arr1是被复制的数组
        int[] arr1 = {1, 2, 3, 4, 5};
        int[] arr2 = new int[arr1.length];
        //int[] arr2 = arr1;    //没有完成数组的复制，只是复制了arr1的地址
        copy(arr1, arr2);
        printArray(arr1);
        printArray(arr2);
    }

    //arr1是被复制的数组
    public static void copy(int[] arr1, int[] arr2) {
        for (int i = 0; i < arr1.length; i++) {
            arr2[i] = arr1[i];
        }
    }

    public static void printArray(int[] arr) {
        System.out.print("[");
        for (int i = 0; i < arr.length; i++) {
            System.out.print(i == arr.length - 1 ? arr[i] : arr[i] + ", ");
        }
        System.out.println("]");
    }
}

```

## 输出结果

```java
[1,2,3,4,5]
[1,2,3,4,5]
```

