https://helm.sh/
https://hub.helm.sh/
https://docs.helm.sh/

https://github.com/helm/helm

---

* https://github.com/helm/chartmuseum
* https://chartmuseum.com/
* https://chartmuseum.com/docs/
* https://github.com/chartmuseum/ui  ChartMuseum frontend UI

Helm Chart Repository 可以通过多种方式托管，包括GitHub或Gitlab页面，对象存储，使用 Chartmuseum 和通过服务提供商。

Host your own Helm Chart Repository https://chartmuseum.com

ChartMuseum is an open-source **Helm Chart Repository** server written in Go (Golang), with support for cloud storage backends, including Google Cloud Storage, Amazon S3, Microsoft Azure Blob Storage, Alibaba Cloud OSS Storage, Openstack Object Storage, Oracle Cloud Infrastructure Object Storage, and Baidu Cloud BOS Storage.

---

Helm 的操作基于两个主要组件的协作：一个名为 helm 的命令行工具和一个名为 tiller 的服务端组件（必须在它管理的集群上运行）。

Helm 部署的基本构建块是 Helm Chart，它负责封装 Kubernetes 原生应用程序的 YAML 文件，可以本地存储，也可以从远程 Chart 仓库中获取。

---

### 1. Helm

Helm is a tool that streamlines(精简) installing and managing Kubernetes applications. Think of it like apt/yum/homebrew for Kubernetes.
* Helm has two parts: a client (helm) and a server (tiller)
* Tiller runs inside of your Kubernetes cluster, and manages releases (installations) of your charts.
* Helm runs on your laptop, CI/CD, or wherever you want it to run.
* Charts are Helm packages that contain at least two things:
    * A description of the package (Chart.yaml)
    * One or more templates, which contain Kubernetes manifest files
* Charts can be stored on disk, or fetched from remote chart repositories (like Debian or RedHat packages)

Helm帮助您管理Kubernetes应用程序。Helm Charts（Helm的软件包）可帮助您定义、安装和升级即使是最复杂的Kubernetes应用程序。Charts的创建、版本控制、共享和发布过程是十分容易，所以开始使用Helm并停止复制和粘贴带来的疯狂。最新版本的Helm由CNCF与微软、谷歌、Bitnami和Helm贡献者社区合作维护。

### 2. Helm Hub

`https://hub.helm.sh/`

`Visit the Helm Hub to explore charts from numerous public Helm repositories. || 访问 Helm Hub，探索众多公共 Helm 存储库中的 charts。`

2018 年 12 月 11 日，Helm Hub  发布。虽然 Helm stable 和 incubator 库一直都是 Helm 的中心，但开发者并不打算将这些作为唯一的公共存储库。此外，Helm Hub 为用户提供一种可以在由不同人和组织托管的许多分布式存储库中找到托管 Chart 的方法。

Helm的设计，考虑了会有许多分布式存储库。与Homebrew Taps和Debian APT存储库一样，Helm可以添加，和使用许多存储库。虽然，Helm的stable和incubator存储库，从一开始就是前沿和中心，但我们并不打算将这些作为唯一的公共存储库。

Helm Hub 由 Monocular 提供支持，随着 Helm Hub 的复杂性增加，Monocular 将增强其处理多存储库和 Chart 的能力。