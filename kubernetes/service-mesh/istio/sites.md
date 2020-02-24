https://istio.io/
https://istio.io/zh/

https://github.com/istio/istio

---

Istio 逻辑上分为数据平面和控制平面
* **数据平面**由一组以 sidecar 方式部署的智能代理（Envoy）组成。这些代理可以调节和控制微服务及 Mixer 之间所有的网络通信。
* **控制平面**负责管理和配置代理来路由流量。此外控制平面配置 Mixer 以实施策略和收集遥测数据。

Envoy 被部署为 sidecar，和对应服务在同一个 Kubernetes pod 中。这允许 Istio 将大量关于流量行为的信号作为属性提取出来，而这些属性又可以在 Mixer 中用于执行策略决策，并发送给监控系统，以提供整个网格行为的信息。

Mixer 是一个独立于平台的组件，负责在服务网格上执行**访问控制和使用策略**，并从 Envoy 代理和其他服务**收集遥测数据**。代理提取请求级属性，发送到 Mixer 进行评估。Mixer 组件负责策略控制和遥测收集。它提供后端抽象和中介，将 Istio 的其余部分与各个基础架构后端的实现细节隔离开来，并为运维提供对网格和基础架构后端之间所有交互的细粒度控制。

Pilot 为 Envoy sidecar 提供**服务发现**功能，为**智能路由**（例如 A/B 测试、金丝雀部署等）和**弹性**（超时、重试、熔断器等）提供流量管理功能。它将控制流量行为的高级路由规则转换为特定于 Envoy 的配置，并在运行时将它们传播到 sidecar。

Citadel 通过内置**身份和凭证管理**可以提供强大的服务间和最终用户身份验证。可用于升级服务网格中未加密的流量，并为运维人员提供基于服务标识而不是网络控制的强制执行策略的能力。

* citadel: 堡垒
* mixer: 混合器
* pilot: 飞行员

---

Connect, secure, control, and observe services.
连接，保护，控制和观察服务。

Istio is an open platform for providing a uniform way to integrate microservices, manage traffic flow across microservices, enforce policies and aggregate telemetry data. Istio's control plane provides an abstraction layer over the underlying cluster management platform, such as Kubernetes, Mesos, etc.

Istio是一个开放平台，用于提供统一的方式来集成微服务，管理跨微服务的流量，实施策略和聚合遥测数据。Istio的控制平面在底层集群管理平台上提供了一个抽象层，例如Kubernetes，Mesos等。

---

至今微服务已经历了两代发展，第一代以Spring Cloud为代表的微服务开发框架，该框架在微服务发展的前几年一度独领风骚，甚至在部分人群中成为微服务的代名词，但事实上该微服务框架并不是唯一实现微服务的方式；第二代微服务技术为服务网格（Service Mesh），它的出现解决了大部分开发人员在使用Spring Cloud中遇到的不足和痛点。

Istio是由Google、IBM、Lyft联合开发的开源项目，2017年5月发布第一个release 0.1.0， 它是一个完全开源的服务网格，可以透明的分层到现有的分布式应用中，它也是一个平台，包括允许它集成到任何日志记录平台，遥测或策略系统的API。Istio 多样化功能集能够高效的运行在分布式微服务架构中，并同时提供保护、连接和监控微服务等方法

Istio默认使用Envoy做智能代理，当然也支持其它代理，例如Linkerd、Nginmesh等。

Envoy在Istio中被部署为sidecar，和对应的微服务在同一个Kubernetes Pod中，Istio将其功能添加到sidecar中来对微服务进行管理而无需更改微服务应用代码，起到一个无侵入式的作用。