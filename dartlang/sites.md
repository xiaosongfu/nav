## Dartlang 官方资源

Dartlang 官网 - [dartlang.org](https://www.dartlang.org/)  
Dartlang 中文官网 - [dartdoc.cn](http://www.dartdoc.cn/)

Google 提供的镜像站点 dartpad.cn

> 子域名

|   子域名  |    说明   |
| :-------- | :------  |
| [news.dartlang.org](https://news.dartlang.org) | Dart news |
| [api.dartlang.org](https://api.dartlang.org) | API reference |
| [dartpad.dartlang.org](https://dartpad.dartlang.org) | DartPad |
| [pub.dartlang.org](https://pub.dartlang.org/) | Pub packages |
| [events.dartlang.org](https://events.dartlang.org) | Events |

> pub

https://pub.dartlang.org/
https://pub.flutter-io.cn/

> api

Dart API reference： api.dartlang.org
Flutter API reference.： docs.flutter.io

> doc

http://www.dartdocs.org/ --> 跳转到： https://pub.dartlang.org/

---

Dart Markdown Live Editor：https://dart-lang.github.io/markdown/

## Dartlang 中文资源

> Dartlang 中文网

Dartlang 中文网 - [www.dartlang.cc](http://www.dartlang.cc/)  

> Dart 中文社区

Dart 中文社区 - [dart-china.org](https://www.dart-china.org/)  
Dart 语言中文社区 - [cndartlang.com](http://www.cndartlang.com/)  

---

## 其他

[medium.com/dartlang](https://medium.com/dartlang)  

---

可以不指定返回值的类型

单表达式函数可以使用箭头语法

可选命名参数 可选位置参数

生成构造方法  命名构造方法 重定向构造函数 常量构造函数 工厂构造函数
构造函数的名字可以是 ClassName 或者 ClassName.identifier

初始化参数列表

抽象方法只存在于抽象类中

import 参数只需要一个指向库的 URI。对于内置库，URI 拥有自己特殊的 `dart:` 方案。对于其他的库，使用系统文件路径或者 `package:` 方案 。

如果导入两个存在标识符冲突的库，则可以为这两个库，或者其中一个指定前缀。

如果你只使用库的一部分功能，则可以选择需要导入的内容。

延迟加载可以让应用在需要的时候再加载库。

---

空感知操作符

···
if (price == null) {
   print("FREE");
} else {
   print(price);
}
···

等同于：`print(price??"FREE")`  => NULL AWARE OPERATORS