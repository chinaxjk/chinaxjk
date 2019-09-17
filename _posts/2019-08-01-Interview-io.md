---
layout: post
title:  "io流 面试题"
date:   2019-08-01
Author: chinaxjk
tags:	[面试题,java]
comments: true
toc: true
pinned: true
---
1. ## **java中有几种类型的流**

	字符流和字节流，字节流继承InputStream和OutputStream,字符流继承了InputStreamWriter和OutputStreamWriter。

2. ## **谈谈java中io里面常见的类，字符流，字节流，接口，实现类，方法阻塞**
	
	*输入流就是将外部文件输入到内存中，输出流就是将内存中的文件输出到文件*
	
	常见的类基本可以分为两大类，分别是字符和字节。字节流集成了InputStream和OutputStream，他们子类FileInputStream和FileOutputStream,BufferedOutputStread等，字符流BufferedReader和writer等。都是实现了Closeable，flushable，Appendable这些接口.程序中输入输出都是以流的形式保存的，流中保存的都是字节文件。

java堵塞是指调用该方法时候，必须等待输入数据可用或检测到输入结束或者抛出异常，否则程序会一直停留在该语句，不会执行下面语句，比如read（）和readline（）方法。

3. ## **字符流和字节流区别?**

	字节读取的时候，读到一个字节就返回一个字节，而字符流使用字节流读取到一个或多个字节（中文对应二个，UTF-8对应三个）时，先去查编码表，返回指定的字符。

	字节可以处理所有类型如：MP3 AVI视频，图片；而字符只能处理纯文本数据。如果处理纯文本数据，优先考虑字符流，其他情况都是用字节流，字节流操作以byte数组为准，主要操作类OutputStream和InputStream

	字符流处理的单位为两个字节的Unicode字符，分别操作字符，字符数组或字符串；而字节处理单元是一个字节，操作字节和字节数组。

4. ## **讲讲NIO**

	NIO 是一种同步非阻塞的I/O模型，将多个IO的堵塞复用到同一个select的阻塞上，从而使系统在单线程的情况下处理多个客户端请求，NIO三个核心对象：通道 Channel ，缓冲区Buffer ，选择器 Selector

	+ NIO线程-Acceptor线程用于监听服务端，接受客户端tcp请求
	+ 网络IO读写等由一个NIO线程池负责，线程池采用标准JDK线程池实现的，它包含一个任务队和N个可用的线程，由这些NIO线程负责消息的读取，解码，编码和发送。
	+ 一个NIO线程可以同时处理N条链路，但是一个链路只对应一个NIO线程，防止发生并发操作

> 参考部分博客
