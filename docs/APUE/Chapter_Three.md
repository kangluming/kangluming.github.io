# 文件I/O

## 文件描述符
> 对于内核而言，所有打开的文件都通过文件描述符引用。文件描述符是一个非负整数。当打开一个现有文件或创建一个新文件时，内核向进程返回一个文件描述符。

## 函数open和openat

```C++
#include <fcnt1.h>
int open(const char *path, int oflag, .../* mode_t mode */)
int openat()

```
以下参数在fcntl.h中定义

|参数|描述|
|----|----|
|O_RDNLY||
|O_WRONLY||
|O_EXEC||
|O_APPEND||
|O_CLOEXEC||
|O_CREAT||


## 函数creat
## 函数close
```c++
#inlcude <unistd.h>
int close (int fd);
```

## 函数lseek
## 函数read
## 函数write