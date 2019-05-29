# Day 20 Summary

1. Promise 介绍
   - 基本概念：Promise 是 ES6 中新增的异步编程解决方案，体现在代码中它是一个对象，可以通过 Promise 构造函数来实例化
   - New Promise(cb) =>实例的基本使用 PendingResolved Rejected
   - 两个原型方法：
     - Promise.prototype.then()
     - Promise.prototype.catch()
2. 常用的静态方法
   - Promise.all() : 可以将多个 promise 实例包装成一个新的 promise 实例当所有 Promise 实例的状态都变成 resolved，Promise.all 的状态才会变成 resolved，此时返回值组成一个数组，传递给 then 中的 resolve函数,只要其中有一个被 rejected，Promise.all 的状态就变成 rejected，此时第一个被 reject 的实例的返回值，会传递给 p 的回调函数
3. Ajax 的同源策略
   - 概念：同源策略是客户端脚本（尤其是Javascript）的重要的安全度量标准。同源策略阻止从一个域上加载的脚本获取或操作另一个域上的文档属性，也就是说，受到请求的 URL 的域必须与当前 Web 页面的域相同。这意味着浏览器隔离来自不同源的内容，以防止它们之间的操作，这里的同源指的是：同协议，同域名（主机名）和同端口
   - 同协议：
   - 同域名：
   - 同端口：
4. Jsonp 跨域
   - 后端代理
   - Jsonp
   - Xhr2
   - Nginx
5. 什么是 Jsonp
   - JSONP(JSON with Padding)是一个非官方的协议，它允许在服务器端集成 Script tags 返回至客户端，通过 javascript callback 的形式实现跨域访问（这仅仅是 JSONP 简单的实现形式）
   - 回调函数：当一个函数作为另一个函数的参数时，那么这个函数就是回调函数
6. 作用：由于同源策略的限制，XmlHttpRequest 只允许请求当前源（域名、协议、端口）的资源，为了实现跨域请求，可以通过 script 标签实现跨域请求，然后在服务端输出 JSON 数据并执行回调函数，从而解决了跨域的数据请求
7. Get 和 post 提交
   - Get 方式：用 get 方式可传送简单数据，但大小一般限制在 1KB 下，数据追加到 url 中发送（http 的 header 传送），也就是说，浏览器将各个表单字段元素及其数据按照 URL 参数的格式附加在请求行中的资源路径后面。另外最重要的一点是，它会被客户端的浏览器缓存起来，那么，别人就可以从浏览器的历史记录中，读取到此客户的数据，比如帐号和密码等，因此，在某些情况下，get 方法会带来严重的安全性问题
   - Post 方式：当使用 POST 方式时，浏览器把各表单字段元素及其数据作为 HTTP 消息的实体内容发送给 Web 服务器，而不是作为 URL 地址的参数进行传递，使用 POST 方式传递的数据量要比使用 GET 方式传送的数据量大的多。总之：get 方式传送数据量小，处理效率高，安全性低，会被缓存，而 POST 反之
8. 区别
   - Post 传输数据时，不需要在 URL 中显示出来，而 Get 方法要在 URL 中显示。
   - Post 传输的数据量大，可以达到 2M，而 Get方法由于受到 URL 长度的限制,只能传递大约1024 字节.
   - Post 顾名思义,就是为了将数据传送到服务器端,Get 就是为了从服务器段取得数据.而 Get之所以也能传送数据,只是用来设计告诉服务器, 你到底需要什么样的数据 .Post 的信息作为http 请求的内容，而 Get 是在 Http 头部传输的
   - get 方法用 Request.QueryString["strName"]接收
   - post 方法用 Request.Form["strName"] 接收
9. 兼容问题
   - 虽然两种提交方式可以统一用Request("strName")来获取提交数据，但是这样对程序效率有影响，不推荐使用