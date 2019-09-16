---
layout:	post
title:	"线程和进程"
date:	2019-08-07
Author: chinaxjk
tags:	[面试题]
comments: true
toc: true
pinned: true
---
1. # 什么是进程和线程
	
	+ 进程是资源分配的基本单位，是正在执行的应用程序
	+ 线程是cpu独立运行和独立调用的基本单位
	+ 两者的联系： 进程和线程都是操作系统所运行的基本单位

2. # 线程和进程区别

	+ 进程有独立的空间地址，一个进程崩溃后，在保护模式下不会对其他进程产生影响
	+ 线程没有单独空间地址，但是线程有单独的栈内存用来存储本地数据，一个线程死了整个进程也会瘫痪
	+ 进程是执行中的程序，线程是进程的一个序列，一个进程可以有多个线程，线程又称为量化的进程

3. # 创建线程 几种方式

	+ 两种方式：
		+ 第一种继承 Thread
		+ 实现Runable 接口
		+ 使用FutureTask 实现又返回结果的线程
		+ 使用ExecutorService，Executors线程池

4. # 死锁如何避免

	+ 互斥条件：一个资源每次只能被一个进程使用
	+ 请求与保持条件：一个进程因请求资源而堵塞时，对已获取资源保持不放
	+ 不剥夺条件：进程已获取资源，在未使用完之前，不能强行剥夺
	+ 循环等待条件：首尾相接等待资源

	> 只要避免其中的一个条件，就可以防止死锁，其中最简单就是破坏循环等待条件

5. # java中活锁与死锁有什么区别？
	
	+ 活锁和死锁类似，不同之处在于活锁线程或进程的状态是不断改变，活锁可以认为是一种特殊的饥饿。主要区别是，前者进程状态可以改变，但是却不能继续执行。

6. # 如何检测一个线程是否拥有锁？

	+ 在java.lang.Thread中有一个方法叫holdsLock（），他饭后 true 如果当且仅当线程拥有某个具体对象的锁。

7. # 遵循多线程最佳实践

	+ 给线程起个有意义的名字
	+ 避免锁定和缩小同步范围
	+ 多用同步类少用 wait 和notify
		+ 首先，CountDownLatch，Semaphore，CyclicBarrier和Exchanger 这些同步类简化操作，而用wait和notify很难实现对复杂流的控制，其次这些类都有人员在维护和优化


> 参考多个博客[链接](https://www.cnblogs.com/kexianting/p/8566318.html)


[jekyll-docs]:https://jekyllrb.com/docs/home
[jekyll-gh]:https://github.com/jekyll/jekyll
[jekyll-talk]:https://talk.jekyllrb.com
