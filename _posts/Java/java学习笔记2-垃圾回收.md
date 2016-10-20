## 垃圾回收

1. 引用计数：一种简单但是慢的垃圾回收技术，每个对象都含有一个引用计数器，当有引用连接至对象时，引用计数+1，引用离开作用域或被置于null时-1.
2. 停止-复制(stop-and-copy)：暂停程序运行，把存活的对象从当前堆复制到另一个堆，没有被复制的都是垃圾，新堆排列紧凑   不是后台进行，执行时程序会被暂停
3. 标记-清扫（mark-and-sweep）：从堆栈和静态存储区出发，遍历所有引用，找出所有存活的对象，每当找到存活对象就会给对象设一个标记，过程中不会回收对象。标记完成后，开始清理动作，没有被标记的会被释放。最后剩下的堆空间是不连续的  后台进行
4. Java虚拟机使用“自适应”技术，

## 初始化

1. 变量未初始化会报错，但是类的数据成员会被保证有一个初始值，即自动初始化（似乎以0为主）
2. 向前引用：
3. 类中，变量即使在定义时散布在方法定义之间，但是仍旧会在任何方法（包括构造器）被调用前得到初始化
4. 初始化顺序是先静态对象再非静态对象，静态初始化只执行一次

## 数组

1. int [ ] a1 = {1,2,3};      int [ ] a2;        a2 = a1 ; 此处其实是复制一个引用，a2和a1是相同数组的别名，所以操作互相可见。

2. 可变参数列表：   void printArray(Object[ ] args) {

   for (Object obj: args)

   // do something with obj

   }

   是因为所有的类都直接或间接继承与Object类的缘故

   更好的方法是：

   void printArray(Object ...args) {

   for (Object obj: args)

   // do something with obj

   }

   例如（String ...trailing)

   ​

3. 枚举

   可以把枚举当做类来使用

   声明：

   public enum Spiciness{

   NOT, MILD, MEDIUM

   }

   枚举方法：toString()、 static values() 、 ordinal()

   调用:  for (Spiciness s : Spiciness.values() ){
   System.out.print( s+ s.ordinal())

   }

   输出 NOT 0   MILD 1 MEDIUM 2

   ### 枚举与switch配合最好

   Spiciness degree;

   switch(degree){

   case NOT :  ; break;

   ……

   }

   调用： Spiciness.NOT等。