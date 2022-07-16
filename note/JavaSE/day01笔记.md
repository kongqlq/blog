# day01 【前言、入门程序、常量】

**主要内容**

```java
Java语言的发展历史【了解】
Java语言开发环境搭建【重点】
HelloWorld入门程序【重点重点重点: 如何书写,如何运行,至于说程序中的内容是什么意思,今天先不讲解】
注释和关键字【理解】
常量/变量【重点重点重点】
进制及转换【了解】
```

**学习目标**

```java
能够输出各种类型的常量及变量并解决程序出现的问题
```

### 第一章 开发前言

##### 1.1 Java语言概述【了解】

```java
Java是一种高级编程语言，而且是面向对象的编程语言。
Java语言是美国Sun公司（Stanford University Network），在1995年推出的高级的编程语言。
Java语言共同创始人之一：詹姆斯·高斯林 （James Gosling），被称为“Java之父”
Java语言的版本：1.0-1.4，5.0...8.0...13.0
目前我们学习的8.0
```

##### 1.2 Java语言能做什么

```java
Java语言主要应用在互联网程序的开发领域
网上购物商城
物流
金融
各行各业的门户网站
```

##### 1.3 Java语言的跨平台实现原理

```java
1.平台: 指的是操作系统,比如windows,linux,macos
2.跨平台: 跨越不同的操作系统
	简单讲: 我们在一个操作系统上编写的程序,可以在其它任意操作系统上运行
	一次编写,到处运行
3.JVM: Java虚拟机,是专门用来运行Java程序的

问题1:
	JVM是跨平台的? 错误的
	每个系统对数据的格式和处理方式是不同的,要求每个系统都需要
	安装专门针对本操作系统的JVM,专门用来运行java程序

问题2:
	Java程序是跨平台的? 正确的

问题3:
	Java程序的跨平台,是通过JVM的不夸平台实现的? 正确的
```

![1599095168899](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041997.jpg)

##### 1.4 JDK_JRE_JVM的组成和作用

```java
1.JVM: 叫做Java虚拟机,是专门用来运行Java程序的,但是不能单独安装JVM
2.JRE: 叫做Java运行环境,包含JVM和核心类库
3.JDK: 叫做Java开发工具包,包含JRE和开发工具(java命令,javac命令)
    
小贴士：
	三者关系： JDK > JRE > JVM
```

![image-20200420095512929](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041999.jpg)

### 

##### 1.5 进制及转换

- 进制

  ```java
  进制的概念：逢几进一,就叫做几进制	
  进制的分类：        
  	十进制: 逢十进一,每位数字0到9
  	二进制: 逢二进一,每位数字0到1
  	八进制: 逢八进一,每位数字0到7
  	十六进制: 逢十六进一,每位数字0到9,A(10),B(11),C(12),D(13),E(14),F(15)        
  ```

  

- 转换

  ```java
  1.十进制转十进制(十进制中从左向右,每位数字内部隐藏了10的多少次方,第一位是10的0次方,第二位是10的1次方...):
  	x^y:x的y次方
  	1234 =  1000 + 200 + 30 + 4
           =  1*10^3 + 2*10^2 + 3*10^1 + 4*10^0
           
  2.二进制转十进制(二进制中从左向右,每位数字内部隐藏了2的多少次方,第一位是2的0次方,第二位是2的1次方...):	
  	这种转换方式: 8421编码
  	1101 =  1*2^3 + 1*2^2 + 0*2^1 + 1*2^0
      	 =  1*8 + 1*4 + 0*2 + 1*1
           =  8 + 4 + 0 + 1
           = 13
          
    	11111 = 1*2^4 + 1*2^3 + 1*2^2 + 1*2^1 + 1*2^0
      	  = 1*16 + 1*8 + 1*4 + 1*2 + 1*1
            = 16 + 8 + 4 + 2 + 1
            = 31
          
     	
  3.十进制转二进制(除以2取余数,倒过来写): 
      十进制的13转换成二进制:	 1101
  	十进制的75转换成二进制:    1001011
  
  ```

  ##### 十进制转二进制图解:

  ![1599098203857](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041263.jpg)



##### 1.6 计算机中的存储单位(2的10次方就是1024  ) 

```java
最重要的是: 一个字节占8位
1.位(bit): 计算机中存储一个二进制数字0或者1,所占用的空间,简写为b	
2.字节(byte): 8个二进制位,就是一个字节,简写为B
	字节是我们常见的计算机中最小存储单元。计算机存储任何的数据，都是以字节的形式存储
	1024B = 1KB	
	1024KB = 1MB
	1024MB = 1GB
	1024GB = 1TB
	...    
```



