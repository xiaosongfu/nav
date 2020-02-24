那么Service Mesh提供的动态路由机制和特定的部署策略如Blue/Green部署结合起来，实现上述目标将更加容易。
* 安全通信：无论何时，安全在整个公司、业务系统中都有着举足轻重的位置，也是非常难以实现和控制的部分。而微服务环境中，不同的服务实例间通信变得更加复杂，那么如何保证这些通信是在安全、有授权的情况下进行就非常重要。通过将安全机制如TLS加解密和授权实现在Service Mesh上，不仅可以避免在不同应用上的重复实现，而且很容易在整个基础设施层更新安全机制，甚至无需对应用做任何操作。
* 多语言支持：由于Service Mesh作为独立运行的透明代理，很容易支持多语言。
* 多协议支持：同多语言支持一样，实现多协议支持也非常容易。
* 指标和分布式追踪：Service Mesh对整个基础设施层的可见性使得它不仅可以暴露单个服务的运行指标，而且可以暴露整个集群的运行指标。
* 重试和最后期限：Service Mesh的重试功能避免将其嵌入到业务代码，同时最后期限使得应用允许一个请求的最长生命周期，而不是无休止的重试。

对这些功能，概括起来，即Service Mesh使得微服务具有下列性能。
* 可见性（visiblity）：运行时指标、分布式跟踪。
* 可管理性（manageablity）：服务发现、负载均衡、运行时动态路由。
* 健壮性（resilience）：超时重试、请求最后期限、熔断机制。
* 安全性（security）：服务间访问控制、TLS加密通信。

---

* 为了解决单体的复杂度问题，我们引入微服务架构；
* 为了解决微服务架构下大量应用部署的问题，我们引入容器；
* 为了解决容器的管理和调度问题，我们引入 Kubernetes；
* 为了解决微服务框架的侵入性问题，我们引入 Service Mesh；
* 为了让 Service Mesh 有更好的底层支撑，我们又将 Service Mesh 运行在 k8s 上。

---

就在最近这一个月，Service Mesh 社区出现了两个推动标准化的大事件：
1. CNCF 筹建 Universal Data Plane API （通用数据平面 API）工作组，计划以 xDS v2 API 为基础制定数据平面的标准 API，工作组的初始成员来自包括 Envoy 和 gRPC 项目的代表（可以理解为 Google 为首）；
2. 微软在 KubeConf 上推出 Service Mesh Interface，准备定义在 Kubernetes 上运行服务网格的规范，为 Service Mesh 带来了灵活性和互通性。SMI 由微软牵头，联合 Linkerd，HashiCorp，Solo，Kinvolk 和 Weaveworks。

![](https://user-gold-cdn.xitu.io/2019/5/29/16b014936333b32b?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

其中，Universal Data Plane API 是数据平面的标准，控制平面通过这个 API 来控制数据平面的行为。而 Service Mesh Interface 是控制平面的标准，上层的应用/工具/生态体系通过 Service Mesh Interface 来实现跨不同的 Service Mesh 实现为最终用户提供一致性的体验。
