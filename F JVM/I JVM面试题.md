[TOC]

### JVM面试题

##### 1. Student s = new Student(); 在内存中做了哪些事情？

1. 加载 Student.**class 文件进内存** 。
2. 在**栈内存**为 s 开辟空间 。
3. 在**堆内存**为 Student **对象开辟空间** 。
4. 对 Student 对象的成员变量进行**默认初始化** 。
5. 对 Student 对象的成员变量进行**显示初始化** 。
6. 通过**构造方法**对 Student 对象的成员变量赋值 。
7. Student 对象**初始化完毕**，把**对象地址赋值给 s 变量** 。

##### 2. JVM线程死锁，你该如何判断是因为什么？如果用VisualVM，dump线程信息出来，会有哪些信息？

常常需要在隔两分钟后再次收集一次 thread dump，如果得到的输出相同，仍然是大量 thread 都在等待给同一个地址上锁，那么肯定是死锁了。