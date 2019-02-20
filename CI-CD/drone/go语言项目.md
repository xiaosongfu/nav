## go docker image 说明

参考：https://hub.docker.com/_/golang

使用此 image 最直接的方法是使用 Go 容器作为构建和运行时环境。在 Dockerfile 中，按照以下方式编写内容将编译并运行您的项目：

```
FROM golang:1.8

WORKDIR /go/src/app
COPY . .

RUN go get -d -v ./...
RUN go install -v ./...

CMD ["app"]
```

## 官方示例

https://docs.drone.io/examples/language/golang/