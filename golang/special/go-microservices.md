IDL 就是接口描述语言（interface description language）的缩写，通过一种中立的方式来描接口，使得在不同的平台上运行的对象和不同语言编写的程序可以相互通信交流。常用的 IDL：一个是 Facebook 开源的 Thrift 协议，另一个是 Google 开源的 gRPC 协议。无论是 Thrift 协议还是 gRPC 协议，他们的工作原来都是类似的。

常用的序列化方式分为两类：文本类如 XML/JSON 等，二进制类如 PB/Thrift 等

摘自：极客时间——从0开始学习微服务 -->微服务架构组件分析 

---

## go-micro

https://github.com/micro/micro

https://micro.mu
https://micro.mu/blog/cn/

go-micro 的官博 [micro.mu/blog](https://micro.mu/blog/) 有一份现成的[翻译文档](http://btfak.com/page2/)，可以快速学习上手。

## go-kit

https://github.com/go-kit/kit

https://gokit.io/

## tp-micro

https://github.com/xiaoenai/tp-micro

TP-Micro v3 是一个基于 Teleport v4 定制的、简约而强大的微服务框架。 https://github.com/henrylee2cn/teleport

## TarsGo

https://github.com/TarsCloud/TarsGo

Tarsgo，一个高性能基于tars协议的go语言rpc框架。在腾讯，部分C++程序员转向了Go语言，tars是广泛使用的rpc框架，支持 C++ / Java / Nodejs PHP，因此Go的支持也成众望所归。

TarsGo新版本发布，支持protobuf，zipkin和自定义插件 https://juejin.im/post/5bea8ebdf265da614a3a092f