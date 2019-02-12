https://github.com/knative

https://knative.dev

https://cloud.google.com/knative/

---

Kubernetes-based platform to build, deploy, and manage modern serverless workloads
基于Kubernetes的平台，用于构建，部署和管理现代无服务器工作负载

---

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

对于函数的运维，一般的 serverless 平台（包括 knative）都提供了 logging、metrics、tracing 三个方面的功能。默认情况下，knative 使用 EFK（Elasticsearch、Fluent、Kibana）来收集、查找和分析日志；使用 prometheus + grafana 来收集和索引、展示 metrics 数据；使用 jaeger 来进行调用关系的 tracing。

针对 serverless 衍生出来的运维工具和平台还不够多，如何调试线上问题还没有看到非常好的解决方案。