### 第二章 Java语言开发环境搭建

##### 2.1 JDK安装

```java
jdk的下载和安装
    1.注意操作系统是windows,linux,MacOS
    2.注意操作系统的位数是32位还是64位
    3.安装java相关软件的时候: 安装路径中不允许出现中文和空格-----务必注意-----
```



![image-20200330102544966](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041000.jpg)

##### 2.2 环境变量JAVA_HOME的配置【了解，已经配置了的话，大家不用过多的浪费时间】

```java
目的: 让javac和java命令可以在任意目录下运行
配置步骤: 参见讲义
```

##### 2.3 Notepad++软件的安装和配置

![image-20200330120224421](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041001.jpg)

![1591846481309](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041002.jpg)

搜狗输入法的设置: 中文状态使用英文标点符号

![image-20200420120351691](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041003.jpg)

![image-20200420120702626]()

![image-20200420120741611](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041004.jpg)



### 第三章 HelloWorld入门程序

##### 3.1 程序开发的步骤

```java
1.编写源程序
	源程序: 程序员自己编写的,程序员可以看得懂得程序
	源程序: 内部就是由字母,数字,_,$,{,},(,)字符组成
	源程序本质就是一个文本文件,但是扩展名不是.txt,而是.java
    
2.编译源程序:
	(1)计算机(JVM)是一个二货,只能识别0和1,源程序计算机(JVM)是不认识的
	(2)需要把源程序,转换成0和1的东西,这种存储0和1的文件,称为字节码文件,	这种文件的扩展名.class
	(3)如何把源程序转换成字节码程序(存储0和1的文件)呢?
		使用编译命令javac,使用格式:
			javac 文件名.java
			javac HelloWorld.java 
			
3.运行字节码程序: 
	不管是源程序还是编译后的字节码程序,都是直接存储在硬盘当中的
	而我们要运行的是字节码程序,不会自动运行,必须把需要运行的字节码程序交给JVM执行
	如何让JVM运行指定的字节码程序呢?
		使用运行命令java,使用格式:
			java 文件名
			java HelloWorld 会把HelloWorld.class字节码程序交给JVM执行
```

![1599103124746](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041005.jpg)



##### 3.2 HelloWorld案例的编写编译运行

```java
1.编写源程序
	创建一个名称为HelloWorld.txt的文本文件,扩展名修改为.java,
	使用notepad++软件打开此文件,输入以下内容:
	public class HelloWorld {
        public static void main(String[] args) {
            System.out.println("HelloWorld");
        }
    }

2.编译源程序:	
	使用编译命令javac,使用格式:
		javac 文件名.java
		javac HelloWorld.java
    注意:
		(1)保证在当前路径下可以看到要编译的java文件
		(2)保证在当前路径下javac编译命令可以使用
		(3)javac编译命令后面文件名的后面必须写扩展名.java
		
3.运行字节码程序: 	
	使用运行命令java,使用格式:
		java 文件名
		java HelloWorld 会把HelloWorld.class字节码程序交给JVM执行
        
    注意:
		(1)保证在当前路径下可以看到要运行的class文件
		(2)保证在当前路径下java运行命令可以使用
		(3)java运行命令后面文件名的后面不能写扩展名.class   
    
```

```java
public class HelloWorld {
	public static void main(String[] args){
		System.out.println("HelloWorld");
	}
}
```



##### 3.3 HelloWorld案例的常见问题

```java
非法字符问题。Java中的符号都是英文格式的。
大小写问题。Java语言对大小写敏感（区分大小写）。
在系统中显示文件的扩展名，避免出现HelloWorld.java.txt文件。
编译命令后的java文件名需要带文件后缀.java
运行命令后的class文件名（类名）不带文件后缀.class
不要把main写成mian
```

### 第四章 注释和关键字

##### 4.1 注释

```java
1.概念: 是用来解释说明程序的说明性信息,是给程序员看的,不参与编译,不影响程序的执行效率
    
2.分类:
	(1)单行注释: //一行注释性的信息
	(2)多行注释: /* 多行注释性的信息 */
	(3)文档注释: /** 多行注释性的信息 */
```

```java
//这里是定义一个类,public class 目前是固定写法
//class后面的名字必须要和文件名保持一模一样
public class Demo01ZhuShi {
	/*
		这里是定义一个方法,public static void 是固定写法
		main方法又叫做主方法,是程序的入口
	*/
	public static void main(String[] args){
		/**
			System.out.println是一条输出语句,
			其中""中的内容是原样显示在控制台的
		*/
		System.out.println("zhushi~~~~~~~~~~~~~~~");
	}
}
```



