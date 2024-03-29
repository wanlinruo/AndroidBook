# 04-栈

## 栈的定义：

栈（英语：stack）又称为堆栈或堆叠，栈作为一种数据结构，是一种只能在一端进行插入和删除操作的特殊线性表。它按照先进后出的原则存储数据，先进入的数据被压入栈底，最后的数据在栈顶，需要读数据的时候从栈顶开始弹出数据（最后一个数据被第一个读出来）。栈具有记忆作用，对栈的插入与删除操作中，不需要改变栈底指针。

## 栈的基本特点：

1. 栈中数据是按照"后进先出（LIFO, Last In First Out）"方式进出栈的。
2. 向栈中添加/删除数据时，只能从栈顶进行操作。
3. 存取速度比堆要快，仅次于直接位于CPU中的寄存器。
4. 但缺点是，存在栈中的数据大小与生存期必须是确定的，缺乏灵活性。

## 栈的应用场景:

1. 逆序输出

   将所有元素依次压入栈中，然后依次弹出即可

2. 编译器的语法检查

   在大多数编程语言中，一般括号都是成对出现，遇到括号的左半部分，则进行入栈（push）操作，遇到括号右半部分则立即与栈顶（top）元素匹配，匹配成功则弹栈（pop），否则报错。

3. 数制转换（10进制转换任意进制）

   数制转换通常采用取余倒置，此处不再展开。

4. 方法调用

   编写的程序在进行方法（函数）调用时，CPU会完成对方法的压栈操作，等方法执行结束后，对应的CPU会完成对方法的弹栈操作。当然除此之外，cpu产生中断后，首先进行压栈操作，将打断的程序运行数据一一入栈，中断服务程序执行完后把入栈的运行数据按照相反的顺序依次出栈，恢复中断前的运行状态，CPU 开始返回中断前的地方继续运行。

## 栈的数据结构：

![&#x6808;&#x7684;&#x6570;&#x636E;&#x7ED3;&#x6784;](../../../.gitbook/assets/栈的数据结构.png)

## 栈的基本操作：

1. push -- 向栈中添加元素。
2. peek -- 返回栈顶元素。
3. pop -- 返回并删除栈顶元素的操作。

## 栈的实现（数组）：

```java
import java.util.Arrays;

public class Stack {
    private int size = 0;  //栈顶位置
    private int[] array;

    public Stack(){
        this(10);
    }
    public Stack(int init) {   
        if(init <= 0){
            init = 10;
        }
        array = new int[init];
    }

    /**
     * 入栈操作
     * @param item 入栈的元素
     */
    public void push(int item){
        if(size == array.length){
            array = Arrays.copyOf(array, size*2);   //扩容操作
        }
        array[size++] = item;
    }

    /**
     * 获取栈顶元素，但栈顶元素不出栈
     * @return 栈顶元素
     */
    public int peek(){
        if(size == 0){  //空栈
            throw new IndexOutOfBoundsException("栈是空的");
        }
        return array[size-1];
    }

    /**
     * 出栈，同时获取栈顶元素
     * @return
     */
    public int pop(){
        int item = peek();  //获取栈顶元素
        size--;  //直接使元素个数减1，不用清除元素，下次入栈会覆盖旧元素的值
        return item;
    }

    /**
     * 判断栈是否已满
     * @return
     */
    public boolean isFull(){
        return size == array.length;
    }

    /**
     * 判断栈是否为空
     * @return
     */
    public boolean isEmpty(){
        return size == 0;
    }

    public int getSize(){
        return size;
    }    
}
```

```java
public class StackTest {
    public static void main(String[] args) {
        Stack s = new Stack(3);  //设置栈的初始容量为3
        s.push(2);
        s.push(5);
        s.push(7);
        s.push(10);    //此时扩容，自底向顶 2—>5->7->10
        System.out.println("栈顶位置是："+s.getTop()); //栈顶指针为4，数组长度为3*2=6        
        System.out.println("获取栈顶元素："+s.peek());  //获取但不弹栈
        System.out.println("弹出栈顶元素："+s.pop());//弹栈返回10,自底向顶 2—>5->7
        System.out.println("弹出栈顶元素："+s.pop());//弹栈返回7,自底向顶 2—>5
        s.push(66);   //入栈后，自底向顶 2—>5->66
        System.out.println("弹出栈顶元素："+s.pop());//弹栈返回66
        System.out.println("弹出栈顶元素："+s.pop());//弹栈返回5
        System.out.println("弹出栈顶元素："+s.pop());//弹栈返回2
        System.out.println("弹出栈顶元素："+s.pop());//抛出异常，提示为空栈
    }
}
```

