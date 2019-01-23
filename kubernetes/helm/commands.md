
#### Install Chart

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

---

You can deploy this chart with `helm install docs/examples/nginx` . Or you can see how this chart would render with `helm install --dry-run --debug docs/examples/nginx` .

