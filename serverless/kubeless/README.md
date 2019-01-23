#### What is Kubeless?

Kubeless is a Kubernetes-native serverless framework that lets you deploy small bits of code (functions) without having to worry about the underlying infrastructure. It is designed to be deployed on top of a Kubernetes cluster and take advantage of all the great Kubernetes primitives. If you are looking for an open source serverless solution that clones what you can find on AWS Lambda, Azure Functions, and Google Cloud Functions, Kubeless is for you!

Kubeless是一个 Kubernetes 原生无服务器框架，允许您部署少量代码（函数），而无需担心底层基础架构。它被设计为部署在Kubernetes集群之上，并利用所有伟大的Kubernetes原语。如果您正在寻找能够克隆AWS Lambda，Azure Functions和Google Cloud Functions上的内容的开源无服务器解决方案，那么Kubeless就是您的最佳选择！

Kubeless Includes:

* Support for Python, Node.js, Ruby, PHP, Golang, .NET, Ballerina and custom runtimes
* CLI compliant with AWS Lambda CLI
* Event triggers using Kafka messaging system and HTTP events
* Prometheus monitoring of functions calls and function latency by default
* Serverless Framework plugin

Kubeless包括：
* 支持Python，Node.js，Ruby，PHP，Golang，.NET，Ballerina和自定义运行时
* CLI 和 AWS Lambda CLI 兼容
* 事件触发器使用Kafka消息传递系统和HTTP事件
* Prometheus默认监视函数调用和函数延迟
* 有插件支持 Serverless 工具

#### How does it work? Check it out!

Kubeless uses a Custom Resource Definition to be able to create functions as custom kubernetes resources. It then runs an in-cluster controller that watches these custom resources and launches runtimes on-demand. The controller dynamically injects the functions code into the runtimes and make them available over HTTP or via a PubSub mechanism.

Kubeless使用 Custom Resource Definition(自定义资源定义) 来创建自定义kubernetes资源的功能。然后，它运行一个集群内控制器，监视这些自定义资源并按需启动运行时。控制器动态地将函数代码注入运行时，并通过HTTP或PubSub机制使它们可用。

---

kubeless是一个Kubernetes本机无服务器框架，允许您部署少量代码，而无需担心底层基础架构管道。它利用Kubernetes资源提供自动扩展，API路由，监控，故障排除等。

Kubeless因我们使用 Custom Resource Definition(自定义资源定义) 能够创建自定义kubernetes资源的功能而脱颖而出。然后，我们运行一个集群内控制器，监视这些自定义资源并按需启动运行时。控制器动态地将函数代码注入运行时，并通过HTTP或PubSub机制使它们可用。