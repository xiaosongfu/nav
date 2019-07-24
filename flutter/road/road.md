# 1. 入门

### 基础

* https://flutterbyexample.com/

* 阅读官方文档：https://flutter.io/docs

* 可以考虑按照这个顺序全部看一下：[Solido/awesome-flutter](https://github.com/Solido/awesome-flutter)

* “Flutter is awesome, but where do I start learning?”: https://medium.freecodecamp.org/learn-flutter-best-resources-18f88346ed0f

### widget

通过参考官方文档来，一个是按索引查看，一个是按分类查看

* widget index -> widget 索引：https://flutter.io/docs/reference/widgets
* Widget catalog -> widget 分类：https://flutter.io/docs/development/ui/widgets

20多个示例演示 flutter 里基础 widget
https://github.com/PoojaB26/FlutterBasicWidgets

# 2. Embedder、Engine、Framework

* Flutter 实现原理及在马蜂窝的跨平台开发实践
https://mp.weixin.qq.com/s/WBnj_6sOonjR9XUnB-wZPA
重点阅读！！！！
    * Embedder 是嵌入层，做好这一层的适配 Flutter 基本可以嵌入到任何平台上去；
    * Engine 层主要包含 Skia、Dart 和 Text。Skia 是开源的二位图形库；Dart 部分主要包括 runtime、Garbage Collection、编译模式支持等；Text 是文本渲染。
    * Framework 在最上层。我们的应用围绕 Framework 层来构建，因此也是本文要介绍的重点。