##### 4.2 关键字

```java
邮箱：	
	@符号在邮箱中有特殊的含义和使用格式,你不能随便胡乱的使用
	@前面表示: 用户名称
	@后面表示: 邮箱地址,用的是哪一家的邮箱
	
	zhangsan@163.com	正确的
	zhangsan_nigulasi@163.com	正确的
	zhangsan@nigulasi@163.com	错误的
	
1.概念: 是指在程序中，Java已经定义好的单词，具有特殊含义以及特殊的使用格式。

2.注意:		
	这里主要是讲解关键字的含义是什么? 不讲解每个关键字的用法和使用格式	

3.特点:
	(1)在高级编辑其中,有彩色显示
	(2)所有字母都是小写的
	
4.说出以下程序中有哪些关键字:
	public class static void	
	
```

```java
/*
	找出以下程序中的关键字?
		public class static void
*/
public class Demo02GuanJianZi {
	public static void main(String[] args){
		System.out.println("guanjianzi==========");
	}
}
```



### 第五章 常量 

##### 5.1 常量的概念和分类

```java
数学中:
	b = a + 6; 数字6是永远不能发生改变的,6属于整数类型
	y = x + 6.6; 数字6.6永远不能发生改变的,6.6属于小数类型
	
数字6,6.6是不可以发生改变的,在数学中叫做常数,在java中叫常量
数字6,6.6是不可以发生改变的,数学中是有分类的,
	对应到java中也是有分类的,而且java中的分类比数学中更为丰富

1.概念: 在程序的执行过程中,其值不可以发生改变的量

2.分类(总共有6类):
	(1)整数常量:	直接写 6,-6
    (2)小数常量:  直接写 6.6,-6.6
    (3)字符常量:
		java中规定,字符常量必须使用单引号''引起来,而且单引号''中只能写一个字符(不能不写,也不能写2个及以上的字符)
        以下选项中,正确表示字符常量的是哪些选项呢?	ACE
       		A:	'a'
            B:	''		''中什么都没有
            C:  ' '		''中有一个空格字符
            D:	'ab'
            E: 	'好'
            F:  '女子'
    (4)字符串常量:
		java中规定,字符串常量必须使用双引号""引起来,而且双引号""中可以写多个字符(0个/1个/2个/...)
           以下选项中,正确表示字符串常量的是哪些选项呢?	ABCDEF
       		A:	"a"
            B:	""		""中什么都没有
            C:  " "		""中有一个空格字符
            D:	"ab"
            E: 	"好"
            F:  "真的好想你"
    (5)布尔常量: 
		只有以下两个值:
		true: 真的,正确的,对的,成立的,是的
		false: 假的,错误的,不对的,不成立的,否定的
	(6)空常量:	后面讲解
		只有一个值null
		注意: 不能直接打印空常量
```

##### 5.2 打印不同类型的常量

```java
/*
	打印不同类型的常量
	System.out.println(xxx): 打印xxx到控制台,并换行
	System.out.print(xxx): 打印xxx到控制台,不换行
	System.out.println(): 单独只完成换行
	
	其中xxx根据不同的类型有不同的书写格式	
		整数/小数/布尔类型的常量,直接写就可以
		字符常量: 必须使用单引号
		字符串常量: 必须使用双引号
		
	ctrl + d: 复制一行
*/
public class Demo03ChangLiang {	
	public static void main(String[] args){
		//(1)整数常量
		System.out.println(6);
		System.out.println(-6);		
		System.out.println("---------------------");
		System.out.print(6);
		System.out.println();
		System.out.print(-6);
		System.out.println();		
		System.out.println("---------------------");
		//(2)小数常量
		System.out.println(6.6);
		System.out.println(-6.6);
		//(3)字符常量
		System.out.println('a');//正确
		//System.out.println('');//错误的,''中不能什么都不写
		System.out.println(' ');//正确
		//System.out.println('ab');//错误的,''中只能写一个字符
		System.out.println('好');//正确
		//System.out.println('好想有个女同桌');//错误的,''中只能写一个字符
		System.out.println("---------------------");
		
		//(4)字符串常量:
		System.out.println("a");
		System.out.println("");
		System.out.println(" ");
		System.out.println("ab");
		System.out.println("好");
		System.out.println("好想有个女朋友");
		
		//(5)布尔常量
		System.out.println(true);	
		System.out.println(false);

		//(6)空常量
		//System.out.println(null);	//错误: 不能直接打印输出空常量
	}
}
```



### 第六章 变量和数据类型【重要】

##### 6.1 变量概念及分类

