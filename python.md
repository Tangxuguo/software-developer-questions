PYTHON开发面试题
===================

什么是 lambda函数？它有什么好处？另外 python在函数式编程方面提供了些什么函数和语
法？

	匿名函数Lambda 是一种单行的表达式函数，主要好处就是能简化代码，不需要定义一些简单功能的
	
	Python 中，函数可以作为参数传入，也可以作为结果被返回
	lambada 语法方便编程
	提供了以下内置函数：
	filter(function, iterable)
	map(function, iterable, ...)
	reduce(function, iterable[, initializer])
	zip([iterable, ...])
详细说说 tuple、list、dict 的用法，它们的特点；

	三者的用法可参考：http://blog.sina.com.cn/s/blog_540775a30101bhhx.html
	Tuple 一旦创建即不能进行修改(删
	除/增加/修改元素)，但是其访问效率较高，且能保护常
	量数据不被更改，所以适合于存储一些常量数据
	List 适合于需要动态增删改的数据集，但不适用于需要查找的使用；因为其实现类似于 C
	中的数组，也不适应于需要经常在 list 之间插入数据的场景。
	Dict 就像很多语言中的 hash，可能在内部使用了红黑树或者其他数据结构存储了数据，以
	达到快速定位的功能
说说 python 中装饰器、迭代器的用法；描述下 dict 的 items() 方法与 iteritems() 方法的不
同；

	装饰器即是装饰器在 python 中的使用，主要用于为类/函数动态添加新的功能，python 中
	的用法如下：
	def deco(func):
		def _deco():
			print("before myfunc() called.")
			func()
			print(" after myfunc() called.")
		# 不需要返回func，实际上应返回原函数的返回值
		return _deco
	
	@deco
	def myfunc():
		print(" myfunc() called.")
	return 'ok'
	
	myfunc()
	
	如果 obj 实现了__iter__以及 Next(), 我们可以使用 iter(obj)来获取迭代器: 并可以使用如下
	方法进行访问：
	fetch = iter(seq)
	while 1:
		try:
			i = fetch.next()
		except StopIteration:
			break
		#do_something_to(i)
	dict 的 items()返回的是一个包含<KEY, VALUE>pair 的 list 对象
	dict 的 iteritems()返回的是一个可以遍历<KEY, VALUE>pair的迭代器 iterator,与 C++中迭代器
	类似，可以使用一些通用函数对其进行遍历处理
知道 greenlet、stackless 吗？说说你对线程、协程、进程的理解；

	greenlet 类似于 goto 语句的功能，但是在函数或者说微线程之间实现了跳转，且在结束后
	能自动回到调用处
	一个 “greenlet” 是一个很小的独立微线程。可以把它想像成一个堆栈帧，栈底是初始调用，
	而栈顶是当前 greenlet 的暂停位置。你使用 greenlet 创建一堆这样的堆栈，然后在他们之间
	跳转执行。跳转不是绝对的：一个 greenlet 必须选择跳转到选择好的另一个 greenlet，这会
	让前一个挂起，而后一个恢复。两 个 greenlet 之间的跳转称为 切换(switch) 。
	当你创建一个 greenlet，它得到一个初始化过的空堆栈；当你第一次切换到它，他会启动指
	定的函数，然后切换跳出 greenlet。当最终栈底 函数结束时， greenlet 的堆栈又编程空的了，
	而 greenlet 也就死掉了。greenlet 也会因为一个未捕捉的异常死掉。
	stackless 是 python 的一个协程实现版本？还没有仔细看。
	线程，进程是比较经典的概念了，进程可以包括文件句柄等系统资源的单位，线程一般是
	现代 CPU 的基本调度单位
	而协程是通过用户调度，切换的消耗要小于线程/进程的切换。
	协程的优势在于可以自己控制切换，适合于顺序执行的一些情况，而线程更加适合并行处
	理数据的情况；同时使用协程可以控制调度，减少切换的消耗。
讲讲对 unicode, gbk, utf-8 等的理解，python2.x 是如何处理编码问题？

	Unicode，GBK 是对字符编码值的规定，两者并不兼容。而 UTF-8 则是对于 Unicode 编码的具
	体表现形式
	Unicode 有多种表达方式，包括 UCS2,UCS4,UTF-8,UTF-7；其中手机短信就是由 ASCII(只存在
	ASCII 编码)及 UCS2 编码混合(存在任意个非 ASCII 编码)
	UTF-8 使用 1-4 个字节来存储单个字符，应该是目前最流行的字符集。Linux 默认字符集就是
	UTF-8
	一般代码头行加入 # -*- coding: utf-8 -*-
	保证 python 编辑器的编码正确，或使用 u’中文’保证被转换成 unicode 编码，推荐使用
	sys.setdefaultencoding('utf-8')来保证我们的编码
	对外来输入：读取文件/读取数据库 得到的字符串使用 decode
