# 05-流程控制

## 条件语句

​ 条件语句可根据不同的条件执行不同的语句。包括if条件语句与switch多分支语句。

### if条件语句

​ 使用if条件语句，可选择是否要执行紧跟在条件之后的那个语句。关键字if之后是作为条件的“布尔表达式”，如果该表达式返回true，则执行其后的语句；若为false，则不执行if后的语句。可分为简单的if条件语句、if···else语句和if···else if多分支语句。

```java
int a = 100;
if(a == 100) {
    System.out.println(a);
}
```

​ 如上方代码，｛｝之间为复合语句，if为条件语句，翻译过来就是如果a等于100，则输出a的值，否则不执行。如果if后只有一条语句，比如上述代码只有一条输出，可以不加｛｝，但为了代码的可读性，以及防止代码过多出现不必要的错误，建议所有的if、else后都加上相应的｛｝。

### if···else语句

​ if···else语句是条件语句中最常用的一种形式，它会针对某种条件有选择的作出处理。通常表现为“如果满足某种条件，就进行某种处理，否则就进行另一种处理”。

if后的\(\)内的表达式必须是boolean型的。如果为true，则执行if后的复合语句；如果为false，则执行else后的复合语句。

```java
/**
输出
math has passed
english has not passed
**/
public class Getifelse {

    public static void main(String[] args) {
        int math = 80;        // 声明，数学成绩为80（及格）
        int english = 50;    // 声明，英语成绩为50（不及格）

        if(math >= 60) {    // if判断语句判断math是否大于等于60
            System.out.println("math has passed");
        } else {            // if条件不成立
            System.out.println("math has not passed");
        }

        if(english >= 60) {    // if判断语句判断english是否大于等于60
            System.out.println("english has passed");
        } else {            // if条件不成立
            System.out.println("english has not passed");
        }
    }

}
```

### if···else if多分支语句

​ if···else if多分支语句用于针对某一事件的多种情况进行处理。通常表现为“如果满足某种条件”，就进行某种处理，否则，如果满足另一种条件，则进行另一种处理。

```java
/**
输出
x的值大于30但小于60
**/
public class GetTerm {

    public static void main(String[] args) {
        int x = 40;

        if(x > 60) {
            System.out.println("x的值大于60");
        } else if (x > 30) {
            System.out.println("x的值大于30但小于60");
        } else if (x > 0) {
            System.out.println("x的值大于0但小于30");
        } else {
            System.out.println("x的值小于等于0");
        }
    }

}
```

### switch多分支语句

​ switch语句是一种比较简单明了的多选一的选择，在Java语言中，可以用switch语句将动作组织起来进行多选一。

```java
switch(表达式)
{ 
 case 常量值1:
        语句块1
        [break;]
...
case 常量值n:
        语句块2
        [break;]
default:
        语句块 n+1;
        [break;]
}
```

​ switch语句中表达式的值必须是**整型或字符型**，常量值1~n必须也是整型或字符型。

​ 首先switch语句先计算表达式的值，如果表达式的值与case后的常量值相同，则执行该case后的若干个语句，直到遇到break语句为止。如果没有break，则继续执行下一case中的若干语句，直到遇到break为止。若没有一个常量的值与表达式的值相同，则执行default后面的语句。default语句可选，如果不存在default语句，而且switch语句中的表达式的值与任何case的常量值都不相同，则switch不做任何处理。并且，同一个switch语句，case的常量值必须互不相同。

```java
import java.util.Scanner;

//用switch语句打印出星期的英文单词
public class GetSwitch {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.print("请输入今天星期几：");
        int week = scan.nextInt();

        switch (week) {
        case 1:
            System.out.println("Monday");
            break;
        case 2:
            System.out.println("Tuesday");
            break;
        case 3:
            System.out.println("Wednesday");
            break;
        case 4:
            System.out.println("Thursday");
            break;
        case 5:
            System.out.println("Friday");
            break;
        case 6:
            System.out.println("Saturday");
            break;
        case 7:
            System.out.println("Sunday");
            break;
        default:
            System.out.println("Sorry,I don't konw");
            break;
        }
    }

}
```