```java
数学中:
	b = a + 6; 数字6是永远不能发生改变的,6属于整数类型
	y = x + 6.6; 数字6.6永远不能发生改变的,6.6属于小数类型
	
	a:2 b:8
    a:4 b:10
    a和b中的值是可以发生变化的,而且是有类型的(整数),并且每次只能存储一个数字
    
    x:2.2 y:8.8
    x:3.3 y:9.9
	x和y中的值是可以发生变化的,而且是有类型的(小数),并且每次只能存储一个数字
	
	总结:
		像a,b,x,y这样的东西,内部只能存储一个数字,而且该数字是有类型的,我们把这种东西称为变量
		变量可以理解为一个小的容器(只能放一个东西)
        
        为什么要有这么多的分类呢?
            每种分类占用的字节数不同,取值范围就不同,使用场景就不同
	
1.变量概念: 在程序的执行过程中,其值可以在一定范围内发生改变的量
2.分类(基本类型(以下四类八中)和引用类型): 
	(1)整数
        1个字节=8位
        1 Byte=8 b
		byte	占1个字节	取值范围 -128到127
		short	占2个字节	取值范围 正负3万多
		int		占4个字节	取值范围 正负21亿	整数常量默认是int类型
		long	占8个字节	取值范围 大概19位数字	表示long类型的数据时,建议右边添加字母L/l		(2)小数
		float	占4个字节	表示float类型的数据时,建议右边添加字母F/f
			虽然float占4个字节,但是由于内部采用科学计数法,取值范围远远大于占用8个字节的long类型
		
		double	占8个字节	小数常量默认是double类型
		
	(3)字符:
		char	占2个字节	取值范围0到65535
		
	(4)布尔:
		boolean	占1个字节	取值只有 true,false
			
```



##### 6.2 变量定义格式图解分析 

```java
变量的理解:
1.变量的本质,就是一块内存空间,空间的大小由数据类型决定
2.变量对应的内存空间中,必须有数据,才可以使用,没有数据不能用,
	把数据存储到变量对应的内存空间的过程叫做赋值或者初始化
3.要想找到变量对应的内存空间的数据,必须给变量对应的内存空间起个名字,叫做变量名称

定义变量格式一:
	数据类型 变量名称 = 数据值;//挖一个坑同时向该坑中种一个萝卜

定义变量格式二:
	数据类型 变量名称;//先挖一个坑
	变量名称 = 数据值;//向坑中种一个萝卜

```

##### 图解:

