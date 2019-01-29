https://github.com/kubernetes/ingress-nginx

https://kubernetes.github.io/ingress-nginx/

---

ingress 由以下两部分组成：

* ingress：指定规则
* ingress controller：监听请求并按照 ingress 指定的规则转发请求 

---

“单Pod单IP”网络模型：每个Pod都有一个独立的IP，Pod内所有容器共享网络namespace（同一个网络协议栈和IP）

如果集群内要访问Pod，走Service，至于集群外要访问Pod，走的是Ingress。

Service和Ingress是K8S专门的抽象出来的和服务发现相关的概念

Ingress是建立在Service之上的L7访问入口，它支持通过URL的方式将Service暴露到K8S集群外；支持自定义Service的访问策略；提供按域名访问的虚拟主机功能；支持TLS通信。