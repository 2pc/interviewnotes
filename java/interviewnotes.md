
1. String类能被继承吗，为什么  
>
不能，String是final的类型类

2. HashMap是线程安全的吗,并发下使用的Map是什么，他们内部原理是什么  
>
HashMap是非线程安全的类，并发Map有ConcurrentHashMap，ConcurrentSkipListMap（key有序）

3. 多线程的几种实现方式  
>
继承Thread,  实现Runnable接口，ExecutorService,Executors,Callable,Future,ThreadPoolExecutor

4. volatile的作用，能代替锁么
>
Java 语言提供了一种稍弱的同步机制,即 volatile 变量.用来确保将变量的更新操作通知到其他线程,保证了新值能立即同步到主内存,以及每次使用前立即从主内存刷新. 当把变量声明为volatile类型后,编译器与运行时都会注意到这个变量是共享的. 非线程安全（如valatile++）

5. string和stringbuffer的区别？  
>
String final类不能被继承（String a ="aaa";假设a指向地址0x0001, a="bbb";假设a指向地址0x0005,因此String的操作都是改变赋值地址而不是改变值操作;stringbuffer 线程安全可变，如append）

6. sleep和wait的区别   
>
sleep()属于Thread，sleep()没有释放锁，；而wait()属于Object，释放锁

7. 类可以继承多个类么，接口可以继承多个接口么,类可以实现多个接口么  
>
 不能继承多个类class C extends A,B,单继承，可以通过class A extends B class C extends B 从而实现C继承A,B，可以多个实现接口），接口可以继承接口

8.抽象类和接口，可以有构造函数么，可以有main函数运行么
>
抽象类：如果一个类(class)包含一个或多个抽象方法，该类必须被限定为抽象的，可以有main函数
接口，interface关键字产生一个完全抽象的类，不提供任何具体实现，允许创建者确定方法名，参数列表，返回类型。也可以包含域（这些域隐式的是static和final的），接口不能有main函数运行（接口没有方法体）

9.对象晋升到老年代的条件是什么
>

10.Lock与synchronized 的区别
>

11.什么是自旋锁，偏向锁
12.你知道哪几种垃圾收集器，各自的优缺点
13.当出现了内存溢出，你怎么排错
14.什么是线程安全，什么是重排序
15.http1.0和http1.1有什么区别
16.TCP三次握手和四次挥手的流程，为什么断开连接要4次
17.tomcat有调优参数有哪些
18.类的实例化顺序，比如父类静态数据，构造函数，字段，子类静态数据，构造函数，字段，他们的执行顺序
19.jvm中一次完整的GC流程（从ygc到fgc）
20.spring的controller是单例还是多例，怎么保证并发的安全
21.项目中用到了缓存系统么，如何设计的，Redis的使用要注意什么，持久化方式，内存设置，集群等
23.用过哪些线程池，内部原理是什么
24.10亿个数字里里面找最小的10个
25.有一个第三方接口，有很多个线程去调用获取数据，现在规定每秒钟最多有10个线程同时调用它，如何做到。
26.分布式集群下如何做到唯一序列号
27.TIME_WAIT和CLOSE_WAIT的区别
28.数据库隔离级别有哪些，各自的含义是什么，Mysql默认的隔离级别是是什么
>
*. Read Uncommitted（读取未提交内容)   所有事务都可以看到其他未提交事务的执行结果，读取为提交的数据，也称之为脏读（Dirty Read）  
*. Read Committed（读取提交内容，读已提交)  大多数数据库系统的默认隔离级别（MySQL默认的是可重复读Repeatable Read），一个事务只能看见已经提交事务所做的改变，不可重复读，因为同一事务的其他实例在该实例处理其间可能会有新的commit，所以同一select可能返回不同结果。  
*. Repeatable Read（可重读）MySQL的默认事务隔离级别，它确保同一事务的多个实例在并发读取数据时，会看到同样的数据行；幻读 （Phantom Read），问题：幻读指当用户读取某一范围的数据行时，另一个事务又在该范围内插入了新行，当用户再读取该范围的数据行时，会发现有新的“幻影” 行。InnoDB和Falcon存储引擎通过多版本并发控制（MVCC，Multiversion Concurrency Control）机制解决了该问题。  
*. Serializable（可串行化）
![Mysql中四种隔离级别](https://github.com/2pc/interviewnotes/blob/master/images/mysql.png)
29.高并发下，如何做到安全的修改同一行数据，乐观锁和悲观锁是什么，INNODB的行级锁有哪2种，解释其含义
30.SQL优化的一般步骤是什么，怎么看执行计划，如何理解其中各个字段的含义，索引的原理？
31.设计一个秒杀系统，30分钟没付款就自动关闭交易
32.如何做一个分布式锁
33.用过哪些MQ，怎么用的，和其他mq比较有什么优缺点
34.分布式事务的原理，如何使用分布式事务
35.什么是一致性hash
36.讲讲Spring事务的传播属性
37.有1亿个数字，其中有2个是重复的，快速找到它，时间和空间要最优
38.用三个线程按顺序循环打印abc三个字母，比如abcabcabc
39.如何设计建立和保持100w的长连接？
40.解释什么是MESI协议(缓存一致性)
41.数据库事务原理，隔离
42.Arraylist与LinkedList区别
>
都不是线程安全的，ArrayList数据实现，插入和删除需要搬运数据（位置以后的都元素需要改变移动）， 随机访问效率高，简单(下标索引)。LinkedList 链表实现（双向链表找到插入元素的位置）
基础题
