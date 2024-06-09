# 1.QT的概述

## 1.1 QT的特点
+ 是一个跨平台的C++应用程序开发框架
+ 投资少、周期短、见效快、效益高
+ 几乎支持所有的平台，可用于桌面程序开发以及嵌入式开发
+ 有属于自己的事件处理机制

QT是标准C++的扩展，C++的语法在QT中都是支持的
+ 良好封装机制使得QT的模块化成都高，可用性好，可快速上手
+ QT提供了一种称为signal/slots的安全类型来替代callback，使得各个元件之间的协同工作变得十分简单。

广泛应用于开发GUI程序，也可用于开发非GUI程序

+ graphical user interface
有丰富的API
+ QT包括达250个以上的C++类
+可以处理正则表达式
支持2D/3D图形渲染，支持OPENGL
QT有详细的官方文档
支持XML,JSON
框架底层模块化，使用者可以根据需求选择相应的模块

## 1.2QT中的模块

Qt类库里大量的类根据功能分为各种模块，这些模块又分为以下几大类：

Qt 基本模块（Qt Essentials)：提供了 Qt 在所有平台上的基本功能。
Qt 附加模块（Qt Add-Ons)：实现一些特定功能的提供附加价值的模块。
增值模块（Value-AddModules)：单独发布的提供额外价值的模块或工具。
技术预览模块（Technology Preview Modules）：一些处于开发阶段，但是可以作为技术预览使用的模块。
Qt 工具（Qt Tools)：帮助应用程序开发的一些工具。
Qt官网或者帮助文档的“All Modules”页面可以查看所有这些模块的信息。以下是官方对Qt基本模块的描述

| 模块 | 描述 |
|---|---|
|Qt Core | Qt 类库的核心，所有其他模块都依赖于此模块 |
|Qt GUI  |设计 GUI 界面的基础类，包括 OpenGL |
| Qt Multimedia |音频、视频、摄像头和广播功能的类 |
| Qt Multimedia Widgets |实现多媒体功能的界面组件类 |
| Qt Network |使网络编程更简单和轻便的类 |
| Qt QML |用于 QML 和 JavaScript语言的类 |
| Qt Quick |用于构建具有定制用户界面的动态应用程序的声明框架 |
| Qt Quick Controls |创建桌面样式用户界面，基于 Qt Quick 的用户界面控件 |
| Qt Quick Dialogs |用于 Qt Quick 的系统对话框类型 |
| Qt Quick Layouts |用于 Qt Quick 2 界面元素的布局项 |
| Qt SQL | 使用 SQL 用于数据库操作的类 |
| Qt Test | 用于应用程序和库进行单元测试的类 |
| Qt Widgets | 用于构建 GUI 界面的 C++ 图形组件类 |

## 1.3 安装QT

由于2020年以后，5.15版本之后，官方不再提供编译好的版本，所以这里推荐先安装5.14.2版本的QT使用
https://download.qt.io/archive/qt/5.14/5.14.2/

下载库  MinGW 32-bit 兼容性比较好
        minGW 64-bit 兼容性差一点
        Sources

配置环境变量
C:\Qt\Qt5.14.2\5.14.2\mingw73_32\bin
C:\Qt\Qt5.14.2\Tools\mingw730_32\bin

参考：
https://subingwen.cn/qt/qt-primer/