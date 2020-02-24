```
steps:
- name: docker  
  image: plugins/docker
  settings:
    username: kevinbacon
    password: pa55word
    repo: foo/bar
    tags:
      - latest
      - '1.0.1'
      - '1.0'


或者

tags: '1.0.0'
```

tags 除了 latest，其他的都必须是字符串，必须用 '' 包裹起来！！！