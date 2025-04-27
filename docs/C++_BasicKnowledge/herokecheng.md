# 面向对象

```C++
#include <iostream>

using namespace std;

class Hero{
public:

    Hero(){
        cout << "默认构造函数" << endl;
    }
    //有参构造
    Hero(int hp) {
        m_Hp = hp;
        cout << "有参构造" << endl;
    }
    //拷贝构造
    Hero(const Hero& h) {
        m_Hp = h.m_Hp;
        cout << "拷贝构造函数" << endl;
    }

    ~Hero() {
        cout << "析构函数" << endl;
    }
private:
    int m_Hp;
};

/**
 * 拷贝构造函数的调用时机
 * 1.用已经创建的对象来初始化对象
 * 2.函数的传参
 * 3.函数的返回值
 */

int fun1() {
    cout << "------------------fun1-------------------" << endl;
    Hero h1(20);
    Hero h2(h1);
}


void test1(Hero h) {

}
void test2(Hero *h) {0000000000000

}
//2.函数的传参
void fun2() {
    cout << "------------------fun2---------------------" << endl;
    Hero h1;
    //test1(h1); 发生拷贝构造
    test2(&h1);
}
//3.函数的返回值
Hero test3() {
    Hero h(40);
    return h;
}
void fun3() {
    cout << "------------------fun3----------------------" << endl;
    Hero h = test3();
}
int main() {
    fun1();
    fun2();
    fun3();
    return 0;
 }
```




静态成员函数
1、所有对象共享函数
2、静态成员函数只能使用静态成员变量，无法使用普通成员变量

# 5.对象特性
## 5-7 this指针

```C++
/*
this指针的用途：
1、当形参和成员变量同名时，可用this指针来区分    解决命名冲突
2、在类的非静态成员函数中返回对象本身，可使用return *this   *this救救可以获取到这个对象本身

this   *this
&h    *(&h)  == h

*/

#include <iostream>
using namespace std;

class Hero{
public:
    Hero(int hp) {
        this->hp = hp;
        cout << this << endl;
        cout << (*this).hp << endl;
    }
    int hp;

}

int main() {
    Hero h(100);
    cout << h.hp <<endl; 
    cout << &h <<endl; 
    cout << (*(& h)).hp << endl;
}

```

## 5-8 const修饰成员函数


```C++
#include <iostream>
using namespace std;

// 常函数



int main() {
    
}


```

