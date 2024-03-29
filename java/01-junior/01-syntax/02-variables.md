# 02-常量与变量

> 在程序执行过程中，**其值不能改变的量称为常量，其值能被改变的量称为变量**。
>
> 变量与常量的声明都必须使用合法的标识符，所有变量与常量只有在声明之后才能使用。

## Java常量

常量通常也被称为“final变量”。常量在整个程序中只能被赋值一次。在为所有对象共享值时，常量是非常有用的。在Java语言中声明一个常量，除了要指定数据类型外，还需要通过final关键字进行限定。声明常量的标准语法格式如下：

```text
final 数据类型 常量名称（=值）
```

在Java编码规范中，要求常量名必须大写，并且中间最好使用下划线作为分隔符来进行连接多个单词。

当定义的常量如果属于“成员变量”，则必须在定义时就赋给初值，否则将会在编译时出先错误。

常量在程序运行过程中主要作用：

1. 代表常数，便于程序的修改，比如：圆周率的值；
2. 增强程序的可读性，比如：常量UP、DOWN、LEFT和RIGHT分辨代表上下左右，其数值分别是1、2、3和4）。

### interface中定义常量：

```java
public interface ConstantInterface {
    String SUNDAY = "SUNDAY";
    String MONDAY = "MONDAY";
    String TUESDAY = "TUESDAY";
    String WEDNESDAY = "WEDNESDAY";
    String THURSDAY = "THURSDAY";
    String FRIDAY = "FRIDAY";
    String SATURDAY = "SATURDAY";
}
```

在interface中定义的常量默认是public static final类型的。所以我们定义String SUMMER = "Summner";的时候，就相当于默认加了public static final前缀，意思与public static final String SUMMER = "Summer";等价。

在接口中定义常量，可以免去加public static final几个单词，少敲几次键盘，但可以达到同样的效果。

但是不推荐这种方式：

1. Java中设计出接口这种语法，就是为了用来实现或者继承的，如果我们在实现类或者子类接口中定义了同名的常量，那么子类接口或者实现类引用同名的常量，就可能不一致。是不是很容易造成混乱。
2. 与接口的定义不相符，接口是一种规范，一种协议规定，主要用来定义必须要实现的API。用接口来定义常量，与创造接口的目的不相符，也有点大财小用。
3. 在interface中定义的常量属于编译型常量，每次更改常量值，都要重新编译所有引用到它的类。

### enum定义常量（推荐）：

```java
enum ConstantEnum {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}
```

### 普通类中定义常量：

```java
public class ConstantClassField {
    public static final String SUNDAY = "SUNDAY";
    public static final String MONDAY = "MONDAY";
    public static final String TUESDAY = "TUESDAY";
    public static final String WEDNESDAY = "WEDNESDAY";
    public static final String THURSDAY = "THURSDAY";
    public static final String FRIDAY = "FRIDAY";
    public static final String SATURDAY = "SATURDAY";
}
```

### final class定义常量（常用）：

```java
public final class ConstantClassField {
    public static final String SUNDAY = "SUNDAY";
    public static final String MONDAY = "MONDAY";
    public static final String TUESDAY = "TUESDAY";
    public static final String WEDNESDAY = "WEDNESDAY";
    public static final String THURSDAY = "THURSDAY";
    public static final String FRIDAY = "FRIDAY";
    public static final String SATURDAY = "SATURDAY";
}
```

这种方式最常用，但这种定义也是编译型常量，如果更改常量值的话，还是需要重新编译所有引用类。

## Java变量

在Java语言中，所有的变量在使用前必须声明。声明变量的基本格式如下：

```text
type identifier [ = value][, identifier [= value] ...] ;
```

格式说明：type为Java数据类型；identifier是变量名；可以使用逗号隔开来声明多个同类型变量。

```java
int a, b, c;             // 声明三个int型整数：a、b、c
int d = 3, e = 4, f = 5; // 声明三个整数并赋予初值
byte z = 22;             // 声明并初始化z
String s = "runoob";     // 声明并初始化字符串s
double pi = 3.14159;     // 声明了双精度浮点型变量 pi
char x = 'x';            // 声明变量x的值是字符 'x'
```

变量虽然是由程序员所命名的，但是变量的命名并不是任意的，需要遵循一定的规则：

1. 变量名必须是一个有效的标识符。
2. 变量名不能重复。
3. 应选择有意义的单词作为变量名。在命名变量名时，最好能通过变量名看出变量的内容，这样既能方便读者对程序的理解，增加可读性，又方便程序的维护，减轻程序维护人员的工作负担。

> 变量的有效范围是指程序代码能够访问该变量的区域，若超出变量所在区域访问该变量则编译时会出现错误。
>
> 在程序中，一般会根据变量能够访问的区域将变量分为成员变量和局部变量。
>
> 在类体中定义的变量被称为成员变量，成员变量在整个类中都有效。
>
> 类的成员变量又分为静态变量（也称类变量）和实例变量两种。

### 局部变量（本地变量）：

1. 声明在方法、构造方法或者语句块中；
2. 在方法、构造方法、或者语句块被执行的时候创建，当它们执行完成后，变量将会被销毁；
3. 访问修饰符不能用于局部变量；
4. 只在声明它的方法、构造方法或者语句块中可见；
5. 在栈上分配的；
6. 没有默认值，所以局部变量被声明后，必须经过初始化，才可以使用。

### 实例变量：

1. 声明在一个类中，但在方法、构造方法和语句块之外；
2. 当一个对象被实例化之后，每个实例变量的值就跟着确定；
3. 在对象创建的时候创建，在对象被销毁的时候销毁；
4. 值应该至少被一个方法、构造方法或者语句块引用，使得外部能够通过这些方式获取实例变量信息；
5. 可以声明在使用前或者使用后；
6. 访问修饰符可以修饰实例变量；
7. 对于类中的方法、构造方法或者语句块是可见的，一般情况下应该把实例变量设为私有，通过使用访问修饰符可以使实例变量对子类可见；
8. 具有默认值，数值型变量的默认值是0，布尔型变量的默认值是false，引用类型变量的默认值是null。变量的值可以在声明时指定，也可以在构造方法中指定；
9. 可以直接通过变量名访问。

### 类变量（静态变量）：

1. 在类中以static关键字声明，但必须在方法构造方法和语句块之外；
2. 无论一个类创建了多少个对象，类只拥有类变量的一份拷贝；
3. 除了被声明为常量外很少使用。常量是指声明为public/private，final和static类型的变量。常量初始化后不可改变；
4. 储存在静态存储区。经常被声明为常量，很少单独使用static声明变量；
5. 在第一次被访问时创建，在程序结束时销毁；
6. 与实例变量具有相似的可见性。但为了对类的使用者可见，大多数静态变量声明为public类型；
7. 默认值和实例变量相似。数值型变量默认值是0，布尔型默认值是false，引用类型默认值是null。变量的值可以在声明的时候指定，也可以在构造方法中指定。此外，静态变量还可以在静态语句块中初始化；
8. 可以通过：ClassName.VariableName的方式访问；
9. 类变量被声明为public static final类型时，类变量名称一般建议使用大写字母。如果静态变量不是public和final类型，其命名方式与实例变量以及局部变量的命名方式一致。

```java
public class VariableType {
    //定义类变量
    public static String name = "王路情";
    //定义实例变量
    public char sex = 'M';

    public static void main(String[] args) {
        //定义局部变量  
        String string = "中国";
    }
}
```

