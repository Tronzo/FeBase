# 前端基础知识整理 2017-5-3
摘自 bryant1410的https://github.com/markyun/My-blog/tree/master/Front-end-Developer-Questions/Questions-and-Answers  
根据自身稍作补充作为记忆文档

web基础：
```
HTML&CSS： 
	对Web标准的理解
	浏览器内核差异&兼容性、hack
	CSS基本功：布局、盒子模型、选择器优先级、HTML5、CSS3、Flexbox

JavaScript：
	数据类型、运算、对象、Function、继承、闭包、作用域、原型链、事件、RegExp
	JSON、Ajax、DOM、BOM、内存泄漏、跨域、异步装载、模板引擎、前端MVC、路由、模块化
	Canvas、ECMAScript 6、Nodejs

其他：
	移动端、响应式、自动化构建、HTTP、离线存储、WEB安全
	优化、重构、团队协作、可维护、易用性、SEO、UED、架构
	职业生涯、快速学习能力
```

## HTML
* 什么是HTML
```
HTML 是用来描述网页的一种语言。

HTML 指的是超文本标记语言 (Hyper Text Markup Language)
HTML 不是一种编程语言，而是一种标记语言 (markup language)
标记语言是一套标记标签 (markup tag)
HTML 使用标记标签来描述网页
```
* HTML 文档 = 网页
```
HTML 文档描述网页
HTML 文档包含 HTML 标签和纯文本
HTML 文档也被称为网页
```
* Doctype作用？标准模式与兼容模式各有什么区别?
```
（1）、<!DOCTYPE>声明位于位于HTML文档中的第一行，处于 <html> 标签之前。告知浏览器的解析器用什么文档标准解析这个文档。DOCTYPE不存在或格式不正确会导致文档以兼容模式呈现。

  （2）、标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。
```
* HTML5 为什么只需要写 ？
```
HTML5 不基于 SGML，因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为（让浏览器按照它们应该的方式来运行）；

而HTML4.01基于SGML,所以需要对DTD进行引用，才能告知浏览器文档所使用的文档类型。
```
* 行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？
```
首先：CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值，如div的display默认值为“block”，则为“块级”元素；span默认display属性值为“inline”，是“行内”元素。

  （1）行内元素有：a b span img input select strong（强调的语气）
  （2）块级元素有：div ul ol li dl dt dd h1 h2 h3 h4…p

  （3）常见的空元素：
  	<br> <hr> <img> <input> <link> <meta>
  	鲜为人知的是：
  	<area> <base> <col> <command> <embed> <keygen> <param> <source> <track> <wbr>

  不同浏览器（版本）、HTML4（5）、CSS2等实际略有差异
  参考: http://stackoverflow.com/questions/6867254/browsers-default-css-for-html-elements
```
* 页面导入样式时，使用link和@import有什么区别？
```
（1）link属于XHTML标签，除了加载CSS外，还能用于定义RSS, 定义rel连接属性等作用；而@import是CSS提供的，只能用于加载CSS;

（2）页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;

（3）import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;
```
* 介绍一下你对浏览器内核的理解？
```
主要分成两部分：渲染引擎(layout engineer或Rendering Engine)和JS引擎。
  渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等），以及计算网页的显示方式，然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同，所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其它需要编辑、显示网络内容的应用程序都需要内核。

  JS引擎则：解析和执行javascript来实现网页的动态效果。

  最开始渲染引擎和JS引擎并没有区分的很明确，后来JS引擎越来越独立，内核就倾向于只指渲染引擎。
```
* 常见的浏览器内核有哪些？
```
Trident内核：IE,MaxThon,TT,The World,360,搜狗浏览器等。[又称MSHTML]
Gecko内核：Netscape6及以上版本，FF,MozillaSuite/SeaMonkey等
Presto内核：Opera7及以上。      [Opera内核原为：Presto，现为：Blink;]
Webkit内核：Safari,Chrome等。   [ Chrome的：Blink（WebKit的分支）]
详细文章：[浏览器内核的解析和对比](http://www.cnblogs.com/fullhouse/archive/2011/12/19/2293455.html)
```
* html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分 HTML 和 HTML5？
```
* HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。
  	  绘画 canvas;
  	  用于媒介回放的 video 和 audio 元素;
  	  本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失;
        sessionStorage 的数据在浏览器关闭后自动删除;
  	  语意化更好的内容元素，比如 article、footer、header、nav、section;
  	  表单控件，calendar、date、time、email、url、search;
  	  新的技术webworker, websocket, Geolocation;

    移除的元素：
  	  纯表现的元素：basefont，big，center，font, s，strike，tt，u;
  	  对可用性产生负面影响的元素：frame，frameset，noframes；

  * 支持HTML5新标签：
  	 IE8/IE7/IE6支持通过document.createElement方法产生的标签，
    	 可以利用这一特性让这些浏览器支持HTML5新标签，
    	 浏览器支持新标签后，还需要添加标签默认的样式。

       当然也可以直接使用成熟的框架、比如html5shim;
  	 <!--[if lt IE 9]>
  		<script> src="http://html5shim.googlecode.com/svn/trunk/html5.js"</script>
  	 <![endif]-->

  * 如何区分HTML5： DOCTYPE声明\新增的结构元素\功能元素
  ```
* 简述一下你对HTML语义化的理解？
  ```
  用正确的标签做正确的事情。
  html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
  即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的;
  搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;
  使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。
  ```
* HTML5的离线储存怎么使用，工作原理能不能解释一下？
```
  在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件。
  原理：HTML5的离线存储是基于一个新建的.appcache文件的缓存机制(不是存储技术)，通过这个文件上的解析清单离线存储资源，这些资源就会像cookie一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。


  如何使用：
  1、页面头部像下面一样加入一个manifest的属性；
  2、在cache.manifest文件的编写离线存储的资源；
  	CACHE MANIFEST
  	#v0.11
  	CACHE:
  	js/app.js
  	css/style.css
  	NETWORK:
  	resourse/logo.png
  	FALLBACK:
  	/ /offline.html
  3、在离线状态时，操作window.applicationCache进行需求实现。
```
  
  
  
  
  
  