Python 是如何进行内存管理的？python 的程序会内存泄露吗？说说有没有什么方面防止或
检测内存泄露？

	Python 使用引用计数来实现内存管理，每一个对象都拥有引用计数，表示正在引用它的变
	量个数；如果一个引用的变量出了作用域，那么对象引用计数减 1，如果引用计数到 0，内
	存回收模块会回收
	如果对象实现了__del__函数，那么对象间的交叉引用将导致__del__无法被调用，而本该在
	__del__中释放的资源(比如数据库的连接)将无法释放
	某些全局变量占用的资源不能被释放
可以使用 objgraph 工具进行对内存的监控及检测

	关于 python 程序的运行性能方面，有什么手段能提升性能？
	合理的使用数据结构：比如由于 dict 使用了 hash table，当需要经常在大容量 list 中使用查
	找时，将 list 转换成 dict 将大大提高性能
	在一些性能瓶颈问题上，考虑使用 c/c++库来实现，将大大提高程序性能
	1. 使用内建函数
	2. 使用 join()连接字符串.
	3. 使用 Python 多重赋值，交换变量
	4. 尽量使用局部变量
	5. 尽量使用 "in"
	6. 使用延迟加载加速
	7. 为无限循环使用 "while 1"
	8. 使用 list comprehension
	9. 使用 xrange()处理长序列
	10. 使用 Python generator
	11. 了解 itertools 模块
	12. 学习 bisect 模块保持列表排序
	13. 理解 Python 列表，实际上是一个数组
	14. 使用 dict 和 set 测试成员
	15. 使用 Schwartzian Transform 的 sort()
	16. Python 装饰器缓存结果
	17. 理解 Python 的 GIL（全局解释器锁）
	
	
	
什么是pyc文件

	pyc是一种二进制文件，是由py文件经过编译后，生成的文件，是一种byte code，py文件变成pyc文件后，加载的速度有所提高，而且pyc是一种跨平台的字节码，是由python的虚拟机来执行的，这个是类似于JAVA或者.NET的虚拟机的概念。pyc的内容，是跟python的版本相关的，不同版本编译后的pyc文件是不同的，2.5编译的pyc文件，2.4版本的 python是无法执行的。
什么是pyo文件

	pyo是优化编译后的程序 python -O 源文件即可将源程序编译为pyo文件
什么是pyd文件

	pyd是python的动态链接库。
为什么需要pyc文件

	这个需求太明显了，因为py文件是可以直接看到源码的，如果你是开发商业软件的话，不可能把源码也泄漏出去吧？所以就需要编译为pyc后，再发布出去。当然，pyc文件也是可以反编译的，不同版本编译后的pyc文件是不同的，根据python源码中提供的opcode，可以根据pyc文件反编译出 py文件源码，网上可以找到一个反编译python2.3版本的pyc文件的工具，不过该工具从python2.4开始就要收费了，如果需要反编译出新版本的pyc文件的话，就需要自己动手了（俺暂时还没这能力^—^）,不过你可以自己修改python的源代码中的opcode文件，重新编译 python，从而防止不法分子的破解。
	
.items() .iteritems()

	一个生成全部，一个是迭代器
range xrange

	一个列表 一个迭代器 xrange
	
python支持多线程，能够单进程无缝发挥多路CPU的优势

	支持，不能够
为什么不能？并行计算？Python的线程实际上是使用单核在运行。

	https://wiki.python.org/moin/ParallelProcessing
	在大多数系统上，Python同时支持消息传递和基于线程的并发编程。尽管大多数程序员熟悉的往往是线程接口，但实际上Python线程受到的限制有很多。尽管最低限度是线程安全的，但Python解释器还是使用了内部的GIL(Global Interperter Lock,全局解释器锁定)，在任意指定的时刻只能在一个处理器上运行。尽管GIL经常是Python社区中争论的热点，但在可以预见的将来它都不可能消失。
	


检查常用类型方法

	dir(list)
	
检查变量类型

	isinstance([], list)
	
