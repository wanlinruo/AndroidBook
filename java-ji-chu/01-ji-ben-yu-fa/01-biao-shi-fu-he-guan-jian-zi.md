# 01-标识符和关键字

\[TOC\]

## 标识符

1. 在java语言中，用来标志类名、对象名、变量名、方法名、类型名、数组名、包名的有效字符序列，称为“标识符”；
2. 标识符由字母、数字、下划线、美元符号组成，且第一个字符不能是数字；
3. java语言区分大小写；
4. 标志符命名规则：类名首字母大写，变量名和方法名采用驼峰标志法，常量全大写，多个单词之间用“\_”隔开，包名全小写；

## 关键字

1. 在java语言中，有一些专门的词汇已经被赋予了特殊的含义，不能再使用这些词汇来命名标识符，这些专有词汇，称为“关键字”；
2. java有50个关键字和3个保留字，均不能用来命名标识符；

### 关键字-定义数据类型（共11个）：

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| class | 类 | public class A\(\){} 花括号里有已实现方法体，类名需要与文件名相同 |
| interface | 接口 | public interface B\(\){} 花括号里有方法体，但没有实现，方法体句子后面是英文分号“:”结尾 |
| public | 公有的 | 可跨包，（默认选择） |
| byte | 字节型 | 1字节，8bit |
| char | 字符型 | 2字节，16bit |
| boolean | 布尔型 | 1字节，8bit |
| short | 短整型 | 2字节，16bit |
| int | 整型 | 4字节，32bit |
| long | 长整型 | 8字节，64bit |
| float | 浮点型 | 4字节，32bit |
| double | 双精度 | 8字节，64bit |

### 关键字-定义数据类型值（共3个）：

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| true | 真 |  |
| false | 假 |  |
| null | 空 |  |

### 关键字-访问控制修饰符（共3个）：

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| private | 私有的 | 当前类可用 |
| protected | 受保护的 | 当前包内可用 |
| public | 公有的 | 可跨包，（默认选择） |

### 关键字-定义类，函数，变量修饰符（共4个）：

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| abstract | 声明抽象 | public abstract class C\(\){} 介于类与接口中间，可以有也可以没有已经实现的方法体 |
| final | 最终的不可被改变的 | 方法和类都可以用final来修饰 final修饰的类是不能被继承的，修饰的方法是不能被子类重写。常量的定义：final修饰的属性就是常量。 |
| static | 静态的 | 属性和方法都可以用static修饰，直接使用类名.属性和方法名。  只有内部类可以使用static关键字修饰，调用直接使用类名.内部类类名进行调用。  static可以独立存在。静态块 |
| synchronized | 线程，同步 |  |

### 关键字-定义类与类之间关系（共2个）：

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| extends | 继承 | 用于类继承类 public class A extends D\(\){} |
| implements | 实现 | 用于类或接口实现接口public class A interface B\(\){} |

### 关键字-定义建立实力及引用实力，判断实例（共4个）：

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| new | 创建新对象 | A a=new A\(\); A表示一个类 |
| this | 当前类的父类的对象 | 调用当前类中的方法（表示调用这个方法的对象） this.addActionListener\(al\):等等 |
| super | 调用父类的方法 | 常见public void paint\(Graphics g\){ super.paint\(g\); ··· } |
| instanceof | 实例 | 一个二元操作符，和==，&gt;，&lt;是同一类的。 测试它左边的对象是否是它右边的类的实例，返回boolean类型的数据 |

### 流程控制语句（共11个）:

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| break | 跳出循环 |  |
| continue | 继续 | 中断本次循环，并并开始下一次 |
| return | 返回 | return 一个返回值类型 |
| do | 运行 | 长与while连用 |
| while | 当什么的时候 | while 怎么样就do什么 while\(\){} |
| if | 如果 | if\(\){} 如果小括号里面怎么怎么样 花括号就怎么怎么样 |
| else | 否则，或者 | 常与if连用，用法相同 |
| for | 满足三个条件时 | for \( ; ; \){} |
| switch | 开关 | switch\(表达式\) { case 常量表达式1:语句1; .... case 常量表达式2:语句2; default:语句; } default就是如果没有符合的case就执行它,default并不是必须的. case后的语句可以不用大括号. switch语句的判断条件可以接受int,byte,char,short,不能接受其他类型. |
| case | 返回开关里的结果 |  |
| default | 默认 |  |

### 错误处理（共5个）:

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| try | 捕获异常 |  |
| catch | 处理异常 | 1.try+catch 程序的流程是：运行到try块中，如果有异常抛出，则转到catch块去处理。然后执行catch块后面的语句  2.try+catch+finally 程序的流程是：运行到try块中，如果有异常抛出，则转到catch块,catch块执行完毕后，执行finally块的代码，再执行finally块后面的代码。 如果没有异常抛出，执行完try块，也要去执行finally块的代码。然后执行finally块后面的语句  3.try+finally 程序的流程是：运行到try块中,如果有异常抛出的话，程序转向执行finally块的代码。那末finally块后面的代码还会被执行吗？不会！因为你没有处理异常，所以遇到异常后，执行完finally后，方法就已抛出异常的方式退出了。 这种方式中要注意的是，由于你没有捕获异常，所以要在方法后面声明抛出异常 |
| finally | 有没有异常都执行 |  |
| throw | 抛出一个异常对象 | 一些可以导致程序出问题的因素,比如书写错误,逻辑错误或者是api的应用错误等等. 为了防止程序的崩溃就要预先检测这些因素,所以java 使用了异常这个机制.  在java中异常是靠 "抛出" 也就是英语的"throw" 来使用的,意思是如果发现到什么异常的时候就把错误信息 "抛出" |
| throws | 声明一个异常可能被抛出 | 把异常交给他的上级管理，自己不进行异常处理 |

### 包的关键字（共2个）:

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| import | 引入包的关键字 | 当使用某个包的一些类时，仅需类名 然后使用ctrl+shift+o或者选定类名（类或属性或方法）按住ctrl+单击 即可自动插入类所在的包。如：JFrame 快捷键之后自动加入 import javax.swing.JFrame; |
| package | 定义包的关键字 | 将所有有关的类放在一个包类以便查找修改等。如：package javake.flycat.draw002; |

### 关键字-其他修饰符（共6个）：

| 关键字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| native | 本地 |  |
| strictfp | 严格,精准 |  |
| transient | 短暂 |  |
| volatile | 易失 |  |
| assert | 断言 |  |
| enum | 枚举 |  |

### 保留字（2个）:

| 保留字 | 意思 | 备注，常用 |
| :--- | :--- | :--- |
| goto | 跳转 |  |
| const | 静态 |  |
