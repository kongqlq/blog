

# Java SE 练习01：买飞机票

## 涉及到的知识点

- 变量、数组
- 运算符：基本运算符、关系运算符、逻辑运算符...
- 程序流程控制：if、switch；for、while；死循环、循环嵌套
- 跳转关键字：break、continue、return
- 方法
- ...

## 需求

- 机票价格按照淡季旺季、头等舱和经济舱收费、输入机票原价、月份和头等舱或经济舱。
- 机票最终优惠价格的计算方案如下：旺季（5-10月）头等舱9折，经济舱8.5折，淡季（11月到来年4月）头等舱7折，经济舱6.5折

## 分析

- 键盘录入机票的原价，仓位类型，月份信息，调用方法返回机票最终的优惠价格。

- 方法内部应该先使用if分支判断月份是是旺季还是淡季，然后使用switch分支判断是头等舱还是经济舱。

- 选择对应的折扣进行计算并返回计算的结果，如果信息录入有误返回价位为-1元代表即可。

  ```java
  package Demo;
  
  import java.util.Scanner;
  
  public class Test1 {
      /*目标：完成买飞机票价格的计算
       * 1.让用户输入机票的原价，月份，仓位类型
       */
      public static void main(String[] args) {
          Scanner scanner = new Scanner(System.in);
          System.out.println("请输入机票原价：");
          double money = scanner.nextDouble();
  
          System.out.println("请输入当前月份：");
          int month = scanner.nextInt();
  
          System.out.println("请输入头等舱或经济舱：");
          String type = scanner.next();
  
          System.out.println("机票优惠之后的价格是" + find(money, month, type));
      }
  
      public static double find(double money, int month, String type) {
          if (month >= 5 && month <= 10) {
              //旺季
              switch (type) {
                  case "头等舱":
                      money *= 0.9;
                      break;
                  case "经济舱":
                      money *= 0.85;
                      break;
                  default:
                      System.out.println("您输入的舱位信息有误！");
                      money = -1;
  //                    break;
              }
          } else if (month >= 1 && month <= 4 || month >= 11 && month <= 12) {
              //淡季
              switch (type) {
                  case "头等舱":
                      money *= 0.7;
                      break;
                  case "经济舱":
                      money *= 0.65;
                      break;
                  default:
                      System.out.println("您输入的舱位信息有误！");
                      money = -1;
  //                    break;
              }
          } else {
              System.out.println("月份输入有误");
              return -1;
          }
          return money;
      }
  }
  
  ```

  