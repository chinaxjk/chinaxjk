---
layout:	post
titile:	"java基础面试题"
date:	2019-09-08
Author: chinaxjk
tags:	[面试题,java]
comments: true
toc: true
pinned: true
---

## 一.  **java基础**

1. > jkd 和 jre有什么区别？

	+ jdk 是开发环境 运行环境 是程序开发需要安装的 里面包含了jre,
	+ jre 是程序运行环境

2. > == 于equals 区别？

	+ == 比较的是对象地址是否相同，equals 比较的是对象的值是否相同，（拓展：包装类和基础类型不能够直接比较，入 long类型与Long ，Integer与Int类型）

3. > 两个对象的hashcode（）相同，则equals也已定为true吗？

	* hashcode 相同 equals不一定为true，equals相同那他们的hashcode也一定相同。

4. > final 在java中有什么作用？

	* final 不可变的，修饰变量那变量就不变，修饰方法，那方法就不能被调用，修饰类，那么累就不能被继承

5. > java 中的 Math.round(-1.5)等于多少？

	* -2,解释 Math.round是表示上取整

6. > string 属于基础数据类型吗？

	* 不属于，string底层是通过char来实现的	

7. > java中操作字符串都有哪些类？他们之间有什么区别？

	* String 是final 修饰，表示不可变，若修改则会产生新的对象
	* StringBuffer 字符串可以改变，且线程安全的，执行效率比较慢
	* StringBuilder 字符串可以改变，线程不安全，执行效率比快

8. > String str = “i” 与String str = new String（“i”）一样吗？

	* 不一样，这表示两个对象，对象地址不同

9. > 如何将字符串反转？

	* reverse().toString();

10. > String 类常用的方法有那些？

	+ String concat(String str)将指定字符串连接到此字符串的结尾。
	+ boolean endsWith(String suffix)测试此字符串是否已指定的后缀结束。
	+ boolean equals(Object anObject)将此字符串与指定对象比较。
	+ int hashcode(String str)返回字符串hashcode	
	+ Int indexof(String str)返回指定子字符串在此字符串中第一次出现的索引，从指定索引开始。

11. > 抽象类必须有抽象方法吗？

	+ 抽象类不一定有抽象方法，有抽象方法的类一定都是抽象类	

12. > 普通的类和抽象类有哪些区别？

	1. 抽象类不能被实例化
	2. 抽象类可以有构造函数，抽象方法不能被声明为静态
	3. 抽象方法只需要申明，而不需实现，抽象类中可以允许普通方法有主体
	4. 含有抽象方法的类必须申明为抽象类
	5. 抽象的子类必须实现抽象类中所有的抽象方法，否则子类也是抽象类

13. > 抽象类能使用fenal修饰吗？

	* 不能 ，抽象类是被用于继承，final修饰代表不能修改，所以不能。

14. > 接口和抽象类有什么区别？

	+ 抽象类中可以定义构造器，接口不能
	+ 抽象类可以有抽象方法和具体方法，接口方法全部都是抽象的
	+ 抽象类成员可以是private,默认，protected,public ;接口只能是public
	+ 抽象类可以定义成员变量；借口中定义都是常量
	+ 有抽象方法的类必须被称为抽象类，而抽象类不是必须有抽象方法；接口中不能有静态方法
	+ 抽象类可以包括静态方法；一个类可以实现多个借口，但最多只能继承一个类

15. > java 中io 流分为几种？

	+ 按照流的方向 分为： inputStream and outputStream
	+ 按照实现功能 分为： 节点流 和 处理流
	+ 按照处理单位 分为： 字节流（InputStream OutputStream）和字符流（InputStreamReader 和 OutputStreamWriter）

16. > BIO NIO AIO 有什么区别？
	
	+ BIO 
		- 同步阻塞I/O模式，数据的读取写入必须阻塞在一个线程内等待其完成。 
		- 在活动连接数不是特别高（小于单机1000）的情况下，这种模型是比较不错的，可以让每一个连接专注于自己的 I/O 并且编程模型简单，也不用过多考虑系统的过载、限流等问题。线程池本身就是一个天然的漏斗，可以缓冲一些系统处理不了的连接或请求。但是，当面对十万甚至百万级连接的时候，传统的 BIO 模型是无能为力的。因此，我们需要一种更高效的 I/O 处理模型来应对更高的并发量。
	+ NIO
		- NIO是一种同步非阻塞的I/O模型
		- NIO中的N可以理解为Non-blocking，不单纯是New。它支持面向缓冲的，基于通道的I/O操作方法。 NIO提供了与传统BIO模型中的 Socket 和 ServerSocket 相对应的 SocketChannel 和 ServerSocketChannel 两种不同的套接字通道实现,两种通道都支持阻塞和非阻塞两种模式。阻塞模式使用就像传统中的支持一样，比较简单，但是性能和可靠性都不好；非阻塞模式正好与之相反。对于低负载、低并发的应用程序，可以使用同步阻塞I/O来提升开发速率和更好的维护性；对于高负载、高并发的（网络）应用，应使用 NIO 的非阻塞模式来开发。
	+ NIO 和 IO区别
		- IO流是阻塞的，NIO流是不阻塞的。
		- IO 面向流（Stream Oriented) 而NIO面向缓冲区Buffer oriented)
		- Channel (通道)NIO 通过Channel（通道） 进行读写。通道是双向的，可读也可写，而流的读写是单向的。无论读写，通道只能和Buffer交互。因为 Buffer，通道可以异步地读写。	
		- Selector (选择器)NIO有选择器，而IO没有。选择器用于使用单个线程处理多个通道。因此，它需要较少的线程来处理这些通道。线程之间的切换对于操作系统来说是昂贵的。 因此，为了提高系统效率选择器是有用的。
	+ AIO 也就是 NIO 2。在 Java 7 中引入了 NIO 的改进版 NIO 2,它是异步非阻塞的IO模型。异步 IO 是基于事件和回调机制实现的，也就是应用操作之后会直接返回，不会堵塞在那里，当后台处理完成，操作系统会通知相应的线程进行后续的操作。

