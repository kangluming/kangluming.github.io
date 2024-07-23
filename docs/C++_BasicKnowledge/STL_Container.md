# Containers library


# STL_Container

## 顺序容器Sequence containers

## 关联容器Associative containers

### std::set

+ std::set 是一种关联容器，含有 Key 类型对象的已排序集。用比较函数 比较 (Compare) 进行排序。搜索、移除和插入拥有对数复杂度。set 通常以红黑树实现。
+ 标准库使用比较 (Compare) 的规定时，均用等价关系确定唯一性。不精确地说，如果两个对象 a 与 b 相互比较不小于对方：!comp(a, b) && !comp(b, a)，那么认为它们等价。
+ std::set 满足容器 (Container) 、知分配器容器 (AllocatorAwareContainer) 、关联容器 (AssociativeContainer) 和可逆容器 (ReversibleContainer) 的要求。

#### 成员函数Member functions

operator=
赋值给容器
get_allocator
 
返回关联的分配器
#### 迭代器Iterators

| 函数名 | 功能 |
| - | - |
| begin cbegin(C++11)| |
| end cend(C++11) | |
| rbegin crbegin(C++11) | |
| rend crend(C++11) | |

#### 容量Capacity
| 函数名 | 功能 |
| - | - |
| empty | checks whether the container is empty |
| size | 返回元素数 |
| max_size | 返回可容纳的最大元素数 |

#### 修改器Modifiers
| 函数名 | 功能 |
| - | - |
| clear | 清除内容 |
| insert | 插入元素或节点 |
| insert_range(C++23) | 插入一个元素范围 |
| emplace(C++11) | 原位构造元素 |
| emplace_hint(C++11)| 使用提示原位构造元素 |
| erase | 擦除元素 |
| swap | 交换内容 | 
| extract(C++17) | 提取容器中的节点 |
| merge(C++17) | 从另一容器合并节点 |


#### 查找Lookup
| 函数名 | 功能 |
| - | - |
| count | 返回匹配特定键的元素数量 |
| find | 寻找带有特定键的元素 |
| contains(C++20) | 检查容器是否含有带特定键的元素 |
| equal_range | 返回匹配特定键的元素范围 |
| lower_bound | 返回指向首个不小于给定键的元素的迭代器 |
| upper_bound | 返回指向首个大于给定键的元素的迭代器 |

#### 观察器Observers
| 函数名 | 功能 |
| - | - |
| key_comp | 返回用于比较键的函数 |
| value_comp | 返回用于比较 value_type 类型的对象中的键的函数 |

#### 代码示例

```C++

```

### multiset


#### 代码示例

```C++

#include <iostream>
#include <set>
#include <iterator>

int main() {
    // 创建一个空的 multiset
    std::multiset<int> mset;

    // 插入元素
    mset.insert(3);
    mset.insert(1);
    mset.insert(4);
    mset.insert(1);
    mset.insert(5);
    mset.insert(9);

    // 输出 multiset 的内容
    std::cout << "Elements in multiset: ";
    for (auto it = mset.begin(); it != mset.end(); ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;
    // Elements in multiset: 1 1 3 4 5 9 自动排序
    
    // 使用 count() 函数
    std::cout << "Count of element '1': " << mset.count(1) << std::endl;
    // Count of element '1': 2
    
    // 使用 find() 函数
    auto findIt = mset.find(4);
    if (findIt != mset.end()) {
        std::cout << "Element '4' found." << std::endl;
    }
    // Element '4' found.

    // 使用 lower_bound() 和 upper_bound() 函数
    auto lower = mset.lower_bound(2);
    auto upper = mset.upper_bound(5);
    std::cout << "Elements between 2 and 5: ";
    for (auto it = lower; it != upper; ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;
    // Elements between 2 and 5: 3 4 5

    // 使用 equal_range() 函数
    auto range = mset.equal_range(1);
    std::cout << "Range of element '1': ";
    for (auto it = range.first; it != range.second; ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;

    // 使用 erase() 函数
    mset.erase(1);
    std::cout << "Elements after erasing '1': ";
    for (auto it = mset.begin(); it != mset.end(); ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;

    // 使用 clear() 函数
    mset.clear();
    std::cout << "Elements after clearing: " << mset.size() << std::endl;

    return 0;
}


```

### std::map

#### 成员函数Member functions

#### 元素访问

| 函数名 | 功能 |
| - | - |
| at | access specified element with bounds checking (public member function)|
| operator[] | access or insert specified element (public member function)|

#### 迭代器Iterators