yield

	[Python yield 使用浅析](http://www.ibm.com/developerworks/cn/opensource/os-cn-python-yield/index.html)

动态加载 反射等

	[Python自省（反射）指南](http://www.cnblogs.com/huxi/archive/2011/01/02/1924317.html)

传值？传引用？传值！

PEP8

	[PEP8中文翻译](http://wiki.hiaero.net/doku.php?id=python:pep8)
	
Python的GIL是什么鬼，多线程性能究竟如何

	http://cenalulu.github.io/python/gil-in-python/
	
python是动态类型的？到底算是强类型的还是弱类型的呢？

	动态强类型
	数据类型不会隐式转换，‘1’+1 报typeerror；是为强类型
	变量可以重新绑定新的值，可以是不同类型的；是为动态

[写程序]

list 对象 alist [{'name':'a','age':20},{'name':'b','age':30},{'name':'c','age':25}]， 请按 alist 中元素的age 由大到小排序；

	alist = [{'name':'a','age':20},{'name':'b','age':30},{'name':'c','age':25}]
	alist.sort(cmp=lambda l,r:l['age']-r['age'], key=None, reverse=False)
	print alist
	# OR
	alist = [{'name':'a','age':20},{'name':'b','age':30},{'name':'c','age':25}]
	alist.sort(key=lambda k:k['age'])
	print alist
两个 list 对象 alist ['a','b','c','d','e','f'], blist ['x','y','z','d','e','f']，请用简洁的方法合并这两个 list，
并且 list 里面的元素不能重复；
	
	alist = ['a','b','c','d','e','f']
	blist = ['x','y','z','d','e','f']
	clist=list(set(alist) | set(blist))
	print clist
打乱一个排好序的 list 对象 alist；

	import random;
	alist = ['a','b','c','d','e','f'
	random.shuffle(alist)
	print alist

	import random;
	alist = [ 'a''b''c''d''e''f'
	random.seed()
	alist.sort(key=lambda k:random.random())
	print alist
简单实现一个 stack

	class Stack:
		def __init__(self):
			self.items = []
		def __iter__(self):
			return self.items.__iter__()
		def pop(self):
			return self.items.pop()
		def top(self):
			if len(self.items) > 0:
				return self.items[len(self.items)-1]
		def push(self, item):
			self.items.append(item)
		def empty(self):
			self.items = []
		def size(self):
			return len(self.items)
	st = Stack()
	st.push(8)
	st.push(5)
	st.push(4)
	st.push(2)
	st.push(6)
	print st.top()
	print st.pop()
	print st.top()
	print max(st)
输入某年某月某日，判断这一天是这一年的第几天？python

	# -*- coding: utf-8 -*-
	#标准库版本
	import re;
	import time;
	import datetime;
	def getSequenceDayOfYear(year, month, day):
	return int(datetime.datetime(year, month, day).strftime("%j"))
	print (getSequenceDayOfYear(2014, 3,27))
	#自己实现版本
	# -*- coding: utf-8 -*-
	def getSequenceDayOfYear1(year, month, day):
	lstNotLeap = [31,28,31,30,31,30,31,31,30,31,30,31] #非闰年
	lstLeap = [31,29,31,30,31,30,31,31,30,31,30,31]#闰年
	lst =[]
	if month < 1 or month >12:
	print 'wrong month'
	return 0
	if (year % 4 == 0) and (year % 100 !=0) or (year % 400 == 0):
	lst = lstLeap
	else:
	lst = lstNotLeap
	if day < 1 or day > lst[month-1]:
	print 'wrong day'
	return 0
	totalDays = 0 # sum(lst.__getslice__(), 12-month)+day
	
	for i in range(0, month-1):
	totalDays = totalDays+lst[i]
	totalDays = totalDays + day
	return totalDays
	print (getSequenceDayOfYear1(2014, 3,27))
将字符串："k:1|k1:2|k2:3|k3:4"python {k:1, k1:2, ... }

	# -*- coding: utf-8 -*-
	s = "k:1|k1:2|d|k2:3|k3:4"
	dict={}
	lst = s.split('|')
	for pair in lst:
		try:
			lstPair = pair.split(':')
			dict[lstPair[0]] = lstPair[1]
		except:
			pass
	print dict

排序

	str_list = ['a', 'b', 'c']
	str_list.sort(key=lambda x:x.lower(),reverse=True)
随机

	import random
	random.random()
	random.sample(range(10), 2)
	l = range(10)
	random.shuffle(l)

文件

	with open('1.txt', 'w') as f:
	    f.write('abc')
	
	with open('1.txt', 'r') as f:
	    for s in f:
	        print s
	
	import os
	os.listdir('.')

	import shutil
	shutil.copyfile('1.txt', '2.txt')
	
	os.remove('2.txt')
	
题目 考虑Decorator 装饰器

	def wrap_info (f):
	    b = {"b":10};
	    def inner_func (*p, **k):
	        print b['b'], p, k;
	        b['b'] += 1;
	        f(*p, **k);
	    return inner_func;
	
	def info (s):    print "func info: %s" % s;
	
	if __name__ == "__main__":
	    f1 = wrap_info (info);
	    f1 ("a");
	    f2 = wrap_info (info);
	    f1 ("b");
	    f2 ("c");
	    
题目 单例模式、

	class singleton (object):
	    """ 单例模式的实现 """
	    def __new__ (cls, **kargs):
	        if '_instance' not in cls.__dict__:
	            cls._instance = object.__new__ (cls, **kargs);
	        return cls._instance;

###题目来源

* http://blog.csdn.net/caoxing81/article/details/45970735
* http://bitwolaiye.github.io/blog/2014/01/16/prepare-python-engineer-interview/