AIO 是异步IO的缩写，虽然 NIO 在网络操作中，提供了非阻塞的方法，但是 NIO 的 IO 行为还是同步的。对于 NIO 来说，我们的业务线程是在 IO 操作准备好时，得到通知，接着就由这个线程自行进行 IO 操作，IO操作本身是同步的。（除了 AIO 其他的 IO 类型都是同步的，这一点可以从底层IO线程模型解释，推荐一篇文章：《漫话：如何给女朋友解释什么是Linux的五种IO模型？》 ）

17. > Files 的常用方法都有哪些？

	+ File()：构造函数，一般是依据文件所在的指定位置来创建文件对象。  
	+ CanWrite()：返回文件是否可写。  
	+ CanRead()：返回文件是否可读。 
	+ CompareTo(File pathname)：检查指定文件路径间的顺序。 
	+ Delet()：从文件系统内删除该文件。 
	+ DeleteOnExit()：程序顺利结束时从系统中删除文件。 
	+ Equals(Object obj)：检查特定对象的路径名是否相等。 
	+ Exists()：判断文件夹是否存在。 
	+ GetAbsoluteFile()：返回文件的完整路径。 
	+ GetAbsolutePath()：返回文件的完整路径。 
	+ GetName()：返回文件名称。 
	+ GetParent()：返回文件父目录路径。 
	+ GetPath()：返回文件的潜在相对路径。 
	+ GetParentFile()：返回文件所在文件夹的路径。 
	+ HashCode()：返回文件哈希码。 
	+ IsDirectory()：判断该路径指示的是否是文件。 
	+ IsFile()：判断该路径指示的是否是文件。 
	+ LastModified() ：返回文件的最后修改时间标志。 
	+ Length()：返回文件长度。 
	+ List()：返回文件和目录清单。 
	+ Mkdir()：生成指定的目录。 
	+ RenameTo(File dest)：更名文件。 
	+ SetReadOnly()：将文件设置为可读。 
	+ ToString()：返回文件状态的字符串。 
	+ ToURL()：将文件的路径字符串转换成URL 

## 二. **容器**

18. > java容器有哪些？

	1. List:存放有序,列表存储,元素可重复

		* ArrayList，擅长随机访问元素，但是插入、删除元素较慢
		* LinkedList,擅长插入、删除和移动元素，但是随机访问元素性能较低。
		* listlterator ListIterator是更为强大的Iterator的子类型，但是它仅仅针对List的类进行访问。ListIterator可以进行双向移动、获取迭代器所处元素的前后元素的索引，还可以使用set()方法替换它访问过的最后一个元素

	2. Set:无序,元素不可重复

		* Set底层HashMap实现

		1. HashSet，使用了散列方式进行存储。
		2. TreeSet，将元素存储在红黑数当中。它会对集合元素进行排序。
		3. LinkedHashSet，使用链表和哈希表来实现Set


	3. Map:无序,元素可重复

		* linkdHashMap,TreeHashMap底层用额外的链表和树进行维护
		* hashMap底层是用数组+链表实现

	4. stack

		* Stack实现了栈数据结构，它是一种LIFO(后进先出)的容器。也就是我们先放进栈的元素，在使用时会先获取到最后放入的元素。

19. > Collection 和 Collections 有什么区别？

	1. java.util.Collection 是一个集合接口。它提供了对集合对象进行基本操作的通用接口方法。Collection接口在java类库中有很多具体的实现。Collection接口的意义是为各种具体的集合提供了最大化的统一操作方式。
	2. java.util.Collections是一个包装类。它包含有各种有关集合操作的 静态多态方法。 此类 不能实例化，就像一个工具类，服务于java的Collection框架。	

20. > List Set Map 之间有什么区别？

	+ Collection 
		- list 对象可以重复，允许null，按顺序插入
			- ArrayList 数组形式存储，线程不同步
			- LinkedList 链表形式存储，线程不同步
			Vector stack 先进后出，线程安全
		- set 无序不重复，可用于去重，以数组的形式存储
	+ Map
		- HashMap 非线程同步，允许null，增长：2倍指数增长
		- HashTable 线程安全，不允许null，增长：n*2+1
		- TreeMap 按照键排序
		- ConcurrentHashMap 线程同步

21. > HashMap 和 Hashtable 有什么区别？
22. > 如何使用HashMap 还是TreeMap？
23. > 说说 HashMap 的实现原理？
24. > 说说 HashSet 实现原理 ？
25. > ArrayList and LinkedList 的区别是什么？
26. > 如何实现数组和List之间的转换？
27. > Array and ArrayList 有何区别？
28. > 在Queue中Poll（）和 remobe（）有什么区别？
30. > 迭代器 lterator 是什么？
31. > Interator and ListIterator 有什么区别？
33. > Interator 怎么使用？有什么特点？
34. > 则么确保一个集合不能被修改？

