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
