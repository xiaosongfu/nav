https://firebase.google.cn/docs/cli/

---

部署特定的 Firebase 服务
如果您只想部署特定的 Firebase 服务或功能，则可以在 firebase deploy 命令的标志中使用逗号分隔列表。例如，以下命令会部署 Firebase 托管内容和 Cloud Storage 安全规则。

```
firebase deploy --only hosting,storage
```

部署特定函数
部署函数时，您可以定位具体的函数。例如：

```
firebase deploy --only functions:function1
firebase deploy --only functions:function1,functions:function2
```