![1599124596661](https://raw.githubusercontent.com/kongqlq/img/main/img/202207162041006.jpg)





##### 6.3 定义8种变量

```java
//定义不同类型的变量
public class Demo04BianLiang {	
	public static void main(String[] args){
		//整数变量
		//挖了一个占1个字节的坑,给这个坑起个名字叫a
		byte a;
		a = 100;//把数字100存储到名称为a的坑中
		System.out.println(a);//打印名称为a的坑中的内容: 100
		
		//挖了一个占2个字节的坑,给这个坑起个名字叫b,
		//同时把数字200存储到这个坑中
		short b = 200;
		System.out.println(b);//打印名称为b的坑中的内容: 200
		
		//挖了一个占4个字节的坑,给这个坑起个名字叫c
		int c;
		c = 300;//把数字300存储到名称为c的坑中
		System.out.println(c);//打印名称为c的坑中的内容: 300
		
		//挖了一个占8个字节的坑,给这个坑起个名字叫d,
		//同时把数字500存储到这个坑中
		long d = 500L;
		System.out.println(d);//打印名称为d的坑中的内容: 500
		
	}
}
```

```java
//定义不同类型的变量
public class Demo05BianLiang {	
	public static void main(String[] args){
		//小数
		//定义float类型的变量a,初始化值为6.6
		//错误: 小数6.6默认是double类型,占8个字节,不能赋值给占4个字节的float变量
		//大萝卜,不能直接放入小坑中
		//float a = 6.6;
		//System.out.println(a);
		
		//定义float类型的变量b,初始化值为6.6
		float b = 6.6F;
		System.out.println(b);//输出变量b中的内容: 6.6
		
		//定义double类型的变量c
		double c;
		//把数字8.8赋值给变量c
		c = 8.8;
		System.out.println(c);//输出变量c中的内容: 8.8
		
		//字符
		//定义char类型的变量ch,初始化值为字符a
		char ch = 'a';
		System.out.println(ch);//输出变量ch中的内容: a
		
		//错误: ''中只能写一个字符
		//char ch2 = 'ab';
		//System.out.println(ch2);
		
		//布尔
		//定义boolean类型的变量flag,初始化值为true
		boolean flag = true;
		System.out.println(flag);//输出变量flag中的内容: true
		//把flase赋值给变量flag,flag中原有的数据将被覆盖
		flag = false;
		System.out.println(flag);//输出变量flag中的内容: false
		//错误: 数据类型不匹配
		//flag = 100;
	}
}
```



##### 6.4 变量的注意事项

```java
变量定义的注意事项:
	1.变量名称：在同一个大括号范围内，变量的名字不可以相同。
	2.变量赋值：定义的变量，不赋值不能使用。
	
public class Demo06BianLiangNotice {
	public static void main(String[] args){
		//定义int变量a,并初始化
		int a = 100;
		System.out.println(a);//100
		
		//把数字200赋值给变量a,变量a中的原有数据将被覆盖
		a = 200;
		System.out.println(a);//200
		
		//错误: 变量a在前面已经定义过来的,这里不能再重新定义了
		//int a = 300;		
		//System.out.println(a);
		
		//定义int变量b,未初始化
		int b;
		//System.out.println(b);//错误: 此时变量b中没有值,不能用
		
		b = 1000;//把数字1000赋值给变量b
		System.out.println(b);//1000
	}
}
```

```java
变量定义的注意事项:		
	1.定义long类型的变量时，需要在整数的后面加L（大小写均可，建议大写）。
		因为整数默认是int类型，整数太大可能超出int范围。		
	2.定义float类型的变量时，需要在小数的后面加F（大小写均可，建议大写）。
		因为浮点数的默认类型是double， double的取值范围是大于float的，类型不兼容。
public class Demo07BianLiangNotice {
	public static void main(String[] args){
		//整数常量6000000000,默认是int类型,然而int类型的取值范围是正负21亿
		//6000000000的大小已经超出了int的取值范围,说白了就是int中根本没有这个数字6000000000
		//long num = 6000000000;
		//System.out.println(num);
		
		//6000000000L就是long类型的数字,占8个字节,可以存储在long类型的变量中
		long num2 = 6000000000L;
		System.out.println(num2);
		
		//8.8默认是double类型,占8个字节,不能直接赋值给占4个字节的float变量
		//大萝卜,不能直接放入小坑中
		//float f = 8.8;
		//System.out.println(f);
		
		float f2 = 8.8F;
		System.out.println(f2);
	}
}
```



##### 6.5 标识符的含义及注意事项

```java
标识符:
	1.概念: 程序中起名字的地方(类名,方法名称,变量名)
	2.命名规则： 硬 性 要 求
		标识符可以包含 英文字母26个(区分大小写) 、 0-9数字 、 $（美元符号） 和 _（下划线） 。
		标识符不能以数字开头。
		标识符不能是关键字。
		
	3.命名规范： 软 性 建 议   
        类名规范：首字母大写，后面每个单词首字母大写（大驼峰式）。
			Demo01BianLiang
			Demo02BianLiang
			Demo03BianLiangNotice
			Demo04BiaoShiFu
				
		方法名规范： 首字母小写，后面每个单词首字母大写（小驼峰式）。
			getMin(...){...}
			getMax(...){...}
				
		变量名规范：首字母小写，后面每个单词首字母大写（小驼峰式）。
			num
			value
			maxValue
```

```java
public class Demo08BiaoShiFu {	
	public static void main(String[] args){
		int ab_$23cd;//正确的
		//int ab_$2%3cd;//错误的,标识符中不能包含字母,数字,$和_以外的内容
		//int 2b;//错误的,标识符以数字开头
		//int class;//错误的,标识符不能是关键字
		
		int ageOfMyGirlFriend = 18;//小驼峰规则
		int ageofmygirlfriend = 18;//不报错,但是不符合小驼峰规则
	}
}
```





##### 总结

```java
能够说出JDK,JRE,JVM各自的作用和关系	
能够完成HelloWorld案例的编写及运行	
1.编写
	public class HelloWorld {
		public static void main(String[] args){
			System.out.println("HelloWorld");
		}
	}
2.编译
	javac HelloWorld.java		生成HelloWorld.class文件
	
3.运行
	java HelloWorld
	
能够使用注释对程序进行说明	
	//: 单行注释
	/*...*/: 多行注释
	/** ... */: 文档注释
	
能够知道关键字的特点
	具有特殊含义和用法的英文档次
	特点:
		1.高级编辑其中彩色显示
		2.全部都是小写字母
		public class static void
		
能够知道常量的分类   
	整数: 100
    小数: 6.6
    字符: 'a'
    字符串: "..."
    布尔: true,false
    空: null
        
```
