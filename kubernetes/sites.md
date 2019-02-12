kubernetes 官网 - [kubernetes.io](https://kubernetes.io/)  

kubernetes 国内官网 - [kubernetes.cn](https://kubernetes.cn/)  

---

Kubernetes的网络中主要存在四种类型的通信：同一Pod内的容器间通信、各Pod彼此之间的通信、Pod与Service间的通信，以及集群外部的流量同Service之间的通信。

Pod网络及其IP由Kubernetes的网络插件负责配置和管理，具体使用的网络地址可在管理配置网络插件时指定，如10.244.0.0/16网络。而Cluster网络和IP则是由Kubernetes集群负责配置和管理，如10.96.0.0/12网络。

---

类似于 CRI 之于 K8S 的 runtime，K8S 使用 CNI（container network interface）作为 Pod 网络配置的标准接口。

* CRI：container runtime interface
* CNI：container network interface

CSI: container storage interface

CNI主要有两类接口，分别是在创建容器时调用的配置网络接口： AddNetwork 和删除容器时调用的清理网络接口：DelNetwork

---

当前主流的load balancer实现有iptables和IPVS，iptables因为扩展性和性能不好，越来越多的厂商正开始使用IPVS模式。

K8S Service有这么几种类型：ClusterIP，NodePort 和Load Balancer。
* 其中，ClusterIP是默认类型，自动分配集群内部可以访问的虚IP——Cluster IP。
* NodePort为Service在Kubernetes集群的每个Node上分配一个端口，即NodePort，集群内/外部可基于任何一个NodeIP:NodePort的形式来访问Service。因此NodePort也成为“乞丐版”的Load Balancer，对于那些没有打通容器网络和主机网络的用户，NodePort成了他们从外部访问Service的首选。
* LoadBalancer类型的Service需要Cloud Provider的支持，因为Service Controller会自动为之创建一个外部LB并配置安全组，K8S原生支持的Cloud Provider就那么几个：GCE，AWS。除了“外用”，Load Balancer还可以“内服”，即如果要在集群内访问Load Balancer类型的Service，kube-proxy用iptables或ipvs实现了云服务提供商LB（一般都是L7的）的部分功能：L4转发，安全组规则等。

使用NodePort类型的Service，但这种“屌丝”的做法除了要求集群内Node有对外访问IP外，还有一些已知的性能问题
使用LoadBalancer类型的Service？它又要求在特定的云服务上跑K8S。而且Service只提供L4负载均衡功能，而没有L7功能，一些高级的，L7的转发功能，比如：基于HTTP header，cookie，URL的转发就做不了。
在K8S中，L7的转发功能，集群外访问Service，这些功能是专门交给Ingress的。

NodePort Service的特点就是Kubernetes集群将为这个Service分配一个高位的随机端口，并在所有的集群节点上开启这个端口。通过集群中任何一个节点的IP地址加上Service被分配到的端口就可以访问Service后端的容器应用。

K8S Service创建好了，那么如何使用，即如何进行服务发现呢？K8S提供了两种方式：环境变量和域名。
* 环境变量即Kubelet为每个Pod注入所有Service的环境变量信息，这种方式的缺点是：容易环境变量洪泛，docker启动参数过长影响性能甚至直接导致容器启动失败。
* 域名的方式是，假设Service（my-svc）在namespace（my-ns）中，暴露名为http的TCP端口，那么在K8S的DNS服务器会生成两种记录，分别是A记录：域名（my-svc.my-ns）到Cluster IP的映射和SRV记录，例如：_http._tcp.my-svc.my-ns到一个http端口号的映射。

Kubernetes用于服务发现的DNS，经历了Sky-DNS,Kube-DNS和最新一代的CoreDNS，它采用更模块化，可扩展的框架构建。

---

摘自 《深入浅出 serverless》：

```
$ docker ps | awk '{print $2}'

#获取Nginx服务的NodePort端口
$ export nginx_port=$( kubectl -n openwhisk describe service nginx | grep https-api | grep NodePort| awk '{print $3}' | cut -d'/' -f1)
#获取API Gateway服务的NodePort端口
$ export api_port=$( kubectl -n openwhisk describe service apigateway | grep mgmt | grep NodePort| awk '{print $3}' | cut -d'/' -f1)
#获取虚拟机的IP地址
$ export host_ip=$( ip a show   eth0|grep global|cut -d ' ' -f 6|cut -d '/' -f 1)
#创建ConfigMap对象
$ kubectl -n openwhisk create configmap whisk.ingress \
    --from-literal=api_host="$host_ip:$nginx_port" \
    --from-literal=apigw_url="http://$host_ip:$api_port"
```

---

https://kubeapps.com/

Kubeapps是一个基于Web的UI，用于在Kubernetes集群中部署和管理应用程序