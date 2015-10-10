#前端工作面试问题

本文包含了一些用于考查候选者的前端面试问题。不建议对单个候选者问及每个问题 (那需要好几个小时)。只要从列表里挑选一些，就能帮助你考查候选者是否具备所需要的技能。

**备注：** 这些问题中很多都是开放性的，可以引发有趣的讨论。这比直接的答案更能体现此人的能力。

## <a name='toc'>目录</a>

  1. [常见问题](#general-questions)
  1. [HTML 相关问题](#html-questions)
  1. [CSS 相关问题](#css-questions)
  1. [JS 相关问题](#js-questions)
  1. [测试相关问题](#testing-questions)
  1. [效能相关问题](#performance-questions)
  1. [网络相关问题](#network-questions)
  1. [代码相关问题](#coding-questions)
  1. [趣味问题](#fun-questions)

## 参与协作

  1. [贡献者](#contributors)
  1. [如何参与贡献](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/CONTRIBUTING.md)
  1. [许可协议](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/LICENSE.md)

#### <a name='general-questions'>常见问题：</a>

* 你在昨天/本周学到了什么？
* 编写代码的哪些方面能够使你兴奋或感兴趣？
* 你最近遇到过什么技术挑战？你是如何解决的？
* 在制作一个网页应用或网站的过程中，你是如何考虑其 UI、安全性、高性能、SEO、可维护性以及技术因素的？
* 请谈谈你喜欢的开发环境。
* 你最熟悉哪一套版本控制系统？
* 你能描述当你制作一个网页的工作流程吗？
* 假若你有 5 个不同的样式文件 (stylesheets), 整合进网站的最好方式是?
* 你能描述渐进增强 (progressive enhancement) 和优雅降级 (graceful degradation) 之间的不同吗?
* 你如何对网站的文件和资源进行优化？
* 浏览器同一时间可以从一个域名下载多少资源？
  * 有什么例外吗？
* 请说出三种减少页面加载时间的方法。(加载时间指感知的时间或者实际加载时间)
* 如果你参与到一个项目中，发现他们使用 Tab 来缩进代码，但是你喜欢空格，你会怎么做？
* 请写一个简单的幻灯效果页面。

		使用animation:spin 2s infinite;
		@keyframes spin
		{
		0% {background-image:url(./1.png);}
		50% {background-image:url(./2.png);}
		100% {background-image:url(./3.png);}
		}

* 如果今年你打算熟练掌握一项新技术，那会是什么？
* 请谈谈你对网页标准和标准制定机构重要性的理解。
* 什么是 FOUC (无样式内容闪烁)？你如何来避免 FOUC？

		如果使用import方法对CSS进行导入,会导致某些页面在Windows 下的Internet Explorer出现一些奇怪的现象:以无样式显示页面内容的瞬间闪烁,这种现象称之为文档样式短暂失效(Flash of Unstyled Content),简称为FOUC。
		
		原因大致为：
		1，使用import方法导入样式表。
		2，将样式表放在页面底部
		3，有几个样式表，放在html结构的不同位置。
		
		其实原理很清楚：当样式表晚于结构性html加载，当加载到此样式表时，页面将停止之前的渲染。此样式表被下载和解析后，将重新渲染页面，也就出现了短暂的花屏现象。在页面DOM加载完成到CSS导入完成中间会有一段时间页面上的内容是没有样式的，这段时间的长短跟网速，电脑速度都有关系。
		
		解决方法：
		使用LINK标签将样式表放在文档HEAD中。

* 请解释什么是 ARIA 和屏幕阅读器 (screenreaders)，以及如何使网站实现无障碍访问 (accessible)。

		屏幕阅读器（Screen Reader）是尝试识别理解当前屏幕上显示信息的一种软件应用，屏幕阅读器通过 Accessibility 的接口识别当前屏幕上的信息，通过文本转语音系统或者盲文的形式呈现给最终用户。读屏软件的用户一般为盲人，视障人士或者文盲。 屏幕阅读器依赖于操作系统，大多数读屏软件都是特定与某个操作系统的。用户可以根据自己的需要选择适合自己的读屏软件。开源的有 Linux 系统下的读屏软件和适用于 Windows 系统下的 NVDA（NonVisual Desktop Access）。
		ARIA（Accessible Rich Internet Applications）是无障碍的富 Internet 应用的简称，ARIA 的目标是帮助残障人士更加无障碍得访问 众多的 Web2.0 的富客户端应用。ARIA 定义了一系列的角色（role），状态（State）和属性（properties）此信息由浏览器（如 Firefox）进行解释，通过平台可访问性 API 向辅助技术提供，对于 Windows，此 API 即 MSAA (Microsoft Active Accessibility)。辅助技术将随后向用户表述信息，从而使得当前的页面元素更富语义的传递给屏幕阅读器，从而给残障人士听到。 ARIA 对窗口小部件（Widget）的键盘操作也给出了一个标准，使得用户操作窗口小部件（widget）就如同本地应用一样，同时对于动态更新的内容 ARIA 也定义了对应的属性帮助用户识别当前 Web 应用上发生的变化。而所有 ARIA 做出的这些定义和标准都要依靠支持这个标准的屏幕阅读器体现出来，使得最终用户能从中受益，享受到真正无障碍得 web2.0 应用。 JAWS 对 ARIA 提供了很好的支持，下面举例说明：

		https://www.ibm.com/developerworks/cn/web/1010_sunqy_jaws/
* 请解释 CSS 动画和 JavaScript 动画的优缺点。

		基于JavaScript的动画性能竟然达到甚至超过了CSS transtions动画
		https://github.com/xiangpaopao/blog/issues/3

		CSS3的动画的优点：
		
		在性能上会稍微好一些，浏览器会对CSS3的动画做一些优化（比如专门新建一个图层用来跑动画）
		代码相对简单
		但其缺点也很明显：
		
		在动画控制上不够灵活
		兼容性不好
		部分动画功能无法实现（如滚动动画，视差滚动等）
		JavaScript的动画正好弥补了这两个缺点，控制能力很强，可以单帧的控制、变换，同时写得好完全可以兼容IE6，并且功能强大。但想想CSS动画的transform矩阵是C++级的计算，必然要比javascript级的计算要快。另外对库的依赖也是一个很让人头疼的问题。
		
		所以，对于一些复杂控制的动画，使用javascript会比较靠谱。而在实现一些小的交互动效的时候，就多考虑考虑CSS吧
		http://segmentfault.com/q/1010000000645415

* 什么使 CORS，以及其要解决的问题？

		跨域资源共享（CORS ）是一种网络浏览器的技术规范，它为Web服务器定义了一种方式，允许网页从不同的域访问其资源。而这种访问是被同源策略所禁止的。CORS系统定义了一种浏览器和服务器交互的方式来确定是否允许跨域请求。 它是一个妥协，有更大的灵活性，但比起简单地允许所有这些的要求来说更加安全。
		简言之，CORS就是为了让AJAX可以实现可控的跨域访问而生的。
		
		以往的解决方案

        以前要实现跨域访问，可以通过JSONP、Flash或者服务器中转的方式来实现，但是现在我们有了CORS。

        CORS与JSONP相比，无疑更为先进、方便和可靠。

        1、 JSONP只能实现GET请求，而CORS支持所有类型的HTTP请求。

        2、 使用CORS，开发者可以使用普通的XMLHttpRequest发起请求和获得数据，比起JSONP有更好的错误处理。

        3、 JSONP主要被老的浏览器支持，它们往往不支持CORS，而绝大多数现代浏览器都已经支持了CORS（这部分会在后文浏览器支持部分介绍）。
        
        网站需要设置头部

		Access-Control-Allow-Origin: http://blog.csdn.net  
		
		http://blog.csdn.net/hfahe/article/details/7730944
	
#### <a name='html-questions'>HTML 相关问题：</a>

* `doctype`(文档类型) 的作用是什么？

		申明文档类型，指示浏览器采用何种模式渲染文档

* 浏览器标准模式 (standards mode) 和怪异模式 (quirks mode) 之间的区别是什么？

		主要区别在盒模型的描述上

* HTML 和 XHTML 有什么区别？

		最主要的不同：
		XHTML 元素必须被正确地嵌套。
		XHTML 元素必须被关闭。
		标签名必须用小写字母。
		XHTML 文档必须拥有根元素。

* 如果页面使用 'application/xhtml+xml' 会有什么问题吗？

		IE不支持application/xhtml+xml类型，支持text/html
		可能会有一些兼容性问题

* 如果网页内容需要支持多语言，你会怎么做？

		申明网页采用UTF-8编码
		<meta charset=utf-8"/>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
		
		1）制图时，应该讲图形的图像层与文本层分离，这样在重新绘制改图形时只需对文本进行翻译。
		
		2）设置控件属性应考虑到各种语言版本的文本显示，尽可能为翻译预留足够的空间。同时也应该保持不同语言界面的统一性，避免过多的差异。
		
		3）编码注意代码复用，将多个模块的共用信息存放在共通的文件中便于全局管理。
		页面请求的过程可描述如下:
		1）用户在终端选择自己所偏好的语言,并通过浏览器向服务器发送页面请求。
		2）模板界面接收到语言选项后,从资源文件中读取相应区域的资源。
		3）在响应用户的页面请求时,系统将根据检索到的语言选项,动态的加载相关区域的JS文件和CSS文件,为不同区域初始化不同的样式。
		4）数据库接口接收到语言选项后,将其作为一个SQL参数传入数据库,检索相应区域的数据。
		5）模板界面将接收到的各种信息,组织成Html代码,再发送给浏览器,显示给终端用户。
		该架构的核心是模板界面,它主要负责将接收到的各类信息组织成Html代码。
		* 在设计和开发多语言网站时，有哪些问题你必须要考虑？
* `data-`属性的作用是什么？

		html5新增加的属性，方便取数据

		下面是元素应用data属性的一个例子：
		
		<div id="day2-meal-expense"
		  data-drink="coffee"
		  data-food="sushi"
		  data-meal="lunch">¥20.12</div>
		
		要想获取某个属性的值，可以像下面这样使用dataset对象：
		
		var expenseday2 = document.getElementById('day2-meal-expense'); 
		var typeOfDrink = expenseday2.dataset.drink;
		
		dataset并不是典型意义上的JavaScript对象，而是个DOMStringMap对象，DOMStringMap是HTML5一种新的含有多个名-值对的交互变量。使用dataset操作data 要比使用getAttribute稍微慢些

* 如果把 HTML5 看作做一个开放平台，那它的构建模块有哪些？
	
		　　　　1）Web Storage API
		　　　　2）基于位置服务LBS
		　　　　3）无插件播放音频视频
		　　　　4）调用相机和GPU图像处理单元等硬件设备
		　　　　5）拖拽和Form API

* 请描述 `cookies`、`sessionStorage` 和 `localStorage` 的区别。

		cookies是服务器存放在客户端的少量数据，方面跨页面操作，保存状态，cookies在和服务器交互时会传输，增大传输带宽，不能跨域
		 sessionStorage用于本地存储一个会话（session）中的数据，这些数据只有在同一个会话中的页面才能访问并且当会话结束后数据也随之销毁
		localStorage是新增加的，主要用来客户端本地存放大量的数据，数据不会传输，能持久保存
	
		共同点：都是保存在浏览器端，且同源的。
		　　区别：
		　　1）cookie数据始终在同源的http请求中携带（即使不需要），即cookie在浏览器和服务器间来回传递。而sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存。
		
		　　2）cookie数据还有路径（path）的概念，可以限制cookie只属于某个路径下。存储大小限制也不同，cookie数据不能超过4k，同时因为每次http请求都会携带cookie，所以cookie只适合保存很小的数据，如会话标识。
		　　3）sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。数据有效期不同，sessionStorage：仅在当前浏览器窗口关闭前有效，自然也就不可能持久保持；localStorage：始终有效，窗口或浏览器关闭也一直保存，因此用作持久数据；cookie只在设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭。
		　　4）作用域不同，sessionStorage不在不同的浏览器窗口中共享，即使是同一个页面；localStorage 在所有同源窗口中都是共享的；cookie也是在所有同源窗口中都是共享的。
		
		Web Storage 支持事件通知机制，可以将数据更新的通知发送给监听者。Web Storage 的 api 接口使用更方便。
		
		sessionStorage 和 localStorage 是HTML5 Web Storage API 提供的，可以方便的在web请求之间保存数据。有了本地数据，就可以避免数据在浏览器和服务器间不必要地来回传递。
		　　sessionStorage、localStorage、cookie都是在浏览器端存储的数据。
		　　　　其中sessionStorage的概念很特别，引入了一个“浏览器窗口”的概念。sessionStorage是在同源的同窗口（或tab）中，始终存在的数据。也就是说只要这个浏览器窗口没有关闭，即使刷新页面或进入同源另一页面，数据仍然存在。关闭窗口后，sessionStorage即被销毁。同时“独立”打开的不同窗口，即使是同一页面，sessionStorage对象也是不同的。
		
		Web Storage带来的好处：
		　　1）减少网络流量：一旦数据保存在本地后，就可以避免再向服务器请求数据，因此减少不必要的数据请求，减少数据在浏览器和服务器间不必要地来回传递。
		　　2）快速显示数据：性能好，从本地读数据比通过网络从服务器获得数据快得多，本地数据可以即时获得。再加上网页本身也可以有缓存，因此整个页面和数据都在本地的话，可以立即显示。
		　　3）临时存储：很多时候数据只需要在用户浏览一组页面期间使用，关闭窗口后数据就可以丢弃了，这种情况使用sessionStorage非常方便。
		
		浏览器本地存储与服务器端存储之间的区别其实数据既可以在浏览器本地存储，也可以在服务器端存储。
		浏览器端可以保存一些数据，需要的时候直接从本地获取，sessionStorage、localStorage和cookie都由浏览器存储在本地的数据。
		服务器端也可以保存所有用户的所有数据，但需要的时候浏览器要向服务器请求数据。
		1.服务器端可以保存用户的持久数据，如数据库和云存储将用户的大量数据保存在服务器端。
		2.服务器端也可以保存用户的临时会话数据。服务器端的session机制，如jsp的 session 对象，数据保存在服务器上。实现上，服务器和浏览器之间仅需传递session id即可，服务器根据session id找到对应用户的session对象。会话数据仅在一段时间内有效，这个时间就是server端设置的session有效期。
		服务器端保存所有的用户的数据，所以服务器端的开销较大，而浏览器端保存则把不同用户需要的数据分布保存在用户各自的浏览器中。浏览器端一般只用来存储小数据，而服务器可以存储大数据或小数据。服务器存储数据安全一些，浏览器只适合存储一般数据。

* 请解释 `<script>`、`<script async>` 和 `<script defer>` 的区别。
 
		html5新增加的属性
		
		<script src="script.js"></script>
		没有 defer 或 async，浏览器会立即加载并执行指定的脚本，“立即”指的是在渲染该 script 标签之下的文档元素之前，也就是说不等待后续载入的文档元素，读到就加载并执行。
		
		<script async src="script.js"></script>
		有 async，加载和渲染后续文档元素的过程将和 script.js 的加载与执行并行进行（异步）。
		
		<script defer src="myscript.js"></script>
		有 defer，加载后续文档元素的过程将和 script.js 的加载并行进行（异步），但是 script.js 的执行要在所有元素解析完成之后，DOMContentLoaded 事件触发之前完成。
		defer 和 async 在网络读取（下载）这块儿是一样的，都是异步的（相较于 HTML 解析）
		它俩的差别在于脚本下载完之后何时执行，显然 defer 是最接近我们对于应用脚本加载和执行的要求的
		关于 defer，此图未尽之处在于它是按照加载顺序执行脚本的，这一点要善加利用
		async 则是一个乱序执行的主，反正对它来说脚本的加载和执行是紧紧挨着的，所以不管你声明的顺序如何，只要它加载完了就会立刻执行
		仔细想想，async 对于应用脚本的用处不大，因为它完全不考虑依赖（哪怕是最低级的顺序执行），不过它对于那些可以不依赖任何脚本或不被任何脚本依赖的脚本来说却是非常合适的，最典型的例子：Google Analytics
		http://segmentfault.com/q/1010000000640869

* 为什么通常推荐将 CSS `<link>` 放置在 `<head></head>` 之间，而将 JS `<script>` 放置在 `</body>` 之前？你知道相关解释吗？

		JS 和 CSS 在页面中的位置，会影响其他资源（指 img 等非 js 和 css 资源）的加载顺序，究其原因，有三个值得注意的点：
		JS 有可能会修改 DOM. 典型的，可能会有 document.write. 这意味着，在当前 JS 加载和执行完成前，后续所有资源的下载有可能是没必要的。这是 JS 阻塞后续资源下载的根本原因。
		JS 的执行有可能依赖最新样式。比如，可能会有 var width = $('#id').width(). 这意味着，JS 代码在执行前，浏览器必须保证在此 JS 之前的所有 css（无论外链还是内嵌）都已下载和解析完成。这是 CSS 阻塞后续 JS 执行的根本原因。
		现代浏览器很聪明，会进行 prefetch 优化。性能是如此重要，现代浏览器在 竞争中，在 UI update 线程之外，还会开启另一个线程，对后续 JS 和 CSS 提前下载（注意，仅提前下载，并不执行）。有了 prefetch 优化，这意味着，在不存在任何阻塞的情况下，理论上 JS 和 CSS 的下载时机都非常优先，和位置无关。
		
		以上三点可简述为三条基本定律：
		定律一：资源是否下载依赖 JS 执行结果。
		定律二：JS 执行依赖 CSS 最新渲染。
		定律三：现代浏览器存在 prefetch 优化。
		
		http://www.zhihu.com/question/20357435

* 什么是渐进式渲染 (progressive rendering)？

		一边加载，一边渲染

* 你用过哪些不同的 HTML 模板语言？

		用过django的模板渲染


#### <a name='css-questions'>CSS 相关问题：</a>

* CSS 中类 (classes) 和 ID 的区别。

		class主要针对用于共性内容，减少重复代码，ID主要用于每个特殊元素，ID的优先级比class高
* 请问 "resetting" 和 "normalizing" CSS 之间的区别？你会如何选择，为什么？

		resetting是重置浏览器样式，normalizing是提供一套兼容各个浏览器默认样式
		
		但是很多reset是没必要的，多写了会增加浏览器在渲染页面的负担。
		
		重置样式非常多，凡是一个前端开发人员肯定有一个常用的重置CSS文件并知道如何使用它们。他们是盲目的在做还是知道为什么这么做呢？原因是不同的浏览器对一些元素有不同的默认样式，如果你不处理，在不同的浏览器下会存在必要的风险，或者更有戏剧性的性发生。
	
		你可能会用Normalize来代替你的重置样式文件。它没有重置所有的样式风格，但仅提供了一套合理的默认样式值。既能让众多浏览器达到一致和合理，但又不扰乱其他的东西（如粗体的标题）。
	
		在这一方面，无法做每一个复位。它也确实有些超过一个重置，它处理了你永远都不用考虑的怪癖，像HTML的audio元素不一致或line-height不一致。


	
* 请解释浮动 (Floats) 及其工作原理。

		Float是很普便的。众所周知，可以使用他制作布局和网格系统，并且兼容所有浏览器。大家都知道，浮动会让元素塌陷。即被浮动元素的父元素不具有高度。例如一个父元素包含了浮动元素，它将塌陷具有零高度。你可以按下面的方法处理：
	
		 使用clearfix(知道Micro clearfix可以加分)
		 父元素浮动也是一种方法
		 父元素使用overflow属性并设置visible值
		 
		 
		 问题成因：在一个容器中，有两个浮动的子元素，会造成显示结果意想不到的问题。在CSS规范中，浮动定位不属于正常的页面流，而是独立定位的。

		关于css的定位机制：普通流，浮动，绝对定位（position：fixed是position：absolute的一个子类）。浮动的框可以左右移动，直到它的外边缘遇到包含框或者另一个浮动框的边缘，所以才说浮动定位不属于正常的页面流。文档中的普通流就会表现得和浮动框不存在一样，当浮动框高度超出包含框的时候，就会出现包含框不会自动伸缩高度类笔盒浮动元素。所以，只含有浮动元素的父容器在显示时不需要考虑子元素的位置，就造成显示父容器像空容器一样。
		
		解决浮动：
		
		1）添加额外标签
		在浮动元素末尾添加一个空的标签例如 <div style=”clear:both”></div>。
		
		　　　　　　优点：通俗易懂，容易掌握
		缺点：可以想象通过此方法，会添加多少无意义的空标签，有违结构与表现的分离，在后期维护中将是噩梦。
		2）使用 br标签和其自身的 html属性 <br clear="all" />
		优点：比空标签方式语义稍强，代码量较少
		缺点：同样有违结构与表现的分离，不推荐使用
		3)父元素设置 overflow：hidden
		
		通过设置父元素overflow值设置为hidden；在IE6中还需要触发 hasLayout ，例如 zoom：1。<div class="warp" id="float3" style="overflow:hidden; *zoom:1;">

		优点：不存在结构和语义化问题，代码量极少
		缺点：内容增多时候容易造成不会自动换行导致内容被隐藏掉，无法显示需要溢出的元素；overflow:hidden会导致中键失效。
		4)父元素设置 overflow：auto 属性。同样IE6需要触发hasLayout，演示和3差不多
		优点：不存在结构和语义化问题，代码量极少
		缺点：多个嵌套后，firefox某些情况会造成内容全选；IE中 mouseover 造成宽度改变时会出现最外层模块有滚动条等，firefox早期版本会无故产生focus等。
		5）使用:after 伪元素
		需要注意的是 :after是伪元素（Pseudo-Element），不是伪类（某些CSS手册里面称之为“伪对象”），很多清除浮动大全之类的文章都称之为伪类，不过csser要严谨一点，这是一种态度。由于IE6-7不支持:after，使用 zoom:1触发 hasLayout。
		
		　　　　.clearfix:after {content:"."; display:block; height:0; visibility:hidden; clear:both; }
		.clearfix { *zoom:1; }
		优点：结构和语义化完全正确,代码量居中
		缺点：复用方式不当会造成代码量增加

* 描述`z-index`和叠加上下文是如何形成的。

		z-index主要用于页面分层布局，z-index值高的元素显示在z-index值低的前面。z-index的使用条件：只对有 position 属性的且值不为static的元素才有效。叠加上下文和“堆栈上下文”有关，一组具有共同双亲的元素，按照堆栈顺序一起向前或向后移动构成了所谓的堆栈上下文。

* 请描述 BFC(Block Formatting Context) 及其如何工作。

		块级格式化上下文
		http://kayosite.com/block-formatting-contexts-in-detail.html

* 列举不同的清除浮动的技巧，并指出它们各自适用的使用场景。

		clear:both
		或者使用伪元素after、before

* 请解释 CSS sprites，以及你要如何在页面或网站中实现它。

		CSS sprites指的是把小图标放在一个图片中，通过操作position来使用图片，好处是可以减少单个图片的加载，网站对并发请求数有限制
		Sprites本质是多张图片拼成一张图片。为了提高性能的原因，使用它们。一般来说，最慢一个网站可以做的是请求一个资源。一个网站的请求需要越少，速度越快。快就等于好。多个请求合成一个请求就是好。
		Sprites是栅格图像。当问到替代品时，好的答案可能都是与事实相关，Sprites通常为Icons和Icons不是需要光栅。SVG图标，字体图标，字符编码等等。

* 你最喜欢的图片替换方法是什么，你如何选择使用。

		一些图标是使用before和after伪元素;
		还有一些使用iconfont;
		使用sprite图;
		用背景图片代替图片。

* 你会如何解决特定浏览器的样式问题？

		渐进增强 (progressive enhancement) 和优雅降级 (graceful degradation)，一般采用优雅降级，先做出一套针对高版本的样式，再针对特殊浏览器hack
	
		A: CSS主要由三种方法：
		
		属性前缀法(即类内部Hack)：例如 IE6能识别下划线"_"和星号" * "，IE7能识别星号" * "，但不能识别下划线"_"，IE6~IE10都认识"\9"，但firefox前述三个都不能认识。
		选择器前缀法(即选择器Hack)：例如 IE6能识别*html .class{}，IE7能识别*+html .class{}或者*:first-child+html .class{}。
		IE条件注释法(即HTML条件注释Hack)：针对所有IE(注：IE10+已经不再支持条件注释)： <!--[if IE]>IE浏览器显示的内容 <![endif]-->，针对IE6及以下版本： <!--[if lt IE 6]>只在IE6-显示的内容 <![endif]-->。这类Hack不仅对CSS生效，对写在判断语句里面的所有代码都会生效。
		
		<!DOCTYPE html>
		<html>
		<head>
		    <title>Css Hack</title>
		    <style>
		    #test
		    {
		        width:300px;
		        height:300px;
		
		        background-color:blue;      /*firefox*/
		        background-color:red\9;      /*all ie*/
		        background-color:yellow\0;    /*ie8*/
		        +background-color:pink;        /*ie7*/
		        _background-color:orange;       /*ie6*/
		    }
		    :root #test { background-color:purple\9; }  /*ie9*/
		    @media all and (min-width:0px){ #test {background-color:black\0;} }  /*opera*/
		    @media screen and (-webkit-min-device-pixel-ratio:0){ #test {background-color:gray;} }  /*chrome and safari*/
		    </style>
		</head>
		<body>
		    <div id="test">test</div>
		</body>
		</html>

* 如何为有功能限制的浏览器提供网页？
  * 你会使用哪些技术和处理方法？
  
		  功能限制的浏览器，比如 IE 低版本、手机浏览器、奇葩国内浏览器，会在很多功能上不符合 Web 标准，而应对的方式有这么几种：
		
		只提供符合 Web 标准的页面；
		提供另一个符合那些浏览器标准的页面(例如说移动端一套css,电脑端一套css);
		兼容：这里有两种思路，一个是渐进增强，一个优雅降级。 渐进增强的思路就是提供一个可用的原型，后来再为高级浏览器提供优化。优雅降级的思路是根据高级浏览器提供一个版本，然后有功能限制的浏览器只需要一个刚好能用的版本。当然，工作中的标准都是尽量满足设计，如果不能满足的话就尽量贴近，不得已（性能之类的问题）才会砍掉某个浏览器版本上的需求。
		相关技术:
		
		Media Query
		CSS hack
		条件判断 <!--[if !IE]><!-->除IE外都可识别 <!--<![endif]-->
* 有哪些的隐藏内容的方法 (如果同时还要保证屏幕阅读器可用呢)？

		display:none，visibility:hidden和opacity: 0.8
		前者隐藏后，不会占用空间，后者会占用空间
		display:none ---不为被隐藏的对象保留其物理空间，即该对象在页面上彻底消失，通俗来说就是看不见也摸不到。

		visible:hidden--- 使对象在网页上不可见，但该对象在网页上所占的空间没有改变，通俗来说就是看不见但摸得到。

* 你用过栅格系统 (grid system) 吗？如果使用过，你最喜欢哪种？

		用过，bootstrap自带的和Responsive Grid System，后者，更小，前者易于上手，学习成本低，还能做出比较大方美观的页面

* 你用过媒体查询，或针对移动端的布局/CSS 吗？

		用过,使用媒体查询可以自适应布局 
	
		@media all and (max-width:880px){
		#sideBar{width: 250px;}
		}
		还有针对缩放比的
	
		<meta content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1.0" name="viewport">
* 你熟悉 SVG 样式的书写吗？
	
		不太熟悉，只是写过一些简单的svg
		<path>
		
		<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
		<circle cx="40" cy="40" r="24" style="stroke:#006600; fill:#00cc00"/>
		<text x="250" y="150" font-family="Verdana" font-size="10px" fill="blue">Hello, out there</text>
		<defs><style type="text/css"> <![CDATA[.sample{stroke:blue;fill:#0080FF;opacity:1;}]]></style></defs>
		<use xlink:href="#sample1" class="sample"/>
		</svg>
	
* 如何优化网页的打印样式？

		使用媒体查询，针对打印样式，单独定义一个css，去掉不必要的导航，背景，发光阴影等
	
		@media screen,print{
			#sideBar{width: 250px;}
			}
	
	
* 在书写高效 CSS 时会有哪些问题需要考虑？

		重置浏览器样式，避免不同浏览器的干扰
		共性的用class，特殊的用id，避免重复定义
		命名统一，简单易识别
		emmet插件
	
		样式是：从右向左的解析一个选择器
		ID最快，Universal最慢 有四种类型的key selector，解析速度由快到慢依次是：ID、class、tag和universal
		不要tag-qualify （永远不要这样做 ul#main-navigation { } ID已经是唯一的，不需要Tag来标识，这样做会让选择器变慢。）
		后代选择器最糟糕（换句话说，下面这个选择器是很低效的： html body ul li a { }）
		想清楚你为什么这样写
		CSS3的效率问题（CSS3选择器（比如 :nth-child）能够漂亮的定位我们想要的元素，又能保证我们的CSS整洁易读。但是这些神奇的选择器会浪费很多的浏览器资源。）
		我们知道#ID速度是最快的，那么我们都用ID，是不是很快。但是我们不应该为了效率而牺牲可读性和可维护性`


* 使用 CSS 预处理器的优缺点有哪些？
  * 请描述你曾经使用过的 CSS 预处理器的优缺点。
  
  使用变量，避免不同像素计算
  
* 如果设计中使用了非标准的字体，你该如何去实现？

		外部引用字体
	
		@font-face { 
		 font-family: SketchRockwell; /*这里是说明调用来的字体名字*/ 
		 src: url(‘SketchRockwell.ttf’); /*这里是字体文件路径*/ 
		} 
		.my_CSS3_class { 
		 font-family: SketchRockwell; /*这里设置某参数的字体值，在这里是“my_CSS3_class”调用了你刚才声明的字体值"SketchRockwell"*/ 
		 font-size: 3.2em; /*这里是字体大小*/ 
		} 

* 请解释浏览器是如何判断元素是否匹配某个 CSS 选择器？

		css选择器：标签、class、id、属性、伪元素选择器before，after、伪类选择器LVHA、子代选择器
		标签<id<class
	
		近的>嵌入>内联>外链
	
	
* 请描述伪元素 (pseudo-elements) 及其用途。

		伪类是基于元素的特征而不是他们的id、class、属性或者内容。一般来说，元素的特征是不可以从DOM树上推断得到的，而且其是动态的，当用户和DOM进行交互的时候，元素可以获得或者失去一个伪类。
		
		:first-child 点我看手册，应用第一个子元素
		:link 点我看手册，应用未访问过的链接
		:visited 点我看手册，应用已访问过的链接
		:hover 点我看手册，应用鼠标指针悬浮的元素
		:active 点我看手册，应用活动的链接
		:focus 点我看手册，应用聚焦的输入元素
		:lang 点我看手册，伪类将应用于元素带有指定lang的情况，不常用
		
		伪元素是创造文档树之外的对象。例如文档不能提供访问元素内容第一字或者第一行的机制。伪元素还提供一些在源文档中不存在的内容分配样式，例如:before和:after能够访问产生的内容。伪元素的内容实际上和普通DOM元素是相同的，但是它本身只是基于元素的抽象，并不存在于文档中，所以叫伪元素。
		
		:first-letter 点我看手册，伪元素的样式将应用于元素文本的第一个字（母）
		:first-line 点我看手册，伪元素的样式将应用于元素文本的第一行
		:before 点我看手册，在元素内容的最前面添加新内容
		:after 点我看手册，在元素内容的最后面添加新内容
		
		首先说一下伪类和伪元素的相同之处，
		
		伪类和伪元素都不出现在源文件和文档树中。也就是说在html源文件中是看不到伪类和伪元素的。
		他们的不同之处，
		
		伪类其实就是基于普通DOM元素而产生的不同状态，他是DOM元素的某一特征。伪元素能够创建在DOM树中不存在的抽象对象，而且这些抽象对象是能够访问到的。
		一句话总结不同之处就是，伪元素产生新对象，在DOM树中看不到，但是可以操作；伪类不产生新的对象，仅是DOM中一个元素的不同状态；
		



		http://gejiawen.github.io/2014/11/20/pseudo-element-and-pseudo-class/

* 请解释你对盒模型的理解，以及如何在 CSS 中告诉浏览器使用不同的盒模型来渲染你的布局。
	
		浏览器渲染上就产生了Quircks mode和Standars mode，两种渲染方法共存在一个浏览器上。
	
	    那么浏览器究竟该采用哪种模式渲染呢？这就引出的DTD，既是网页的头部声明，浏览器会通过识别DTD而采用相对应的渲染模式：
	
		1. 浏览器要使老旧的网页正常工作，但这部分网页是没有doctype声明的，所以浏览器对没有doctype声明的网页采用quirks mode解析。
		2. 对于拥有doctype声明的网页，什么浏览器采用何种模式解析，这里有一张详细列表可参考：http://hsivonen.iki.fi/doctype/
		
		3. 对于拥有doctype声明的网页，这里有几条简单的规则可用于判断：对于那些浏览器不能识别的doctype声明，浏览器采用strict mode解析
		4. 在doctype声明中，没有使用DTD声明或者使用HTML4以下（不包括HTML4）的DTD声明时，基本所有的浏览器都是使用quirks mode呈现，其他的则使用strict mode解析。
		5. 可以这么说，在现有有doctype声明的网页，绝大多数是采用strict mode进行解析的。
		6. 在ie6中，如果在doctype声明前有一个xml声明(比如:<?xml version="1.0" encoding="iso-8859-1"?>)，则采用quirks mode解析。这条规则在ie7中已经移除了。
		
		    Quirks mode和Standars mode最大的不同就是提现在对盒模式的解释上，这也是我们在js里要注意的地方。
		    什么是盒模式？ 这是针对块级元素说的，说白了就是把块级元素想像成一个装东西的盒子，而margin,padding,border,width这些css属性构成了盒模式。
		
		在Standars mode中：
	
		元素真正的宽度 = margin-left  +  border-left-width  +  padding-left  + width  +  padding-right  +  border-right-width  +  margin-right;
		
		在Quirks mode中：
		
		width则是元素的实际宽度，内容宽度 = width  -  (margin-left  +  margin-right  +  padding-left  +  padding-right  +  border-left-width  +  border-right-width)
		
		http://cavonchen.iteye.com/blog/738423

* 请解释 ```* { box-sizing: border-box; }``` 的作用, 并且说明使用它有什么好处？

		在 IE5.x 以及 Quirks 模式的 IE6/7 中，将 border 与 padding 都包含在 width 之内。
		定义 box-sizing: content-box; 时，浏览器对盒模型的解释遵从我们之前认识到的 W3C 标准；
		定义 box-sizing: border-box; 时，浏览器对盒模型的解释与 IE6 相同；
		IE 对于盒模型的解释固然不符合 W3C 的规范，但是也有它的好处：无论如何改动 border 与 padding 的值，都不会导致 box 总尺寸发生变化，也就不会打乱页面整体布局。而在 Firefox 等现代浏览器下，如果我们要改变一下 padding 的值，就不得不重新计算 box 的 width。现在 IE6 寿终正寝，这个 CSS 属性未免有些姗姗来迟。

* 请罗列出你所知道的 display 属性的全部值

		none,block,inline,inline-block,table-cell,inherit
		
		none	此元素不会被显示。
		block	此元素将显示为块级元素，此元素前后会带有换行符。
		inline	默认。此元素会被显示为内联元素，元素前后没有换行符。
		inline-block	行内块元素。（CSS2.1 新增的值）
		table-cell	此元素会作为一个表格单元格显示（类似 <td> 和 <th>）
		inherit	规定应该从父元素继承 display 属性的值。
	

* 请解释 inline 和 inline-block ，block的区别？

		- 块级元素与行内元素
	
	    - 块级元素会扩展到与元素同宽。
	
	    - 行内元素会“收缩包裹” 其内容，并且会尽可能包紧。
	    
	    其默认css样式
	    - 块级元素其高度为其内容高度，宽度会扩展到与父元素同宽。所以导致块级元素会独占一行，无法在其后容纳其他块级元素与行内元素。
		- 行内元素其高度为其内容高度，宽度会收缩包裹其内容。奇怪的一点：行内元素之间有一定的距离，使用控制台看的时候，并没有把这段距离算作盒子模型。我使用margin:0;padding:0并不会清除这段距离，？？求告知！
		
		css修饰
		
		- 块级元素可以对其高度宽度进行设置，同时也可以对边框，内外边距，进行设置，其设置结果影响文档流布局效果。
		注意修改width后，并不会使得其下面的行内元素向上移动。
		
		- 行内元素，行内元素可以对其高度进行设置么？当然不能！这个回答当然太过绝对。
		元素分为替换元素与非替换元素。几乎所有替换元素都是行内元素。
		
		行内元素与块级元素的转换

	    - display
		块级元素默认display:block;行内非替换元素(a,span)默认为display:inline;；行内替换元素(input)默认为display:inline-block;
	
	        - display:none;不显示该元素，也不会保留该元素原先占有的文档流位置。
	
	        - display:block;转换为块级元素。
	
	        - display:inline;转换为行内元素。
	
	        - display:inline-block;转换为行内块级元素。
		以上四个是我常用的，事实上，还有很多
	        - 通过display:block;与display:inline;可以很容易的实现两类元素变现形式之间的转换。
		但是，有很多时候，我们需要使用display:inline-block；来转换行内元素，或者是块级元素。但是这个元素时css2新增的属性，对于IE7以下的版本不支持这个属性，所以需要一些兼容的办法。这里会即将写一篇
	
	    - float
		当把行内元素设置完float:left/right后，该行内元素的display属性会被赋予block值，且拥有浮动特性。行内元素去除了之间的莫名空白，
	
	    - position
		当为行内元素进行定位时，position:absolute，与position:fixed。都会使原先的行内元素变为块级元素。
		
		http://www.jianshu.com/p/274614a078f3

* 请解释 relative、fixed、absolute 和 static 元素的区别

		值	描述
		static	默认。位置设置为 static 的元素，它始终会处于页面流给予的位置（static 元素会忽略任何 top、bottom、left 或 right 声明）。
		relative	位置被设置为 relative 的元素，可将其移至相对于其正常位置的地方，因此 "left:20" 会将元素移至元素正常位置左边 20 个像素的位置。
		absolute	位置设置为 absolute 的元素，可定位于相对于包含它的元素的指定坐标。此元素的位置可通过 "left"、"top"、"right" 以及 "bottom" 属性来规定。
		fixed	位置被设置为 fixed 的元素，可定位于相对于浏览器窗口的指定坐标。此元素的位置可通过 "left"、"top"、"right" 以及"bottom" 属性来规定。不论窗口滚动与否，元素都会留在那个位置。工作于 IE7（strict 模式）。

* CSS 中字母 'C' 的意思是叠层 (Cascading)。请问在确定样式的过程中优先级是如何决定的 (请举例)？如何有效使用此系统？
* 你在开发或生产环境中使用过哪些 CSS 框架？你觉得应该如何改善他们？
* 请问你有尝试过 CSS Flexbox 或者 Grid 标准规格吗？

		Flexbox对于部分浏览器支持不是很好，目前没有使用

* 为什么响应式设计 (responsive design) 和自适应设计 (adaptive design) 不同？

		先说共同点，两者都是因为越来越多的 移动设备（ mobile, tablet device ）加入到互联网中来而出现的为移动设备提供更好的体验的技术。用技术来使网页适应从小到大（现在到超大）的不同分辨率的屏幕。有人说，RWD 是 AWD 包含的一个子集。
		
		RWD：Ethan Marcote 的文章是大家认为 RWD 的起源。他提出的 RWD 是采用 CSS 的 media query 技术，配合流体布局（ fluid grids ）和同样可以自适应的图片/视频等资源素材。以上所说，都是通过 HTML 和 CSS 就能完成的。一般来说，RWD 倾向于只改变元素的外观布局，而不大幅度改变内容。Jeffrey Zeldman 总结说，我们就把 RWD 定义为一切能用来为各种分辨率和设备性能优化视觉体验的技术吧。
	
		AWD：Adaptive Design 是 Aaron Gustafson 的书的标题。他认为 AWD 在包括 RWD 的 CSS media query 技术以外，也要用 Javascript 来操作 HTML 来更适应移动设备的能力。AWD 有可能会针对移动端用户减去内容，减去功能。AWD 可以在服务器端就进行优化，把优化过的内容送到终端上。AWD 通常会牵扯到另外一个词 “progressive enhancement” 。
		
		progressive enhancement：从针对最低端的，最低分辨率的设备的设计做起，逐步逐步为更高阶的设备增加功能和效果的做法。（换个角度说，也就是相当于为移动设备减去功能）

* 你有兼容 retina 屏幕的经历吗？如果有，在什么地方使用了何种技术？

		没有

* 请问为何要使用 `translate()` 而非 *absolute positioning*，或反之的理由？为什么？

		http://caibaojian.com/f2e-interview.html


#### <a name='js-questions'>JS 相关问题：</a>

* 请解释事件代理 (event delegation)。
* 请解释 JavaScript 中 `this` 是如何工作的。
* 请解释原型继承 (prototypal inheritance) 的原理。
* 你怎么看 AMD vs. CommonJS？
* 请解释为什么接下来这段代码不是 IIFE (立即调用的函数表达式)：`function foo(){ }();`.
  * 要做哪些改动使它变成 IIFE?
* 描述以下变量的区别：`null`，`undefined` 或 `undeclared`？
  * 该如何检测它们？
* 什么是闭包 (closure)，如何使用它，为什么要使用它？
* 请举出一个匿名函数的典型用例？
* 你是如何组织自己的代码？是使用模块模式，还是使用经典继承的方法？
* 请指出 JavaScript 宿主对象 (host objects) 和原生对象 (native objects) 的区别？
* 请指出以下代码的区别：`function Person(){}`、`var person = Person()`、`var person = new Person()`？
* `.call` 和 `.apply` 的区别是什么？
* 请解释 `Function.prototype.bind`？
* 在什么时候你会使用 `document.write()`？
* 请指出浏览器特性检测，特性推断和浏览器 UA 字符串嗅探的区别？
* 请尽可能详尽的解释 AJAX 的工作原理。
* 请解释 JSONP 的工作原理，以及它为什么不是真正的 AJAX。
* 你使用过 JavaScript 模板系统吗？
  * 如有使用过，请谈谈你都使用过哪些库？
* 请解释变量声明提升 (hoisting)。
* 请描述事件冒泡机制 (event bubbling)。
* "attribute" 和 "property" 的区别是什么？
* 为什么扩展 JavaScript 内置对象不是好的做法？
* 请指出 document load 和 document ready 两个事件的区别。
* `==` 和 `===` 有什么不同？
* 请解释 JavaScript 的同源策略 (same-origin policy)。
* 如何实现下列代码：
```javascript
[1,2,3,4,5].duplicator(); // [1,2,3,4,5,1,2,3,4,5]
```
* 什么是三元表达式 (Ternary expression)？“三元 (Ternary)” 表示什么意思？
* 什么是 `"use strict";` ? 使用它的好处和坏处分别是什么？
* 请实现一个遍历至 `100` 的 for loop 循环，在能被 `3` 整除时输出 **"fizz"**，在能被 `5` 整除时输出 **"buzz"**，在能同时被 `3` 和 `5` 整除时输出 **"fizzbuzz"**。
* 为何通常会认为保留网站现有的全局作用域 (global scope) 不去改变它，是较好的选择？
* 为何你会使用 `load` 之类的事件 (event)？此事件有缺点吗？你是否知道其他替代品，以及为何使用它们？
* 请解释什么是单页应用 (single page app), 以及如何使其对搜索引擎友好 (SEO-friendly)。
* What is the extent of your experience with Promises and/or their polyfills?
* 使用 Promises 而非回调 (callbacks) 优缺点是什么？
* 使用一种可以编译成 JavaScript 的语言来写 JavaScript 代码有哪些优缺点？
* 你使用哪些工具和技术来调试 JavaScript 代码？
* 你会使用怎样的语言结构来遍历对象属性 (object properties) 和数组内容？
* 请解释可变 (mutable) 和不变 (immutable) 对象的区别。
  * 请举出 JavaScript 中一个不变性对象 (immutable object) 的例子？
  * 不变性 (immutability) 有哪些优缺点？
  * 如何用你自己的代码来实现不变性 (immutability)？
* 请解释同步 (synchronous) 和异步 (asynchronous) 函数的区别。
* 什么是事件循环 (event loop)？
  * 请问调用栈 (call stack) 和任务队列 (task queue) 的区别是什么？

#### <a name='testing-questions'>测试相关问题：</a>

* 对代码进行测试的有什么优缺点？
* 你会用什么工具测试你的代码功能？
* 单元测试与功能/集成测试的区别是什么？
* 代码风格 linting 工具的作用是什么？

#### <a name='performance-questions'>效能相关问题：</a>

* 你会用什么工具来查找代码中的性能问题？
* 你会用什么方式来增强网站的页面滚动效能？
* 请解释 layout、painting 和 compositing 的区别。

#### <a name='network-questions'>网络相关问题：</a>

* 为什么传统上利用多个域名来提供网站资源会更有效？
* 请尽可能完整得描述从输入 URL 到整个网页加载完毕及显示在屏幕上的整个流程。
* Long-Polling、Websockets 和 Server-Sent Event 之间有什么区别？
* 请描述以下 request 和 response headers：
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* 什么是 HTTP action？请罗列出你所知道的所有 HTTP action，并给出解释。

#### <a name='coding-questions'>代码相关的问题：</a>

*问题：`foo`的值是什么？*
```javascript
var foo = 10 + '20';
```

*问题：如何实现以下函数？*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*问题：下面的语句的返回值是什么？*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

*问题：`window.foo`的值是什么？*
```javascript
( window.foo || ( window.foo = "bar" ) );
```

*问题：下面两个 alert 的结果是什么？*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*问题：`foo.length`的值是什么？*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

*问题：`foo.x`的值是什么？*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

*问题：下面代码的输出是什么？*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```

## [前端工作面试 JS 相关问题](https://github.com/darcyclarke/Front-end-Developer-Interview-Questions#js)

* Q：解释下事件代理。

  A: 当我们需要对很多元素添加事件的时候，可以通过将事件添加到它们的父节点而将事件委托给父节点来触发处理函数。这主要得益于浏览器的事件冒泡机制。

  ```
    var delegate = function(client, clientMethod) {
        return function() {
            return clientMethod.apply(client, arguments);
        }
    }

    var agentMethod = delegate (client, clientMethod);
    agentMethod();
  ```

  相关阅读：
   - [JavaScript事件代理和委托（Delegation）](http://www.cnblogs.com/owenChen/archive/2013/02/18/2915521.html)
   - [事件代理](http://www.cnblogs.com/owenChen/archive/2013/02/18/2915521.html)
   - [事件代理的应用](http://tangram.baidu.com/article/138)

* Q: 解释下 JavaScript 中 `this` 是如何工作的。


  A: `this` 在 JavaScript 中主要由以下五种使用场景。

   - 作为函数调用，`this` 绑定全局对象，浏览器环境全局对象为 window 。
    * 内部函数内部函数的 `this` 也绑定全局对象，应该绑定到其外层函数对应的对象上，这是 JavaScript的缺陷，用`that`替换。
   - 作为构造函数使用，`this` 绑定到新创建的对象。
   - 作为对象方法使用，`this` 绑定到该对象。
   - 使用`apply`或`call`调用 `this` 将会被显式设置为函数调用的第一个参数。

   参考阅读：
    - [深入浅出 JavaScript 中的 this](http://www.ibm.com/developerworks/cn/web/1207_wangqf_jsthis/#ibm-pcon)
    - [this 的工作原理](http://bonsaiden.github.io/JavaScript-Garden/zh/#function.this)



* Q: 解释下原型继承的原理。

  A:原型继承的基础是原型链查找。
  原型链查找基本概念：
    1. 每一个函数 F 都有一个原型对象（prototype）F.prototype
    2. 每一个函数都可以通过 new 关键字化身成为一个类构造函数，new F 会产生一个对象 O
    3. 在调用对象的某个属性或者方法，比如 http://O.xxx 的时候，会首先查找对象自身是否有这个方法或者属性，如果没找到就会去对象的构造函数的原型对象中查找（注意有两个定语），也就是查找 O 的构造函数 F 的原型对象 http://F.prototype.xxx
    4. F.prototype 也是一个对象，查找 http://F.prototype.xxx 的时候会重复第 3 步的过程

  参考：
    - [深入理解javascript原型继承](http://www.jianshu.com/p/d2742610ec30#)
    - [JavaScript原型继承工作原理](http://www.ituring.com.cn/article/56184)
    - [Prototypal Inheritance in JavaScript](http://javascript.crockford.com/prototypal.html)

* Q: 你是如何测试JavaScript代码的？

* A: AMD vs. CommonJS？

  Q: 可参考: <http://stackoverflow.com/questions/16521471/relation-between-commonjs-amd-and-requirejs>

* Q: 什么是哈希表？

  A: 哈希表是根据关键字（Key value）而直接访问在内存存储位置的数据结构。也就是说，它通过把键值通过一个函数的计算，映射到表中一个位置来访问记录，这加快了查找速度。这个映射函数称做散列函数，存放记录的数组称做散列表。

* Q: 解释下为什么接下来这段代码不是 IIFE(立即调用的函数表达式)：`function foo(){ }();`.
  * 要做哪些改动使它变成 IIFE?

  A: 可参考 [前端编码风格规范之 JavaScript 规范](http://roshanca.com/2014/web-develop-styleguide-javascript/)

  总是将代码包裹成一个 IIFE(Immediately-Invoked Function Expression)，用以创建独立隔绝的定义域。这一举措可防止全局命名空间被污染。

  IIFE 还可确保你的代码不会轻易被其它全局命名空间里的代码所修改（i.e. 第三方库，window 引用，被覆盖的未定义的关键字等等）。

    不推荐
    ```
    var x = 10,
        y = 100;

    // Declaring variables in the global scope is resulting in global scope pollution. All variables declared like this
    // will be stored in the window object. This is very unclean and needs to be avoided.
    console.log(window.x + ' ' + window.y);
    ```
    推荐
    ```
    // We declare a IIFE and pass parameters into the function that we will use from the global space
    (function(log, w, undefined){
      'use strict';

      var x = 10,
          y = 100;

      // Will output 'true true'
      log((w.x === undefined) + ' ' + (w.y === undefined));

    }(window.console.log, window));
    ```

    IIFE（立即执行的函数表达式）:无论何时，想要创建一个新的封闭的定义域，那就用 IIFE。它不仅避免了干扰，也使得内存在执行完后立即释放。

    所有脚本文件建议都从 IIFE 开始。

    立即执行的函数表达式的执行括号应该写在外包括号内。虽然写在内还是写在外都是有效的，但写在内使得整个表达式看起来更像一个整体，因此推荐这么做。

    不推荐
    ```
    (function(){})();
    ```

    推荐
    ```
    (function(){}());
    ```
    so，用下列写法来格式化你的 IIFE 代码：
    ```
    (function(){
      'use strict';

      // Code goes here

    }());
    ```
    如果你想引用全局变量或者是外层 IIFE 的变量，可以通过下列方式传参：
    ```
    (function($, w, d){
      'use strict';

      $(function() {
        w.alert(d.querySelectorAll('div').length);
      });
    }(jQuery, window, document));
    ```



* Q: 描述以下变量的区别：`null`，`undefined` 或 `undeclared`？
  * 该如何检测它们？


  A: `undefined`是Js语言类型，而`undeclared`是一种Js语法错误。在JavaScript中，有两个表示‘空’的值`undefined`和`null`，`undefined`是一个值为`undefined` 的类型。JavaScript语言也定义了一个全局变量，它的值是 `undefined`，这个变量也被称为`undefined`。 但是这个变量不是一个常量，也不是一个关键字。这意味着它的值可以轻易被覆盖。为了避免可能对`undefined`值的改变，一个常用的技巧是使用一个传递到匿名包装器的额外参数。在调用时，这个参数不会获取任何值。如下例子：

  ```
    var undefined = 123;
    (function(something, foo, undefined) {
    // 局部作用域里的 undefined 变量重新获得了 `undefined` 值
    })('Hello World', 42);
  ```

    待修改。

   - <http://stackoverflow.com/questions/6429225/javascript-null-or-undefined>
   - <http://www.zhihu.com/question/19966545>


* 什么是闭包，如何使用它，为什么要使用它？

* 请举出一个匿名函数的典型用例？

* 解释 “JavaScript 模块模式” 以及你在何时使用它。
  * 如果有提到无污染的命名空间，可以考虑加分。
  * 如果你的模块没有自己的命名空间会怎么样？

* 你是如何组织自己的代码？是使用模块模式，还是使用经典继承的方法？

* Q: 请指出 JavaScript 宿主对象和原生对象的区别？

   A: 宿主对象是指DOM和BOM。原生对象是Object、Function、Array、String、Boolean、Number、Date、RegExp、Error、Math等对象。

* Q:指出下列代码的区别：

    ```javascript
    function Person(){}
    var person = Person();
    var person = new Person();
    ```

  A: 第一行是定义了一个函数 Person()；第二行代码是执行函数 Person() 并将其返回值复制给变量 person，如果 Person() 是一个构造器函数的话，新的对象将不会被创建，并且 this 将被绑定到全局对象上；第三行代码是用构造函数 Person() 构造一个实例对象 person。



* Q:`.call` 和 `.apply` 的区别是什么？

  A: [关于javascript中apply()和call()方法的区别](http://www.cnblogs.com/fighting_cp/archive/2010/09/20/1831844.html)

* 请解释 `Function.prototype.bind` 的作用？

* 你何时优化自己的代码？

* 你能解释一下 JavaScript 中的继承是如何工作的吗？

* 在什么时候你会使用 `document.write()`？
    * 大多数生成的广告代码依旧使用 `document.write()`，虽然这种用法会让人很不爽。

* 请指出浏览器特性检测，特性推断和浏览器 UA 字符串嗅探的区别？

* 请尽可能详尽的解释 AJAX 的工作原理。

  Q: Ajax 全称为 Asynchronous JavaScript and XML（异步 JavaScript 和 XML），是一种创建交互式网页应用的网页开发技术。
    Ajax 的原理简单来说通过 XmlHttpRequest 对象来向服务器发异步请求，从服务器获得数据，然后用 JavaScript来操作 DOM 而更新页面。这其中最关键的一步就是从服务器获得请求数据。

    以往我们浏览网页的原理是由 Client 向 Server 提交页面申请，再由 Server 将申请通过 HTTP 传回给 Client 生成浏览页面：

    ![Ajax 原理图](http://yianbin.qiniudn.com/fe-ajax-a.png)

    使用 Ajax 后的工作原理如下图，可见通过 Ajax 在用户交互方面有了很大改进，用户可以不用为提交了 Form 而长时间等待服务器应答，而且通过 Ajax 也可以开发出华丽的 Web 交互页面。

    ![Ajax 原理图](http://yianbin.qiniudn.com/fe-ajax-b.png)

    转自：[AJAX 的工作原理](https://github.com/infp/Front-end-Interview/blob/master/source/javascript.md#21%E8%AF%B7%E5%B0%BD%E5%8F%AF%E8%83%BD%E8%AF%A6%E5%B0%BD%E7%9A%84%E8%A7%A3%E9%87%8A-ajax-%E7%9A%84%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86)

* 请解释 JSONP 的工作原理，以及它为什么不是真正的 AJAX。

* 你使用过 JavaScript 模板系统吗？
    * 如有使用过，请谈谈你都使用过哪些库，比如 Mustache.js，Handlebars 等等。

* 请解释变量声明提升。

* 请描述下事件冒泡机制。

* "attribute" 和 "property" 的区别是什么？

* 为什么扩展 JavaScript 内置对象不是好的做法？

* 为什么扩展 JavaScript 内置对象是好的做法？

* 请指出 document load 和 document ready 两个事件的区别。

* Q: `==` 和 `===` 有什么不同？

  A: `==`（相等运算法），`===`（严格相等运算符） JavaScript 对象的比较是引用的比较，非值的比较，对象和其本身相等，和其他任何对象不相等。 `===` 首先计算其操作数的值，然后比较，比较过程无任何类型转换。 `==` 如果两个操作数不是同一类型的，则相等运算符进行一些类型转换进行比较。 `==` 这里截取 [JavaScript 相等表格](http://dorey.github.io/JavaScript-Equality-Table)上的的两张图片让大家更为直观的感受下。

  ![](http://paddingme.qiniudn.com/1396461120383-2.png)

  ![](http://paddingme.qiniudn.com/1396464279990-1.png)

  引用下[温特大大](http://weibo.com/wintercn)的总结就是：**只要记住 `null` 只和`undefined` 相等，有 `number` 都转 `number`，有 `boolean` 也转 `number`，有 `string` 都转 `string`，对象互相不等，`NaN` 互相不等就可以了**。

* 你如何从浏览器的 URL 中获取查询字符串参数。

* 请解释一下 JavaScript 的同源策略。

* 请描述一下 JavaScript 的继承模式。

* 如何实现下列代码：
```javascript
[1,2,3,4,5].duplicator(); // [1,2,3,4,5,1,2,3,4,5]
```

* 描述一种 JavaScript 中实现 memoization(避免重复运算)的策略。

* 什么是三元表达式？“三元” 表示什么意思？

* 函数的参数元是什么？

* 什么是 `"use strict";` ? 使用它的好处和坏处分别是什么？



#### <a name='fun-questions'>趣味问题：</a>

* 你最近写过什么的很酷的项目吗？
* 在你使用的开发工具中，最喜欢哪些方面？
* 你有什么业余项目吗？是哪种类型的？
* 你最爱的 IE 特性是什么？
* 你对咖啡有没有什么喜好？


#### <a name='contributors'>贡献者：</a>

本文档始于 2009 年，是以下作者的合作成果：[@paul_irish](https://twitter.com/paul_irish) [@bentruyman](https://twitter.com/bentruyman) [@cowboy](https://twitter.com/cowboy) [@ajpiano](https://twitter.com/ajpiano) [@SlexAxton](https://twitter.com/slexaxton) [@boazsender](https://twitter.com/boazsender) [@miketaylr](https://twitter.com/miketaylr) [@vladikoff](https://twitter.com/vladikoff) [@gf3](https://twitter.com/gf3) [@jon_neal](https://twitter.com/jon_neal) [@sambreed](https://twitter.com/sambreed) 和 [@iansym](https://twitter.com/iansym)。

时至今日，文档已经融入超过 [100 位开发者](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors)的贡献。
