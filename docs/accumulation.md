### ***String、StringBuffer和StringBuilder之间的区别？***

##### 	String 的值是不可变的，每次对String的操作都会产生新的 String 对象，效率低下且会浪费内存空间。

#####     StringBuffer 是可变类和线程安全的多线程字符串操作类，任何对它指向的字符串的操作都不会产生新的对象。

#####     StringBuilder 是可变类和线程不安全的单线程操作字符串类，速度更快。

####  ***StringBuilder为什么线程不安全？***

#####     String、StringBuilder 和 StringBuffer 的内部实现一致，都是通过一个 char 数组存储字符串，不同的是 String 中的 char 数组是 final 修饰的，是不可变的。而 StringBuilder 和 StringBuffer 自身的 append() 方法内都使用了继承自 AbstractStringBuilder 的 append() 方法，但是StringBuffer 在 append() 上加了 synchronized 关键字，StringBuilder 没有。

