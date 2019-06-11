* Pivotal Function Service
* Google Cloud Function
* AWS LAMBDA
* Azure Functions

---

# Pivotal Function Service

https://pivotal.io/cn/

https://pivotal.io/cn/platform/pivotal-function-service

---

PFS是Knative项目

那么，PFS都包括什么呢？
* 运行、伸缩和更新函数的环境。PFS负责函数源代码并执行部署。如果存在旧版本的函数，新版本会取而代之，而PFS则保留旧版本，以便在回滚时使用。软件定义的网络层负责处理所有路由调整，不会发生任何中断。函数会在不用时缩减为零个实例，并且会根据流量进行扩展。所有这些活动都不需要手动干预，对开发人员来说这是真正的无服务器体验。
* 原生的事件组件支持构建组合型响应式系统。函数对事件做出响应。这些事件可能是来自外部的HTTP(S)请求。或者，一个函数完成的工作就是触发另一个函数的事件。例如，一个函数通过修改邮政编码清理客户提交的邮寄地址，另一个负责将邮寄地址存储到数据库中的函数会等待一个事件，这个事件告诉它地址格式已修改正确。这种松散耦合的关系就是动态架构的标志。
* 在任意Kubernetes环境中只需使用pfs system install命令就可以轻松安装。我们已经撰写了适用于PKS、GKE，甚至还有本地Minikube的安装文档。适用于更多Kubernetes目标，例如Azure Kubernetes Service和VMware Cloud PKS的文档正在制作之中！
* 以一致、安全的方式打包函数的构建包。开发人员只想编写他们的业务逻辑，而不希望因为复杂的函数打包工作而纠结。在PFS中，我们加入了云原生构建包，它可以检测依赖关系并自动将您的函数构建到可运行的工件中。开发人员从不需要干预构建包，只需发送一个指向他们的源代码的pfs function create命令即可。但构建包对于时刻关注安全的运维人员来说意义重大。因为构建包提供的分层安全机制，你可以用透明方式修补映像而不影响函数本身。

---

参考： 
* 官宣！首个企业级开放式多云无服务器平台问世啦！https://mp.weixin.qq.com/s/Mu_S094hmmpdkWpL2zKdNQ

# Google Cloud Function

* 

# AWS LAMBDA

https://github.com/awslabs

* https://github.com/awslabs/aws-sam-cli ===> AWS SAM CLI is a CLI tool for local development and testing of Serverless applications

---

* AWS 为 Lambda 建立了一套架构描述规范 SAM：
https://github.com/awslabs/serverless-application-model，通过基于 yaml 格式的 SAM 描述文件，用户可以定义一个具体的 lambda 函数的各类配置信息，如运行环境、资源限制、API 网关、权限等。

* 当用户通过 SAM 定义 lambda 应用后，在正式部署前还需要进行本地测试。 AWS SAM Local 是一个由 python 实现的命令行工具，通过 SAM Local，用户可以在本地开发环境中运行和调试 SAM 定义的 AWS Lambda 应用。SAM Local 可以模拟事件源的事件输出，启动本地 API 网关示例。

# Azure Functions

https://github.com/azure

* https://github.com/Azure/azure-functions-core-tools ===> Command line tools for Azure Functions

---

* Azure Functions 的运行环境是开源的：https://github.com/Azure/azure-functions-host
