## go 1.13-2019年09月03日

* 现在，Go 命令默认使用 Go module mirror 和 Go checksum 数据库来下载和验证模块
* 数字字面值的改进
* 错误包装
* 默认启用 TLS 1.3
* 改进的模块支持

## go 1.12

* go tool vet 不再支持
请使用 `go vet` 代替 `go tool vet`。

* go tour 不再包含在主二进制发行版中。

要在本地运行 tour，不再是运行 `go tool tour`，而需要手动安装它：

```
go get -u golang.org/x/tour
tour
```

## go 1.11

go 1.11 后 pkg 目录还兼有 mod 功能
