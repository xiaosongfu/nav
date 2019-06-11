https://github.com/knative

https://knative.dev

https://cloud.google.com/knative/

---

Kubernetes-based platform to build, deploy, and manage modern serverless workloads
基于Kubernetes的平台，用于构建，部署和管理现代无服务器工作负载

和标准化的 FaaS 不同（只运行特定标准的 Function 代码），knative 期望能够运行所有的 workload : traditional application、function、container。

knative 建立在 kubernetes 和 istio 平台之上，使用 kubernetes 提供的容器管理能力（deployment、replicaset、和 pods等），以及 istio 提供的网络管理功能（ingress、LB、dynamic route等）。



---

为了实现 serverless 应用的管理，knative 把整个系统分成了三个部分：
* Build：构建系统，把用户定义的函数和应用 build 成容器镜像
* Serving：服务系统，用来配置应用的路由、升级策略、自动扩缩容等功能
* Eventing：事件系统，用来自动完成事件的绑定和触发

以下Knative组件可用：
* build - 源到容器的构建编排
* eventing - 管理和交付事件
* serving - 请求驱动的计算，可以扩展到零

> build

> eventing

> serving

Knative Serving 以 Kubernetes 和 Istio 为基础，支持serverless applications and function 的部署和服务。Serving 很容易上手和扩展以支持高级方案。
Knative Serving 项目提供了中间件原语，可以：
* 快速部署无服务器容器
* 自动放大和缩小到零
* Istio 组件的路由和网络编程
* 部署的代码和配置的时间点快照

---

## CloudEvents

https://cloudevents.io/
https://github.com/cloudevents/spec

---

knative 是谷歌开源的 serverless 架构方案，旨在提供一套简单易用的 serverless 方案，把 serverless 标准化。目前参与的公司主要是 Google、Pivotal、IBM、Red Hat，2018年7月24日对外发布，当前还处于快速发展的阶段。
