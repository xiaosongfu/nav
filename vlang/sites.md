https://vlang.io/

https://github.com/vlang/v


http://gitly.org/


---

Simple, fast, safe language created for developing [Volt](https://volt-app.com/), soon available for everyone. 

Open source release in June 2019. [Early access](https://www.patreon.com/vlang) since April 15.

---
V can translate your entire C/C++ project and offer you the safety, simplicity, and up to 200x compilation speed up. 
V 可以翻译整个 C/C++ 项目，并为您提供安全性，简单性和高达200倍的编译速度。 

V can also emit human readable C, which can then be compiled to run on any platform. This way the compilation speed is about 10 times slower (≈150k lines/second).
V还可以发出人类可读的C，然后可以将其编译为在任何平台上运行。这样编译速度大约慢10倍（≈150k行/秒）。

The entire language and its standard library are less than 400 KB. You can build V in 0.3 seconds.
整个语言及其标准库小于400 KB。你可以在0.3秒内构建 V.

---

自带 Native cross platform UI library

支持 Hot code reloading

支持 REPL

---

V 最初使用 Go 编写，现在改为使用 V 自己编写。

V 不使用 LLVM，它直接编译为机器码。

V 没有 GC，它在编译时管理内存（如Rust）。

V is a very modular language and encourages creation of modules that are easy to reuse. There will be a central package manager, and installing modules will be as easy as
V是一种非常模块化的语言，鼓励创建易于重用的模块。将有一个中央包管理器，安装模块就像这样简单

```
v install sqlite
```


