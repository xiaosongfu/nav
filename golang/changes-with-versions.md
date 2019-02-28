## go 1.12

* go tool vet 不再支持
请使用 `go vet` 代替 `go tool vet`。

* go tour 不再包含在主二进制发行版中。

要在本地运行 tour，不再是运行 `go tool tour`，而需要手动安装它：

```
go get -u golang.org/x/tour
tour
```