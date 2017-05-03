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
