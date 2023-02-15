# 04-运算符与表达式

## 表达式

表达式是由变量、常量和运算符的组合，它执行计算并返回计算结果。在表达式中运算符作用的变量或常量称为操作数。

## 运算符分类

* 算术运算符
* 关系运算符
* 位运算符
* 逻辑运算符
* 赋值运算符
* 其他运算符
  * 条件运算符
  * instanceof 运算符

## 算术运算符

| 操作符 | 描述 | 例子 |
| :--- | :--- | :--- |
| + | 加法 - 相加运算符两侧的值 | A + B 等于 30 |
| - | 减法 - 左操作数减去右操作数 | A – B 等于 -10 |
| \* | 乘法 - 相乘操作符两侧的值 | A \* B等于200 |
| / | 除法 - 左操作数除以右操作数 | B / A等于2 |
| ％ | 取余 - 左操作数除以右操作数的余数 | B%A等于0 |
| ++ | 自增: 操作数的值增加1 | B++ 或 ++B 等于 21（区别详见下文） |
| -- | 自减: 操作数的值减少1 | B-- 或 --B 等于 19（区别详见下文） |

## 关系运算符

| 运算符 | 描述 | 例子 |
| :--- | :--- | :--- |
| == | 检查如果两个操作数的值是否相等，如果相等则条件为真。 | （A == B）为假。 |
| != | 检查如果两个操作数的值是否相等，如果值不相等则条件为真。 | （A != B）为真。 |
| &gt; | 检查左操作数的值是否大于右操作数的值，如果是那么条件为真。 | （A&gt; B）为假。 |
| &lt; | 检查左操作数的值是否小于右操作数的值，如果是那么条件为真。 | （A &lt;B）为真。 |
| &gt;= | 检查左操作数的值是否大于或等于右操作数的值，如果是那么条件为真。 | （A&gt; = B）为假。 |
| &lt;= | 检查左操作数的值是否小于或等于右操作数的值，如果是那么条件为真。 | （A &lt;= B）为真。 |

## 位运算符

| 操作符 | 描述 | 例子 |
| :--- | :--- | :--- |
| ＆ | 如果相对应位都是1，则结果为1，否则为0 | （A＆B），得到12，即0000 1100 |
| \| | 如果相对应位都是 0，则结果为 0，否则为 1 | （A \| B）得到61，即 0011 1101 |
| ^ | 如果相对应位值相同，则结果为0，否则为1 | （A ^ B）得到49，即 0011 0001 |
| 〜 | 按位取反运算符翻转操作数的每一位，即0变成1，1变成0。 | （〜A）得到-61，即1100 0011 |
| &lt;&lt; | 按位左移运算符。左操作数按位左移右操作数指定的位数。 | A &lt;&lt; 2得到240，即 1111 0000 |
| &gt;&gt; | 按位右移运算符。左操作数按位右移右操作数指定的位数。 | A &gt;&gt; 2得到15即 1111 |
| &gt;&gt;&gt; | 按位右移补零操作符。左操作数的值按右操作数指定的位数右移，移动得到的空位以零填充。 | A&gt;&gt;&gt;2得到15即0000 1111 |

## 逻辑运算符

| 操作符 | 描述 | 例子 |
| :--- | :--- | :--- |
| && | 称为逻辑与运算符。当且仅当两个操作数都为真，条件才为真。 | （A && B）为假。 |
| \| \| | 称为逻辑或操作符。如果任何两个操作数任何一个为真，条件为真。 | （A \| \| B）为真。 |
| ！ | 称为逻辑非运算符。用来反转操作数的逻辑状态。如果条件为true，则逻辑非运算符将得到false。 | ！（A && B）为真。 |

## 赋值运算符

| 操作符 | 描述 | 例子 |
| :--- | :--- | :--- |
| = | 简单的赋值运算符，将右操作数的值赋给左侧操作数 | C = A + B将把A + B得到的值赋给C |
| + = | 加和赋值操作符，它把左操作数和右操作数相加赋值给左操作数 | C + = A等价于C = C + A |
| - = | 减和赋值操作符，它把左操作数和右操作数相减赋值给左操作数 | C - = A等价于C = C - A |
| \* = | 乘和赋值操作符，它把左操作数和右操作数相乘赋值给左操作数 | C  _= A等价于C = C_  A |
| / = | 除和赋值操作符，它把左操作数和右操作数相除赋值给左操作数 | C / = A，C 与 A 同类型时等价于 C = C / A |
| （％）= | 取模和赋值操作符，它把左操作数和右操作数取模后赋值给左操作数 | C％= A等价于C = C％A |
| &lt;&lt; = | 左移位赋值运算符 | C &lt;&lt; = 2等价于C = C &lt;&lt; 2 |
| &gt;&gt; = | 右移位赋值运算符 | C &gt;&gt; = 2等价于C = C &gt;&gt; 2 |
| ＆= | 按位与赋值运算符 | C＆= 2等价于C = C＆2 |
| ^ = | 按位异或赋值操作符 | C ^ = 2等价于C = C ^ 2 |
| \| = | 按位或赋值操作符 | C \| = 2等价于C = C \| 2 |

## 条件运算符

条件运算符也被称为三元运算符。该运算符有3个操作数，并且需要判断布尔表达式的值。该运算符的主要是决定哪个值应该赋值给变量。

```java
variable x = (expression) ? value if true : value if false
```

## instanceof 运算符

该运算符用于操作对象实例，检查该对象是否是一个特定类型（类类型或接口类型）。

```java
( Object reference variable ) instanceof  (class/interface type)
```

## 运算符优先级

| 类别 | 操作符 | 关联性 |
| :--- | :--- | :--- |
| 后缀 | \(\) \[\] . \(点操作符\) | 左到右 |
| 一元 | expr++ expr-- | 从左到右 |
| 一元 | ++expr --expr + - ～ ！ | 从右到左 |
| 乘性 | \* /％ | 左到右 |
| 加性 | + - | 左到右 |
| 移位 | &gt;&gt; &gt;&gt;&gt;  &lt;&lt; | 左到右 |
| 关系 | &gt; &gt;= &lt; &lt;= | 左到右 |
| 相等 | == != | 左到右 |
| 按位与 | ＆ | 左到右 |
| 按位异或 | ^ | 左到右 |
| 按位或 | \| | 左到右 |
| 逻辑与 | && | 左到右 |
| 逻辑或 | \| \| | 左到右 |
| 条件 | ？： | 从右到左 |
| 赋值 | = + = - = \* = / =％= &gt;&gt; = &lt;&lt; =＆= ^ = \| = | 从右到左 |
| 逗号 | ， | 左到右 |
