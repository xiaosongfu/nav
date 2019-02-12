https://istio.io/

* https://istio.io/zh/
* https://preliminary.istio.io/zh

https://github.com/istio/istio

---

* citadel: 堡垒
* mixer: 混合器
* pilot: 飞行员

--

Connect, secure, control, and observe services.
连接，保护，控制和观察服务。

Istio is an open platform for providing a uniform way to integrate microservices, manage traffic flow across microservices, enforce policies and aggregate telemetry data. Istio's control plane provides an abstraction layer over the underlying cluster management platform, such as Kubernetes, Mesos, etc.
Istio是一个开放平台，用于提供统一的方式来集成微服务，管理跨微服务的流量，实施策略和聚合遥测数据。Istio的控制平面在底层集群管理平台上提供了一个抽象层，例如Kubernetes，Mesos等。

---

至今微服务已经历了两代发展，第一代以Spring Cloud为代表的微服务开发框架，该框架在微服务发展的前几年一度独领风骚，甚至在部分人群中成为微服务的代名词，但事实上该微服务框架并不是唯一实现微服务的方式；第二代微服务技术为服务网格（Service Mesh），它的出现解决了大部分开发人员在使用Spring Cloud中遇到的不足和痛点。

Istio是由Google、IBM、Lyft联合开发的开源项目，2017年5月发布第一个release 0.1.0， 它是一个完全开源的服务网格，可以透明的分层到现有的分布式应用中，它也是一个平台，包括允许它集成到任何日志记录平台，遥测或策略系统的API。Istio 多样化功能集能够高效的运行在分布式微服务架构中，并同时提供保护、连接和监控微服务等方法

Istio默认使用Envoy做智能代理，当然也支持其它代理，例如Linkerd、Nginmesh等。

Envoy在Istio中被部署为sidecar，和对应的微服务在同一个Kubernetes Pod中，Istio将其功能添加到sidecar中来对微服务进行管理而无需更改微服务应用代码，起到一个无侵入式的作用。