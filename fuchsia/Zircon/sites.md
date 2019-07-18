## xx

https://fuchsia.googlesource.com/fuchsia/+/refs/heads/master/zircon/

Zircon is the core platform that powers the Fuchsia OS. 

## xx

Zircon 由微内核和一小组用户空间服务，驱动程序和 库(系统启动，与硬件通信，加载
用户空间进程并运行它们所必须的库)组成。

Zircon Kernel提供系统调用来管理进程，线程，虚拟内存，进程间通信，等待对象状态更改和锁定（通过futexes）。

