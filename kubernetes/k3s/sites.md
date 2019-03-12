https://k3s.io/

https://github.com/rancher/k3s

---

2019年2月26日，Rancher Labs（以下简称Rancher）宣布推出轻量级Kubernetes发行版K3s（已开源），这款产品专为在资源有限的环境中运行Kubernetes的研发和运维人员设计。Rancher此次发布的K3s项目，将满足在边缘计算环境中运行在x86、ARM64和ARMv7处理器上的小型、易于管理的Kubernetes集群日益增长的需求。

K3s支持x86_64、ARM64和ARMv7架构，使K3s得以更加灵活地跨任何边缘基础架构工作。除了边缘计算的使用场景，K3s还非常适合那些寻求简单方法来部署Kubernetes轻量级发行版的用户。在早期技术预览期间，许多用户反馈说K3s对于CI/CD环境、嵌入式系统和本地Kubernetes部署特别有帮助。

K3s主要功能包括：
* 生产级Kubernetes：K3s是一个符合标准的、已获CNCF官方认证的Kubernetes发行版。
* 一个没有主机依赖的二进制文件：在任何设备上安装Kubernetes所需的一切都包含在这一个40MB的二进制文件当中，不需要像KuberSpray、KubeADM或者RKE这样的外部安装程序。只需要一个命令，用户就可以配置或者升级单节点K3s集群。
* 一条命令，向集群添加节点：若想向集群添加其他节点，管理员只需在新节点上运行一条命令，指向原始服务器，通过安全token传递即可。
* 自动生成证书：集群启动时，在Kubernetes主服务器和节点之间建立TLS所需的所有证书都会被自动创建，还会自动创建服务账号的加密密钥。

为了减少运行Kubernetes所需内存，K3s开发团队主要专注于以下四个方面的主要变化：
* 删除旧的、非必须的代码：K3s不包括任何默认禁用的Alpha功能或者过时的功能，原有的API组件目前仍运行于标准部署当中。除此之外，Rancher还删除了所有非默认许可控制器，in- tree云提供商和存储驱动程序，但允许用户添加任何他们需要的驱动程序。
* 整合正在运行的打包进程：为了节省RAM，K3s将通常在Kubernetes管理服务器上运行的多流程合并为单个流程。还将在工作节点上运行的kubelet、kubeproxy和flannel代理进程组合成一个进程。
* 使用containerd代替Docker作为运行时的容器引擎：通过用containderd替换Docker，K3s能够显著减少运行时占用空间，删除libnetwork、swarm、Docker存储驱动程序和其他插件等功能。
* 除了 etcd 之外，引入 SQLite 作为可选的数据存储：在k3s中添加了SQLite作为可选的数据存储，从而为etcd提供了一个轻量级的替代方案。该方案不仅占用了较少的内存，而且大幅简化了操作。

---
