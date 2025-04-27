# Headline

> An awesome project.





```c++

void algorithm(int n) {
    int a = 2;    1
    a = a + 1;  1
    a = a * 2;  1
    // 循环 n 次
    for (int i = 0; i < n; i++) {  
        cout << 0 << endl;         1
    }
}


时间复杂度   3+n = O(n)
```

```c++
void algorithm(int n) {
    int a = 1;  // +0（技巧 1）
    a = a + n;  // +0（技巧 1）
    // +n（技巧 2）
    for (int i = 0; i < 5 * n + 1; i++) {
        cout << 0 << endl;
    }
    // +n*n（技巧 3）
    for (int i = 0; i < 2 * n; i++) {
        for (int j = 0; j < n + 1; j++) {
            cout << 0 << endl;
        }
    }
}

5n+2n*n = 5n^2+2n
时间复杂度 5n^2+2n = O(n^2)

```


```c++
/* 对数阶（循环实现） */
int logarithmic(int n) {
    int count = 0;
    while (n > 1) {
        n = n / 2;
        count++;
    }
    return count;
}

n = n/2
2^x = n
x = log2n
时间复杂度 O(logn)
```
6
123456

插入一个3  在 34之间

a[3] = 3

1 2 3 3 4 5 

删除 334 中间的3 

1 2 3 4 5 

源码 


a[3] ={1,2,3};
for(int i=0;i<3;i++){
    print (a[i]);
}
print ()



