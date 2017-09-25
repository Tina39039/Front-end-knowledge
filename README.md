# Front-end-knowledge
前端知识
## HTML
* 1.Doctype的作用
>
><!DOCTYPE>声明位于html文档中的第一行，处于<html>标签之前。用于告知浏览器用什么文档标准解析这个文档。
>
* 2.行内元素有哪些？块级元素有哪些？空元素有哪些？
>
>首先：css规范规定：每个元素都有display属性，确定该元素的类型。每个元素都有默认的display值。
>
>>(1)行内元素有 a,b,span,img,input,select,strong等.
>
>>(2)块级元素有 div,ul,ol,li,dl,dt,dd,h1,h2,h3,h4...p
>
>>(3)常见的空元素有：br,hr,img,input,link,meta
>
* 3.页面导入样式时，使用link和@import有什么区别？
>
>(1)link属于xhtml标签，除了加载css外，还能定义rss,定义rel连接属性等作用；而@import是css提供的，只能用于加载css;
>
>(2)页面被加载的时候，link会同时被加载，而@import引用的css会等到页面被加载完再加载;
>
>(3)@import是css2.1提出的，只能在IE5以上才能被识别，而link是XHTML标签，无兼容性问题.
>
* 4.HTML5新特性
>
>(1)画布 `canvas`;
>
>(2)用于媒介播放的 `video` 和 `audio` 元素；
>
>(3)本地离线存储 `localStorage` 长期存储数据，浏览器关闭后数据不丢失；
>
>(4) `sessionStorage` 的数据会在浏览器关闭后自动删除；
>
>(5)新增语义化标签：`article`,`header`,`footer`,`nav`,`section`;
>
>(6)表单控件：`calendar`,`date`,`time`,`email`,`url`,`search`;
>
>(7)新技术：`webworker`,`websocket`,`Geolocation`;
>
>(8)移除的元素：纯表现的元素：`basefont`,`big`,`center`,`font`,`s`,`strike`,`tt`,`u`;对可用性产生负面影响的元素：`frame`,`frameset`,`noframes`;
>
* 5.简述对HTML语义化的理解？
>
>用正确的标签做正确的事；
>
>html语义化让页面的内容结构化，结构更加清晰，便于对浏览器、搜索引擎解析；
>
>即使在没有css样式的情况下,页面也能呈现出清晰的结构；
>
>利于seo，有利于爬虫抓取更多有效信息;
>
>便于团队开发和维护，语义化更具可读性。
>
* 6.描述一下cookie,sessionStorage和localStorage的区别
>
>cookie是网站为了表示用户身份而存储在用户本地终端（client side)上的数据（通常经过加密）。
>
>cookie的数据始终在同源的http请求中携带，会在浏览器与服务器之间来回传递。
>
>sessionStorage和localStorage不会自动把数据发送给服务器，仅在本地保存。
>
>存储大小：
>
>>cookie数据大小不能超过4k.
>
>>sessionStorage和localStorage虽然也有存储大小的限制，但是比cookie大得多，可以达到5M或更大。
>
>有效时间：
>
>>localStorage存储持久数据，浏览器关闭后数据不丢失，需手动删除数据；
>
>>sessionStorage数据在当前浏览器窗口关闭后自动删除。
>
>>cookie设置的cookie过期时间之前一直有效，及时窗口关闭。
>
* 7.iframe有哪些缺点？
>iframe会阻塞主页面的onload事件；
>
>搜索引擎的检索程序无法解读这种页面，不利于SEO；
>
>iframe和主页面共享连接池，而浏览器对相同域的链接有限制，所以会影响页面的并行加载。
>
>使用iframe之前需要考虑这两个缺点。如果需要使用iframe,最好是通过javascript动态给iframe添加src属性值，这样可以绕开前两个问题。
>
* 8.label的作用是什么？
>label标签用于定义表单控件间的关系，当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。
>
* 9.如何实现浏览器内多个标签页之间的通信？
>websocket、sharedworker;
>
>也可以调用localstorage、cookie等本地存储方式；
>
* 10.websocket如何兼容低版本浏览器？
>Adobe Flash Socket;
>
>ActiveX HTMLFile (IE);
>
>基于 multipart 编码发送 XHR;
>
* 11.页面可见性（Page Visibility API)
>通过visibilityState的值检测页面当前是否可见，以及打开网页的时间等；
>
>在页面被切换到其他后台进程的时候，自动暂停音乐或视频的播放；
>
* 12.如何在页面上实现一个圆形的可点击区域？
>
>(1)map+area或者svg;
>
>(2)border-radius;
>
* 13.DOM操作----怎么添加，移除，移动，复制，创建和查找节点？
>
>(1)创建新节点
>
>>createDocumentFragment() //创建一个DOM片段
>
>>createElement()  //创建一个具体的元素
>
>>createTextNode()  //创建一个文本节点
>
>(2)添加、移除、替换、插入
>
>appendChild()
>
>removeChild()
>
>replaceChild()
>
>insertBefore()
>
>(3)查找
>
>getElementByTagName()  //通过标签名称
>
>getElementByName()  //通过元素的name属性的值
>
>getElementBtId()  //通过元素id，唯一性
>
* 14.如何对网站的文件和资源进行优化？
>
>文件合并；
>
>文件最小化/文件压缩；
>
>使用CDN托管；
>
>缓存的使用（多个域名来提供缓存）；
>
>
## CSS
* 1.介绍一下标准的css盒子模型
>
>(1)盒子模型有两种：IE盒子模型、W3C盒子模型；
>
>(2)盒子模型：内容（content)、填充（padding)、边界（margin）、边框（border);
>
>(3)区别：IE的content部分把border和padding计算进去了。
>
* 2.css选择器有哪些？哪些属性可以继承？
>
>id选择器（#id），类选择器（.classname)，标签选择器(div,p)，相邻选择器(h1+p)，子代选择器(ul>li)，后代选择器(li a)，通配符选择器(*)，属性选择器(a[rel="external"]，伪类选择器(a:hover,li:nth-child)
>
>可继承的样式：font-size,font-family,color,text-indent;
>
>不可继承的样式：border,padding,margin,width,heigth;
>
>CSS3新增伪类：
>
>p:first-of-type
>
>p:last-of-type
>
>p:only-child
>
>p:nth-child(n)
>
>:checked
>
* 3.CSS3有哪些新特性？
  >
  >css3实现圆角（border-radius),阴影（box-shadow);
  >
  >对文字加特效（text-shadow),线性渐变（gradient),旋转（transform）；
  >
  >tansform:rotate(9deg) scale(0.85,0.90) translate(0px,-10px) skew(-8deg,0deg);//旋转，缩放，定位，倾斜
  >
  >增加了许多新选择器
  >
  >rgba
  >
  >唯一引入的伪元素：：selection
  >
  >媒体查询，多栏布局
  >
  >border-image
  >
* 4.为什么要初始化css样式？
  >
  >因为浏览器的兼容问题，不同浏览器之间对有些标签的默认值是不同的，如果没对css初始化往往会出现浏览器之间页面显示差异。
  >
  >最简单的初始化方法是：*{padding：0；margin：0}
  >
* 5.对BFC规范的理解？
  >
  >BFC,块级格式化上下文，一个创建了新的BFC的盒子是独立布局的，盒子里面的子元素的样式不会影响到外面的元素。在同一个bfc中的两个毗邻的块级盒子在垂直方向的margin会发生折叠。
  >
  



