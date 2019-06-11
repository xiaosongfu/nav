## Go language server

A language server *should* be a core part of each language, built and managed by the core language team. Tooling is so important to the developer experience for any language, and a language server is one of the most important kinds of tooling there is (because the user interacts with it on virtually every keystroke in their editor). So, we're very happy that there will be a Go language server that is owned by the Go team!

Go team计划自己维护一个 language server protocol 的原始实现 ，类似 sourcegragh 的go-langserver - [网页链接](https://go-review.googlesource.com/c/tools/+/136676#message-11c783bc9a9f6adf6119bbb85c89510fda25abe9)

`gopls` is currently under active development by the Go team. The code is in the x/tools repository, in [golang.org/x/tools/internal/lsp](https://golang.org/x/tools/internal/lsp) and [golang.org/x/tools/cmd/gopls](https://golang.org/x/tools/cmd/gopls). 

* 2019-03-14
Go team 的 Rebecca Stambler 宣布 Go 语言的 Language Server Protocol 实现 gopls 进入 alpha 测试状态，邀请广大 gopher 测试验证并提供反馈。gopls 目前支持 vscode 、vim、emacs。gopls 成熟后，gopher 可以用之替换掉维护不那么积极的 gocode 了。




---

## LSP 规范

Language Server Protocol  https://microsoft.github.io/language-server-protocol/

## LSP 实现

sourcegragh 的实现：
https://github.com/sourcegraph/go-langserver
https://langserver.org/