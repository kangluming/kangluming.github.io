# QT窗口

## QWidget窗口类的特点

所有窗口的积累
可以内嵌到其他窗口的内部-无边框（需要给该窗口指定父窗口）
可以作为独立的窗口显示-有边框（不能给该窗口置顶父窗口）
**Qt中所有控件的基类**

## QDialog窗口类的特点
对话窗口类
模态和非模态两种显示方式
不能内嵌

## QMainWindow窗口类的特点

# QT坐标

x轴方向是右边
y周方向是下边

坐标原点在左上角(0,0)

坐标远点随着主题窗口 原点一直在变化
窗口内嵌！

# QT的内存回收机制

QT实现内存的自动回收需要满足以下两个条件：
1.创建的对象必须是QObject类的子类（间接子类也可以）
* QObject类是没有父类的，Qt中有很大一部分类都是从这个类派生出去的
    * Qt中使用频率很高的窗口类和控件都是QObject的直接或者间接的子类
    * 其他的类可以自己查阅QT帮助文档
2.创建出的类对象，必须要指定其父对象是谁，一般情况下有两种操作方式

```C++

// 方式1 ： 通过构造函数
// parent: 当前窗口的父对象，找构造函数中的 parent


// 方式2：通过setParent()方法
// 假设这个控件没有在构造的时候指定父对象，可以通过调用QWidget的api指定父窗口对象


```

# log输出

qDebug类
产生的exe也想执行输出日志，需要在.pro文件 CONFIG += c++11 console 增加conslole

# 字符串类型

```C++
c   => char*
c++ => std::string
Qt  => QByteArray, QString
```

## QByteArray

+ 构造函数

```
// 构造空对象, 里边没有数据
QByteArray::QByteArray();
// 将data中的size个字符进行构造, 得到一个字节数组对象
// 如果 size==-1 函数内部自动计算字符串长度, 计算方式为: strlen(data)
QByteArray::QByteArray(const char *data, int size = -1);
// 构造一个长度为size个字节, 并且每个字节值都为ch的字节数组
QByteArray::QByteArray(int size, char ch);

```

+ 数据操作

```

```


# QVariant

+ QVariant这个类很神奇，或者说方便。很多时候，需要几种不同的数据类型需要传递，如果用结构体，又不大方便，容器保存的也只是一种数据类型，而QVariant则可以统统搞定。
+ QVariant 这个类型充当着最常见的数据类型的联合。QVariant 可以保存很多Qt的数据类型，包括QBrush、QColor、QCursor、QDateTime、QFont、QKeySequence、 QPalette、QPen、QPixmap、QPoint、QRect、QRegion、QSize和QString，并且还有C++基本类型，如 int、float等。



# 位置和尺寸

QPoint


# 日期和时间
