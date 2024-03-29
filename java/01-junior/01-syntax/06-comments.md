# 06-注释和分隔符

## 注释

​ 程序中的注释没有逻辑意义，但是又是十分重要的程序组成成分。恰当地书写注释可以增强程序的可读性，提高理解计算机程序的效率，降低程序维护的代价。

### 分类

* 单行注释 //
* 多行注释 /\*\*/
* 文档注释 javadoc

## 分隔符

​ Java语言里的分号\(;\)、花括号\({}\)、方括号\(\[\]\)、圆括号\(\(\)\)、空格、圆点\(.\)都具有特殊的分隔作用， 因此被统称为分隔符。

### 分类

* 分号：Java语言里对语句的分隔不是使用回车来完成的，java语言采用分号\(;\)作为语句的分隔，因此每个java语句必须使用分号作为结尾。

> 注意：java语句可以跨越多行书写，但字符串和变量名不能跨越多行。虽然java语法允许一行书写多个语句但从程序可读性角度来看， 应该避免在一行书写多个语句

* 花括号：花括号的作用就是定义一个代码块，一个代码块指的就是”{”和”}”所包含的一段代码，代码块在逻辑上是一个整体。花括号一般是成对出现的，有一个“{”则必然有一个”}”，反之亦然。
* 方括号：方括号的主要作用是用于访问数组元素，方括号通常紧跟数组变量名，而方括号里指定希望访问的数组元素的索引
* 圆括号：圆括号是一个功能非常丰富的分隔符：定义方法时必须使用圆括号来包含所有的形参声明，调用方法时也必须使用圆括号来传入实参值；等等
* 空格：Java语言里使用空格分隔一条语句的不同部分。Java语言是一门格式自由的语言，所以空格几乎可以出现在java程序的任何部分，也可以出现任意多个空格，但不要使用空格把一个变量名隔开成两个，这将导致程序出错。

> Java语言中的空格包含空格符\(Space\)、制表符\(Tab\)、和回车\(Enter\)等。除此之外，Java源程序还会使用空格来合理缩进java代码，从而提供更好的可读性。

* 圆点：圆点（.）通常用做类/对象和它的成员（包括Field、方法和内部类）之间的分隔符，表明调用某个类或某个实例的指定成员。