## 循环语句

​ 循环语句就是在满足一定条件的情况下反复执行某一个操作。包括while循环语句、do···while循环语句和for循环语句。

### while循环语句

​ while循环语句的循环方式为利用一个条件来控制是否要继续反复执行这个语句。

```java
//1～10相加求和
public class GetSum {

    public static void main(String[] args) {
        int x = 1;            // 定义初值
        int sum = 0;        // 定义求和变量，用于存储相加后的结果

        while(x <= 10) {
            sum += x;        // 循环相加，也即    sum = sum + x;
            x++;
        }
        System.out.println(sum);
    }

}
```

### do···while循环语句

​ do···while循环语句与while循环语句的区别是，while循环语句先判断条件是否成立再执行循环体，而do···while循环语句则先执行一次循环后，再判断条件是否成立。也即do···while至少执行一次。

```java
do
{
    执行语句
}  while (条件表达式);
```

```java
/**
输出
b == 10
**/
public class Cycle {

    public static void main(String[] args) {
        int a = 10;
        int b = 10;

        // while循环语句
        while(a == 8) {
            System.out.println("a == " + a);
            a--;
        }

        // do···while循环语句
        do {
            System.out.println("b == " + b);
            b--;
        } while(b == 8);
    }

}
```

### for循环语句

​ for循环语句是Java程序设计中最有用的循环语句之一。一个for循环可以用来重复执行某条语句，知道某个条件得到满足。

```java
for(表达式1; 表达式2; 表达式3)
{
    语句序列
}
```

​ 其中，表达式1为初始化表达式，负责完成变量的初始化；表达式2为循环条件表达式，指定循环条件；表达式3为循环后操作表达式，负责修整变量，改变循环条件。三个表达式间用分号隔开。

```java
//用for循环语句求100以内所有偶数的和。
public class Circulate {

    public static void main(String[] args) {
        int sum = 0;

        for(int i=2; i<=100; i+=2) {
            sum += i;
        }

        System.out.println(sum);
    }

}
```

​ 说到for循环语句就不得提到foreach语句了，它是Java5后新增的for语句的特殊简化版本，并不能完全替代for语句，但所有foreach语句都可以改写为for语句。foreach语句在遍历数组等时为程序员提供了很大的方便。

```java
for(元素变量x : 遍历对象obj) {
    引用了x的Java语句;
}
```

```java
int array[] = {7, 8, 9};

for (int arr : array) {
     System.out.println(arr);
}
```

## 跳转语句

​ Java语言提供了三种跳转语句，分别是break语句、continue语句和return语句。

### break语句

​ break语句刚刚在switch中已经见过了，是用来中止case的。实际上break语句在for、while、do···while循环语句中，用于强行退出当前循环，为什么说是当前循环呢，因为break只能跳出离它最近的那个循环的循环体，假设有两个循环嵌套使用，break用在内层循环下，则break只能跳出内层循环。

```java
for(int i=0; i<n; i++) {    // 外层循环
    for(int j=0; j<n ;j++) {    // 内层循环
        break;
    }
}
```

### continue语句

​ continue语句只能用于for、while、do···while循环语句中，用于让程序直接跳过其后面的语句，进行下一次循环。

```java
//输出10以内的所有奇数
public class ContinueDemo {

    public static void main(String[] args) {
        int i = 0;

        while(i < 10) {
            i++;

            if(i%2 == 0) {    // 能被2整除，是偶数
                continue;    // 跳过当前循环
            }

            System.out.print(i + " ");
        }
    }

}
```

### return语句

​ return语句可以从一个方法返回，并把控制权交给调用它的语句。

```java
//用于获取姓名，当调用这个方法时将返回姓名值。
public void getName() {
    return name;
}
```

