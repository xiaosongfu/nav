```
kind: pipeline
name: default


kind: secret


kind: signature
hmac: F10E2821BBBEA527EA02200352313BC059445190


# --------------

workspace:
  base: /go
  path: src/github.com/octocat/hello-world




clone:
  depth: 50
  disable: true



platform:
  os: linux
  arch: arm64




volumes:
  - name: docker
    host:
      path: /var/run/docker.sock


volumes:
  - name: cache
    host:
      path: /var/lib/cache

services:
  - name: database
    image: mysql
    entrypoint: [ mysqld ]


services:
  - name: database
    image: postgres
    environment:
      POSTGRES_USER: postgres
      POSTGRES_DB: test


trigger:
  branch:
    - master
  event:
    - push
  status:
    - success
    - failure


node:
  instance: highmem




steps:

  - name: frontend
    image: node
    commands:
      - npm install
      - npm test

  - name: backend
    image: golang
    commands:
      - go build
      - go test



  - name: build
    image: golang
    environment:
      GOOS: linux
      GOARCH: amd64
      CGO_ENABLED: 0
# environment 可以是数组或者字典



  - name: build
    image: golang
    privileged: true
    pull: always
    volumes:
      - name: docker
        path: /var/run/docker.sock



  - name: clone
    image: docker:git
    commands:
      - git clone https://github.com/octocat/hello-world.git
      - git submodule update --recursive --remote
      - git checkout $DRONE_COMMIT



  - name: integration
    image: golang
    commands:
      - go test -v
    when:
      event:
        - pull_request
        - push
      branch:
        - master
        - feature/*



  - name: notify
    image: plugins/slack
    settings:
      room: general
      webhook: https://...




  - name: build
    image: alpine
    environment:
      USERNAME:
        from_secret: username
      PASSWORD:
        from_secret: password
# 将 secrets 暴露为环境变量



  - name: build
    image: plugins/docker
    settings:
      repo: octocat/hello-world
      tags: latest
      username:
        from_secret: username
      password:
        from_secret: password
# 从 secrets 中加载插件的配置值



  - name: build
    image: golang
    commands:
      - go build
      - go test
    when:
      branch:
        - master
      event:
        - push
        - pull_request
        - tag
        - promote
        - rollback
      ref:
        - refs/heads/feature-*
        - refs/tags/v1.*
      repo:
        - octocat/hello-world
      instance:
        - drone.instance1.com
        - drone.instance2.com
      target:
        - production

  - name: notify
    image: plugins/slack
    when:
      status:
        - success
        - failure
# 配置  status 为 success 重复了。
# The default behavior is for pipeline steps to only execute when the pipeline is in a passing state.
```