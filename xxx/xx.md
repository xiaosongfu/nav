Vendor 机制
默认情况下，Go modules 会忽略 vendor/ 目录。这个想法是最终废除掉 vendor 机制[^1]。但如果我们仍然想要在我们的版本管理中添加 vendor 机制管理依赖，我们还是可以这么做的：

$ go mod vendor

这会在你项目的根目录创建一个 vendor/目录，并包含你的项目的所有依赖项。

即使如此，go build 默认还是会忽略这个目录的内容，如果你想要构建的时候从 vendor/ 目录中获取依赖的代码来构建，那么你需要明确的指示：

$ go build -mod vendor




go.mod文件可以通过require，replace和exclude语句使用的精确软件包集。

require语句指定的依赖项模块
replace语句可以替换依赖项模块
exclude语句可以忽略依赖项模块




https://studygolang.com/articles/14588