---
title: Http协议
date: 2020-05-04 16:53:58
tag: 随笔
top: 10
---
# http协议知识总结  
 <!-- more-->

## 1.http协议概述  
 HTTP协议是Hyper Text Transfer Protocol（超文本传输协议）的缩写，是用于从万维网（WWW:World Wide Web ）服务器传输超文本到本地浏览器的传送协议。 

 HTTP是一个基于TCP/IP通信协议来传递数据（HTML 文件， 图片文件，查询结果等）。 

 HTTP是一个属于应用层的面向对象的协议，由于其简捷、快速的方式，适用于分布式超媒体信息系统。HTTP协议工作于客户端-服务端架构为上。浏览器作为HTTP客户端通过URL向HTTP服务端即WEB服务器发送所有请求。Web服务器根据接收到的请求后，向客户端发送响应信息。 

## 2.http协议特点  
 简单快速、灵活、无连接、无状态 

## 3.http报文组成部分  
 请求报文：请求行 请求头 空行 请求体 

 响应报文：状态行 响应头 空行 响应体 

 请求行：http方法 页面地址 http协议 版本 

 请求头：key value值 

## 4.http协议方法  
 GET    获取资源 

 POST   传输资源 

 PUT    更新资源 

 DELETE 删除资源 

 HEAD   获取报文首部 

## 5.POST和GET的区别  
 GET在浏览器回退时是无害的，而POST会再次提交请求 

 GET产生的URL地址可以被收藏，而POST不可以 

 GET请求会被浏览器主动缓存，而POST不会，除非手动设置 
 
 GET请求只能进行url编码，而POST请求支持多种编码方式 

 GET请求参数会被完整保留在浏览器历史记录里，二POST参数不会被保留 

 GET请求在URL中传送的参数是有长度限制的，而post没有 

 对参数的数据类型，GET只接受ASCII字符，而POST没有限制 

 GET比POST更不安全，因为参数直接暴露在URL上，所以不能用来传递敏感信息 

 GET参数通过URL传递，POST放在REquest body中 

## 6.HTTP状态码  
 1xx：指示信息-表示请求已被接收，继续处理 

 2xx：成功-请求已被成功接收 

 3xx：重定向-要完成请求必须进行更进一步的操作 

 4xx：客户端错误-请求有语法错误或请求无法实现 

 5xx：服务器错误-服务器未能实现合法的请求 

## 7.什么是持久连接？  
 持久连接的特点是，只要任意一端没有明确提出断开连接，则保持 TCP 连接状态。 

 在 HTTP/1.1 中，所有的连接默认都是持久连接，而HTTP/1.0 使用非持久连接。 

## 8.什么是管线化？
 持久连接使得多数请求以管线化（pipelining）方式发送成为可能。从前发送请求后需等待并收到响应，才能发送下一个请求。管线化技术出现后，不用等待响应亦可直接发送下一个请求。这样就能够做到同时并行发送多个请求，而不需要一个接一个地等待响应了！！ 

***

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=1385126398&auto=0&height=66"></iframe>
