https://github.com/swift-server

* [SSWG 2019 年度更新](https://swift.org/blog/sswg-update/)

数据库驱动程序
* https://github.com/vapor/sqlite-nio
* https://github.com/vapor/postgres-nio
* https://github.com/vapor/mysql-nio
* https://github.com/Mordil/swift-redi-stack
* https://github.com/mongodb/mongo-swift-driver


---

## swift-nio

https://github.com/apple/swift-nio

## vapor

https://vapor.codes/

https://github.com/vapor/vapor

## kitura

https://www.kitura.io/

https://github.com/ibm-swift/kitura

还出了一本书：[《Server Side Swift with Kitura》](https://store.raywenderlich.com/products/server-side-swift-with-kitura)

## smoke-framework

https://github.com/amzn/smoke-framework

SwiftNIO 的推出被视作 apple 终于肯“认真对待” server-side swift 的标志。目前各大 swift 服务端框架都纷纷接入了 SwiftNIO 的支持。简单的总结 SwiftNIO 就是：很强。

smoke-framwork 是 Amazon 推出的 server-side swift 的框架，默认使用 SwiftNIO 来做网络层，并且支持 OpenAPI 这样的代码自动生成工具。Amazon 作为行业主要是云服务提供商，这个发布是极具指导意义的，代表 swift 真正被服务端市场所接纳、认可。虽然目前针对 smoke-framework 的评测还不多，但基本可以确定的是该框架会和 Amazon 的 AWS 生态有较好的融合，这对于绝大多数公司而言绝对是利好。
