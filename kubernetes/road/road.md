# 


# 源码

如何顺利完成Kubernetes源码编译？：https://mp.weixin.qq.com/s/km3e5SZbUUMbDe4MLL5NFg
Kubernetes源码编译，大致分为本地二进制可执行文件编译和docker镜像编译两种。
由于Kubernetes每个组件服务的镜像Dockerfile文件是由Kubernetes源码自动生成的，因此，社区并未提供每个组件的镜像Dockerfile文件。