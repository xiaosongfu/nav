https://drone.io/
https://docs.drone.io/
http://plugins.drone.io/
https://discourse.drone.io/


https://github.com/drone/drone-go
https://github.com/drone/drone-cli
https://github.com/drone/doc


---

Drone 是一个持续交付平台，可帮助您的组织优化和自动化软件交付。

dron 是一种基于容器技术的持续交付系统。Drone 使用简单的 YAML 配置文件（docker-compose的超集），来定义和在 Docker 容器中执行 Pipelines。

---

plugins 是 Docker 容器，用于执行预定义的任务，并配置为 pipeline 中的步骤。插件可用于部署代码，发布工件，发送通知等。

---

Drone 在存储库的根目录中查找特殊的 `.drone.yml` 文件以获取管道定义。

每个步骤就是个容器，每个插件也是个容器。

drone 自身是不管每个步骤是什么功能的，只傻瓜式的帮你起容器，执行命令，跑完正常就执行下个步骤，失败就终止。

---

## 在 1.0.0 中，pipeline 配置语法发生了显着变化

这种语法的灵感来自 kubernetes，并且对已经采用 kubernetes 的很大一部分 Drone 社区人员应该是熟悉的。

这个官方文档 https://docs.drone.io/user-guide/pipeline/migrating/ 描述了改动，特别的是，对插件的配置改到了 settings 域下面，例如：

```
steps:
- name: publish
  image: plugins/docker
  settings:
    repo: octocat/hello-world
    username: octocat
    password: 
      from_secret: docker_password
```

---

commands 域的命令会被转为 shell 脚本，并作为 docker 容器的 entrypoint，演进流程如下：

```
# 定义 commands
steps:
- name: build
  image: golang
  commands:
  - go build
  - go test

# 转换为 shell script
#!/bin/sh
set -e

go build
go test

# 作为 docker 容器的 entrypoint
docker run --entrypoint=build.sh golang
```