## 认识几个术语

WebAssembly、WASM、WASI——最近这些关键字开始活跃，但是它们都是什么意思呢？

首先 WebAssembly 是 Web+Assembly 的拼接词，字面意思就是 Web 汇编语言。真实的 WebAssembly 也是 Web 汇编语言的意思，它是诞生在 Web 社区的国际标准，是为了解决 JS 性能低下的问题而提出的终极的解决方案。WASM 则是 WebAssembly 的缩写，同时 WebAssembly 对应的二进制模块文件很多是以 .wasm 作为后缀名。

而 WASI 则是WebAssembly System Interface的缩写，意思为WebAssembly的操作系统接口。WebAssembly最初诞生于Web社区，只能在浏览器小打小闹，WASI的目标是为了解除浏览器对WebAssembly的禁锢，让WebAssembly模块作为本地应用执行。

## WebAssembly的本质

WebAssembly 本质上就是 Web 汇编语言，文本格式的汇编语言是为了方便阅读，和传统汇编语言中机器指令的助记符是一个思路。使用 WebAssembly 汇编语言编写的程序最终会以二进制保存为模块。而以二进制文件保存的模块最终会被 WebAssembly 虚拟机执行。

因此WebAssembly其实分为三个层面：最上层是汇编语言，中间是二进制文件的格式，下层是WebAssembly虚拟机。可以将其和Java的JVM虚拟机进行类比，是跨平台的汇编语言。WebAssembly功能比不上Java的JVM强大，但是WebAssembly是国际标准是其最大的优势。

---

## WebAssembly

https://webassembly.org/
https://github.com/WebAssembly

## WebAssembly System Interface

https://wasi.dev/
https://github.com/WebAssembly/WASI

## Emscripten

Emscripten是一个工具链，用于编译使用LLVM构建的asm.js和WebAssembly，它允许您以接近本机的速度在Web上运行C和C ++而无需插件。

https://emscripten.org/

