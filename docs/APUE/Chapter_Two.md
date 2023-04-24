# UNIX标准及实现

## UNIX标准化

### ISO C

### IEEE POSIX

### Single UNIX Specification

### FIPS


### SVR4

## UNIX 系统实现

## 限制
### IOS C 限制
### POSIX 限制
### XSI 限制

### 函数sysconf、pathconf和fpathconf

```C
#include <unistd.h>
long sysconf(int name);
long pathconf(const char *pathname, int name);
long fpathconf(int fd, int name);
```

表1 sysconf的限制及name参数

|  Name of limit       | Description  | name argument |
|  ----                | ----  | ---- |
| ARG_MAX              | maximum length, in bytes, of arguments to the exec functions | _SC_ARG_MAX |
| ATEXIT_MAX           | maximum number of functions that can be registered with the atexit function | _SC_ATEXIT_MAX |
| CHILD_MAX            | maximum number of processes per real user ID | _SC_CHILD_MAX |
| clock ticks/second   | number of clock ticks per second | _SC_CLK_TCK |
| COLL_WEIGHTS_MAX    | maximum number of weights that can be assigned to an entry of the LC_COLLATE order keyword in the locale definition file | _SC_COLL_WEIGHTS_MAX |
| HOST_NAME_MAX       | maximum length of a host name as returned by gethostname | _SC_HOST_NAME_MAX |
| IOV_MAX            | maximum number of iovec structures that can be used with readv or writev | _SC_IOV_MAX |
| LINE_MAX           |maximum length of a utility's input line |_SC_LINE_MAX|
| LOGIN_NAME_MAX    |maximum length of a login name | _SC_LOGIN_NAME_MAX|
| NGROUPS_MAX       |maximum number of simultaneous supplementary process group IDs per process | _SC_NGROUPS_MAX|
| OPEN_MAX|maximum number of open files per process |_SC_OPEN_MAX |
|PAGESIZE | system memory page size, in bytes| _SC_PAGESIZE|
| PAGE_SIZE|system memory page size, in bytes | _SC_PAGE_SIZE|
| RE_DUP_MAX| number of repeated occurrences of a basic regular expression permitted by the regexec and regcomp functions when using the interval notation /{m,n/}|_SC_RE_DUP_MAX |
| STREAM_MAX| maximum number of standard I/O streams per process at any given time; if defined, it must have the same value as FOPEN_MAX| _SC_STREAM_MAX|
|SYMLOOP_MAX |number of symbolic links that can be traversed during pathname resolution | _SC_SYMLOOP_MAX|
|TTY_NAME_MAX |length of a terminal device name, including the terminating null | _SC_TTY_NAME_MAX|
|TZNAME_MAX | maximum number of bytes for the name of a time zone| _SC_TZNAME_MAX|


## 基本系统数据类型
一些常用的基本系统数据类型

| 类型|说明 |
|----|----|
|clock_t	|时钟滴答计数器（进程时间）|
|comp_t	|压缩的时钟滴答|
|dev_t	|设备号（主和次）|
|fd_set|	文件描述符集|
|fpos_t	|文件位置|
|gid_t	|数值组ID|
|ino_t	|i节点编号|
|mode_t	|文件类型，文件创建模式|
|nlink_t	|目录项的链接计数|
|off_t	|文件大小和偏移量（带符号的）|
|pid_t|	进程ID和进程组ID（带符号的）|
|ptrdiff_t|	两个指针相减的结果（带符号的）|
|rlim_t	|资源限制|
|sig_atomic_t|	能原子地访问的数据类型|
|sigset_t	|信号集|
|size_t	|对象（例如字符串）大小（不带符号的）|
|ssize_t|	返回字节数的函数（带符号的）（read、write）|
|time_t	|日历时间的秒计数器|
|uid_t	|数值用户ID|
|wchar_t|	能表示所有不同的字符码|

















