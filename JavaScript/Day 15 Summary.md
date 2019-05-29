# Day 15 Summary

1. Apache 服务器(端口号定义，http 协议，开启和关闭)
   - Apache 服务器：一种开放源码的 HTTP 服务器，可以在大多数计算机操作系统中运行，由于其多平台和安全性被广泛使用，是最流行的 Web 服务器端软件之一。简单说：Apache 是提供 web 服务的程序，用来执行网页程序和显示网页的服务器。Apache 本身不用装 php 和 mysql 也能提供服务
   - Apache 的默认端口是 80 : https://localhost:80
   - 访问自己 Web 服务器的三种方法
     - Localhost
     - 127.0.0.1
     - 自己的IP地址
   - netstat –an :查看机器有哪些端口在监听
   - netstat –anb :发现哪个程序监听该端口
2. Apache 如何配置端口
   - Apache 同时可以监听多个端口，修改 httpd.conf 文件中配置，我们修改端口。修改完成之后重新启动 apache 服务器
   - Apache 的核心服务是 httpd 的，然后依次加载各类服务
3. HTTP 协议
   - http 协议是 Hyper Text Transfer Protocol（超文本传输协议）的缩写，是用于从万维网（WWW：World Wide Web）服务器传输超文本到本地浏览器的传送协议
   - http 是一个基于 TCP/ IP 通信协议来传递数据（HTML 文件，图片文件，查询结果等）
   - http 协议工作于客户端-服务端架构为上。浏览器作为 HTTP客户端通过 URL 向 HTTP 服务器即 WEB 服务器发送所有请求。WEB 服务器根据接收到的请求后，向客户端发送响应信息
4. 主要特点
   - 简单快速：客户向服务器请求服务时，只需传送请求方法和路径。请求方法常用的有 GET、HEAD、POST。每种方法规定了客户与服务器联系的类型不同。由于HTTP 协议简单，使得 HTTP 服务器的程序规模小，因而通信速度很快
   - 灵活：HTTP 允许传输任意类型的数据对象。正在传输的类型由 Content-Type 加以标记
   - 无连接：无连接的含义是限制每次连接只处理一个请求。服务器处理完客户的请求，并收到客户的应答后，即断开连接。采用这种方式可以节省传输时间
   - 无状态：HTTP 协议是无状态协议。无状态是指协议对于事务处理没有记忆能力。缺少状态意味着如果后续处理需要前面的信息，则它必须重传，这样可能导致每次连接传送的数据量增大。另一方面，在服务器不需要先前信息时它的应答就较快
   - 支持 B/S 及 C/S 模式
5. Webserver 原理
   - Web 服务器的工作原理并不复杂，一般可分成如下 4个步骤：连接过程、请求过程、应答过程以及关闭连接
6. 集成环境安装
   - WampServer:是一款由法国人开发的 ApacheWeb 服务器、PHP 解释器以及 MySQL 数据库的整合软件包
   - WampServer 就是 Windows Apache Mysql PHP集成安装环境，即在 window 下的 apache、php和 mysql 的服务器软件

