## secrets 可以暴露给环境变量或者插件

```
  - name: build
    image: alpine
    environment:
      USERNAME:
        from_secret: username
      PASSWORD:
        from_secret: password
```

```
- name: build
    image: plugins/docker
    settings:
      repo: octocat/hello-world
      tags: latest
      username:
        from_secret: username
      password:
        from_secret: password
```

## secrets 可以加密