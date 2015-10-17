后端开发面试题
===================


#后端开发面试知识点大纲：
##语言类（C++）：
###关键字作用解释：
volatile是干啥用的

	告诉编译器此处必须得从地址去取,不得作相关优化
	
static const ，
			
const的含义及实现机制，

extern c，
			
宏定义和展开、内联函数，

global,static

###库函数实现：
malloc,strcpy,strcmp的实现，常用库函数实现，哪些库函数属于高危函数
###STL原理及实现：
STL各类型容器实现，STL共有六大组件

什么是“标准非STL容器”？

###虚函数：
虚函数的作用和实现原理，什么是虚函数,有什么作用? 
			
虚函数实现原理:包括虚函数表、虚函数指针等 
			
衍生问题:为什么 C++里访问虚函数比访问普通函数慢? 
			
为什么需要虚析构函数?

内联函数、构造函数、静态成员函数可以是虚函数吗?
			
构造函数中可以调用虚函数吗?
			
为什么需要虚继承?虚继承实现原理解析，

父类的析构函数为什么要定义为虚函数

###设计模式：
C++单例模式写法，

如何定义一个只能在堆上定义对象的类?栈上呢

###内存分配：
c++运行时各类型内存分配（堆，栈，静态区，数据段，BSS，ELF），BSS段，
sizeof一个类求大小（字节对齐原则）、
			
多重类构造和析构的顺序，C++四种强制类型转换，
			
int char float,long long long类型长度
###指针：

防止指针的越界使用，

什么是指针退化及防止、

指针的移动问题，
			
Const,volatile修饰指针的含义，
			
堆和栈上的指针，
			
指针的释放及内存泄露原因，

指针作为函数的参数，函数指针，
			
指针和引用及地址的区别，数组名，

迭代器与普通指针有什么区别

智能指针的原理,
		其他：override和overload的区别，写string类的构造，析构，拷贝函数
		
##数据结构算法：

链表、树、哈希表、有效避免hash结果值的碰撞

排序算法性能比较
		
##操作系统：

linux的内存管理机制，内存寻址方式，什么叫虚拟内存，内存调页算法，任务调度算法、
		
进程和线程、进程间及线程通信方式、共享内存的使用实现原理

死锁必要条件及避免算法、
		
动态链接和静态链接的区别、
		
c程序辨别系统是16位or32位,大端or小端字节序、

常见的信号、系统如何将一个信号通知到进程、
		
linux系统的各类同步机制、linux系统的各类异步机制、
		
如何实现守护进程
		
标准库函数和系统调用的区别，
		
fd和PCB，
		
32位系统一个进程最多有多少堆内存，
		
五种I/O 模式，

Apache 模型（Process Per Connection，简称PPC），TPC（ThreadPer Connection）模型，以及 select 模型和 poll 模型，epoll模型

惊群现象，

块设备和字符设备有什么区别，

用户态和内核态的区别
		
##网络：
TCP和UDP区别、
		
TCP和UDP头部字节定义，
		
TCP和UDP三次握手和四次挥手状态及消息类型,
		
time_wait，close_wait状态产生原因，keepalive，
		
什么是滑动窗口，超时重传，
		
列举你所知道的tcp选项，
		
connect会阻塞检测及防止，socket什么情况下可读？
		
长连接和短连接, 
		
DNS和HTTP协议，HTTP请求方式，
		
cookie,session,localstroage,
		
一致性哈希负载均衡，
		
描述在浏览器中敲入一个网址并按下回车后所发生的事情，
		
##数据库：
谈谈你对数据库中索引的理解，索引和主键区别

现在普通关系数据库用得数据结构是什么类型的数据结构，
		
索引的优点和缺点，
		
关系型数据库和非关系数据库的特点，
		
乐观锁与悲观锁的区别，

数据库范式
	
##海量数据处理：
bitmap

Map-Reduce原理，

BloomFilter原理、

Trie树原理、

B+树原理，

LSM树原理,

大数据处理
	
##工具：
编译工具GCC，调试工具GDB，性能优化工具Perf,内存泄露检查工具Valgrind,makefile编写
其他工具: netstat,ps,top,df,fdisk,lsof，ifconfig,uname,kill，tcpdump，ipcs，grep
	
##其他：安全，加密方式（DES，SHA）
	
附：[软件开发者面试百问](http://blog.csdn.net/programmer_editor/article/details/4004408)
#相关书籍

	语言类：
	C:C程序设计语言（K&R）->C和指针->C专家编程->C陷阱与缺陷->你必须知道的495个C语言问题
	C++: C++ primer -> effective C++->深度探索C++对象模型 ->stl源码分析->C++必知必会
	java：java编程思想->java并发编程->深入理解Java虚拟机：JVM高级特性与最佳实践
	 
	算法和数据结构：
	算法导论->数据结构与算法分析(维斯)->编程之美->剑指offer
	 
	操作系统：
	深入理解计算机操作系统->编译原理（龙书）
	鸟哥的linux私房菜->linux内核设计与实现->深入理解linux内核
	linux shell脚本攻略（短小精悍）
	
	网络编程： 
	TCP/IP协议详解v1->
	unix高级环境编程->
	unix网络编程（卷1&卷2）->
	unix编程艺术(进阶)
	
	视野：
	大型网站技术架构：核心原理与案例分析，
	深入理解nginx：模块开发与架构解析，
	大规模分布式存储系统 : 原理解析与架构实战
	
	其他：
	程序员自我修养，
	重构，
	编写可读代码的艺术，
	headfirst设计模式
	
#相关网络资源

	Coolshell：http://coolshell.cn/
	Matrix67大牛的博客：http://www.matrix67.com/blog/。
	July的CSDN博客：http://blog.csdn.net/v_JULY_v。
	何海涛博客：http://zhedahht.blog.163.com/。
	笔试面试的经典：Cracking the coding interview--问题与解答：
	http://hawstein.com/posts/ctci-solutions-contents.html
	LeetCode：http://leetcode.com/
	这里有不少笔试题集锦：http://blog.csdn.net/hackbuteer1
	程序员编程艺术：面试和算法心得http://taop.marchtea.com/
	
	
	
#本文参考资料
	
	江南烟雨 http://blog.csdn.net/xiajun07061225/article/details/12844801
	胡成 腾讯后台开发面试题及答案（不好意思找不到原作者链接，知道的麻烦说下）
	


