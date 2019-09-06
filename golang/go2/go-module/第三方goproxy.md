* https://athens.azurefd.net
* https://goproxy.io
* https://gocenter.io

---

* goproxy.cn：由七牛云运行，支持代理 sum.golang.org，经过 CDN 加速，高可用，可应用进公司复杂的开发环境中，亦可用作上游代理；
* mirrors.aliyun.com/goproxy：由阿里云运行，不支持 sumdb 代理，经过 CDN 加速，高可用，可应用进公司复杂的开发环境中，亦可用作上游代理；
* goproxy.io：由个人运行，支持代理 sum.golang.org。

---

## 1. athens

* https://github.com/gomods/athens
* https://docs.gomods.io/

我们还运行了一个体验版本的 Athens,因此你什么都不需要安装也能开始。为此，你需要设置环境变量 GOPROXY="https://athens.azurefd.net".

参考文章：[为 Go module 搭建私服](http://blog.cyeam.com/golang/2018/09/27/athens)

## 2. goproxy.io

* https://github.com/goproxyio/goproxy
* https://goproxy.io/
* goproxy.io for Go modules : https://mp.weixin.qq.com/s/COethtOaiygsYev-kkCc4A

## 3. thumbai

https://github.com/thumbai/thumbai

## 4. GoCenter

2019年01月30日，JFrog 正式宣布 Gopher 世界的第一个中心式 immutable Modules 仓库服务正式运行！截至目前已经收录45k个modules。使用Go 1.11及以后版本的 Gopher 可以通过设置 `export GOPROXY=https://gocenter.io` 来使用该中心服务。

* The Central Go Modules Repository：  https://gocenter.jfrog.com/stats
* Github：https://github.com/jfrog/gocenter
* 版本历史：https://github.com/jfrog/gocenter/blob/master/releases.md

官网还提供了一个脚本 `curl -fL https://getgoc.gocenter.io | sh`，该脚本的功能是下载 `goc` 工具，该工具的功能很简单，它包装了 官方的 `go` 工具，通过设置 `GOPROXY=https://gocenter.io` 来实现从 GoCenter 获取依赖，如果 GoCenter 没有收录该module，则会取消设置 `GOPROXY` ，转而使用 `go` 工具的默认行为。

* https://github.com/jfrog/goc

有3种方法从 GoCenter 解析 Go module：
* 使用 `goc`

使用GoCenter的最简单方法是为go客户端安装goc包装器。goc自动设置GOPROXY指向GoCenter，然后只需调用go客户端。要安装goc，请使用提供的curl命令或遵循goc的GitHub页面中的安装说明。
然后，从项目的根目录运行任何命令，就像运行go一样，例如：goc buildgoc的另一个优点是它将回退到GoCenter中尚未包含的软件包的源代码控制下载，建议在GoCenter提供您将需要的所有依赖项之前，因为此功能在官方go客户端中仍然不可用。

* 使用 `go`

使用这种方法，你需要设置 GOPROXY：`export GOPROXY=https://gocenter.io`，但是请注意，您可能会遇到未收录的包。在这种情况下，go客户端不会自动回退到源代码控制下载。

* 设置 repository manager 来代理 GoCenter

如果您使用的是诸如Artifactory或Athens之类的存储库管理器，则只需要在存储库管理器中指向GOPROXY，并确保将GoCenter作为远程存储库（Artifactory中的开箱即用）包含在内。有关解析不在GoCenter中的模块的说明，请参阅JFrog CLI文档。

## 5. https://goproxy.cn

https://github.com/goproxy/goproxy.cn/blob/master/README.zh-CN.md

* [goproxy.cn - 为中国 Go 语言开发者量身打造的模块代理](https://mp.weixin.qq.com/s/Pw_a5heUgyIkuJrXF4HCVg)
* [Go 模块代理超大型库初始化速度实测：goproxy.cn vs goproxy.io](https://studygolang.com/topics/9994)

## 6. https://mirrors.aliyun.com/goproxy