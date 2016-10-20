---
layout: post
title:  "python"
date:   2016-10-09 16:21:22
categories: Git
comments: true
---

1. 包访问权限：可以访问一个包里其他类的成员，但是对于包外的东西，默认像private一样

2. 非面向对象语言：前期绑定         面向对象语言：后期绑定，像对象发送消息时，被调用的代码直到运行时才能确定，编辑器保证被调用方法的存在，并对调用参数和返回值执行类型检查

3. 向上转型：定义：doSomething(Shape shape)    调用： doSomething(circle) ;  doSomething(line)

4. 单根继承结构：Java中所有类都继承自Object

5. Java的存储方式：

   ​	5.1: 寄存器（位于处理器内部，不能直接控制） 

   ​	5.2: 堆栈：位于通用RAM（随机访问存储器），堆栈指针向下移动，分配新内存，向上移动，释放内存

   ​	5.3：堆，位于RAM，存放所有Java对象

6. 基本类型：不用new来创建变量，而是创建一个非引用的“自动”变量，直接存储“值”并置于堆栈中，因此更加高效。

7. 方法签名 == 方法名+参数列表

   基本类型作为参数传递时，是传递值的拷贝，无论你怎么改变这个拷贝，原值是不会改变的

   Java中对象作为参数传递时，是把对象在内存中的地址拷贝了一份传给了参数，类似于引用传递

   具体例子见http://blog.csdn.net/witsmakemen/article/details/7319594

8. 一次导入某个包的一群类： import java.util.*

9. java包命名规范：

10. static对每个类有一份存储空间，非static对每个对象有一个存储空间，static不用创建对象即可调用

11. javadoc: /**   */

12. 别名问题：对对象赋值的时候，如果将一个对象赋值给另一个对象，如c=d，那么c和d都会指向原本只有d指向的对象

13. 比较两个对象：1.==、!=比较的是两个对象的引用是否相同， 对象1.equals(对象2)比较的是两个对象实际内容是否相同，但是注意，equals（）默认比较的是引用，Integer等基本类型比较内容可以直接用，自己定义的类需要覆盖equals()

14. 指数： 1.37*10的(-43次方)： 1.39e-43f

15. 三元操作符： booleab-exp? : value1  : value0    -> 布尔结果为true就计算value1， 错误就计算value0

16. 截尾：float或double转型为整数时，截尾，即（int）29.7 == 29   如果想四舍五入则需要java.lang.Math中的round()

17. for each语法：float f[] = new float[10]     for(float x: f)

18. break和continue: break强行退出循环，不执行循环中剩余的语句，continue停止执行当前的迭代，返回循环开始处开始下一次迭代

   标签： label1：    outer-iteration{

   innner-iteration

   //...

   break;

   //...

   continue;

   //...

   continue label1;

   //...

   break label1;

   }

一般的continue还会退回最内层循环的开头（顶部），并继续执行

带标签的continue会到达标签的位置，并重新进入紧接在那个标签后面的循环

一般的break会中断并跳出当前循环

带标签的break会跳出标签所指的循环 

19. switch只对Int和char这样的整数值有用，对浮点数和字符串没有用

20. this：1. 返回当前对象的引用，如: {return Peeler.peel(this)}

    ​          2.在构造器中使用构造器  this(s), 每次只能调用一个构造器，构造器只能放到最起始处