| 函数名 | 功能 |
| - | - |
| begin cbegin(C++11)| returns an iterator to the beginning |
| end cend(C++11) | returns an iterator to the end |
| rbegin crbegin(C++11) | returns a reverse iterator to the beginning |
| rend crend(C++11) | returns a reverse iterator to the end |

#### 容量Capacity

| 函数名 | 功能 |
| - | - |
| empty | checks whether the container is empty |
| size | returns the number of elements |
| max_size | returns the maximum possible number of elements |

### std::multiset

### std::multimap


## 无序关联容器Unordered associative containers (since C++11)

unordered_set
  
(C++11)
 
collection of unique keys, hashed by keys
(class template)
unordered_map
  
(C++11)
 
collection of key-value pairs, hashed by keys, keys are unique
(class template)
unordered_multiset
  
(C++11)
 
collection of keys, hashed by keys
(class template)
unordered_multimap
  
(C++11)
 
collection of key-value pairs, hashed by keys
(class template)

## 容器适配器Container adaptors

### std::stack

#### 成员函数Member functions

| 函数名 | 功能 |
| - | - |
| (constructor) | constructs the stack (public member function)  |
| (destructor) | destructs the stack (public member function)|
| operator= | assigns values to the container adaptor (public member function) |
 
#### 元素访问Element access

| 函数名 | 功能 |
| - | - |
| top | accesses the top element (public member function) |
 
#### Capacity

| 函数名 | 功能 |
| - | - |
| empty | checks whether the container adaptor is empty (public member function) |
| size | returns the number of elements(public member function) |

#### Modifiers

| 函数名 | 功能 |
| - | - |
| push | inserts element at the top (public member function)  | 
| push_range(C++23) | inserts a range of elements at the top (public member function) |
| emplace(C++11) | constructs element in-place at the top (public member function)|
| pop | removes the top element(public member function) |
| swap(C++11) | swaps the contents (public member function)|

#### 代码示例

```C++

#include <iostream>
#include <stack>
#include <vector>

using namespace std;

// 将整个 vector 压入栈的函数
template <typename T>
void pushVectorToStack(stack<T>& s, const vector<T>& vec) {
    for (const T& elem : vec) {
        s.push(elem);
    }
}

int main() {
    // 创建一个空栈
    stack<int> s;

    // 使用 push 将元素压入栈
    s.push(5);
    s.push(10);
    s.push(15);

    // 使用 push_range 将整个 vector 压入栈
    vector<int> v = {20, 25, 30};
    //s.push_range(v.begin(), v.end()); 不支持
    // 将整个 vector 压入栈
    pushVectorToStack(s, v);

    // 使用 emplace 向栈中插入新元素（在栈顶）
    s.emplace(35);

    // 输出栈顶元素
    cout << "当前栈顶元素：" << s.top() << endl;

    // 使用 swap 交换两个栈的内容
    stack<int> anotherStack;
    anotherStack.push(100);
    anotherStack.push(200);
    cout << "交换前第二个栈的栈顶元素：" << anotherStack.top() << endl;
    s.swap(anotherStack);
    cout << "交换后第二个栈的栈顶元素：" << anotherStack.top() << endl;

    // 使用 operator= 赋值给另一个栈
    stack<int> copyStack = s;
    cout << "复制栈的大小：" << copyStack.size() << endl;

    // 遍历栈中的元素
    cout << "栈中的元素（自顶向下）：";
    while (!s.empty()) {
        cout << s.top() << " ";
        s.pop(); // 弹出栈顶元素
    }
    cout << endl;

    return 0;
}

```
 
## 容器适配器 Container adaptors

| stack | 适配一个容器以提供栈（LIFO 数据结构） |
| - | - |
| queue | 适配一个容器以提供队列（FIFO 数据结构）|
| priority_queue | 适配一个容器以提供优先级队列 |
| flat_set (C++23) | 调整容器以提供按键排序的唯一键集合 |
| flat_map (C++23) | 适配两个容器以提供按唯一键排序的键值对集合 |
| flat_multiset (C++23) | 调整容器以提供按关键字排序的关键字集合 |
| flat_multimap (C++23) | 适配两个容器以提供按键排序的键值对集合 |

###  stack

+ std::stack 类是一种容器适配器，它给予程序员栈的功能——特别是 FILO（先进后出）数据结构。
+ 该类模板用处为底层容器的包装器——只提供特定函数集合。栈从被称作栈顶的容器尾部推弹元素。
  

 


  

 


 

  

 


 


 


 
