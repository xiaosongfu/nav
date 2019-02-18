https://github.com/kubernetes/ingress-nginx
https://kubernetes.github.io/ingress-nginx/

版本历史：https://github.com/kubernetes/ingress-nginx/blob/master/Changelog.md

---

官方文档：https://kubernetes.io/docs/concepts/services-networking/ingress/

---

ingress 由以下两部分组成：

* ingress：指定规则
* ingress controller：监听请求并按照 ingress 指定的规则转发请求 

---

您可以在群集中部署任意数量的 ingress controllers。创建 ingress 时，应使用适当的 `ingress.class` 注释每个 ingress，以指示在群集中存在多个 ingress controllers 时应使用哪个 ingress controllers。

Ingress Controller 是一个守护程序，部署为 Kubernetes Pod，它监视 apiserver 的 `/ingresses` 端点以更新 Ingress资源。

---

“单Pod单IP”网络模型：每个Pod都有一个独立的IP，Pod内所有容器共享网络namespace（同一个网络协议栈和IP）

如果集群内要访问Pod，走Service，至于集群外要访问Pod，走的是Ingress。

Service和Ingress是K8S专门的抽象出来的和服务发现相关的概念

Ingress是建立在Service之上的L7访问入口，它支持通过URL的方式将Service暴露到K8S集群外；支持自定义Service的访问策略；提供按域名访问的虚拟主机功能；支持TLS通信。

---

Ingress Contronler 通过与 Kubernetes API 交互，动态的去感知集群中 Ingress 规则变化，然后读取它，按照自定义的规则，规则就是写明了哪个域名对应哪个service，生成一段 Nginx 配置，再写到 Nginx-ingress-control的 Pod 里，这个 Ingress Contronler 的pod里面运行着一个nginx服务，控制器会把生成的nginx配置写入/etc/nginx.conf文件中，然后 reload 一下 使用配置生效。以此来达到域名分配置及动态更新的问题。