
#### 1. 安装 Chart 命令示例 --> 从官方 stable 仓库安装

To install the Airflow Chart into your Kubernetes cluster :

```
helm install --namespace "airflow" --name "airflow" stable/airflow
```

After installation succeeds, you can get a status of Chart

```
helm status "airflow"
```

If you want to delete your Chart, use this command:

```
helm delete  --purge "airflow"
```

> 安装指定版本：

```
helm install stable/airflow --version 0.13.0
```

参考：https://hub.helm.sh/charts/stable/airflow

#### 2. 安装 Chart 命令示例 --> 从本地 tgz 压缩包安装

```
# 下载 openwhisk 压缩包并解压

$ cd incubator-openwhisk-deploy-kube/helm

$ helm install . --namepace=openwhisk --name=openwhisk
```

---

You can deploy this chart with `helm install docs/examples/nginx` . Or you can see how this chart would render with `helm install --dry-run --debug docs/examples/nginx` .

