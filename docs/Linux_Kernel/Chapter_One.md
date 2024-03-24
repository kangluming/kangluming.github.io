## 概述

### 1.1 Linux 的诞生和发展

Linux 操作系统是 UNIX 操作系统的一种克隆系统。
Linux 操作系统的诞生、发展和成长过程依赖于以下五个重要支柱： UNIX 操作系统、 MINIX 操作系统、 GNU 计划、 POSIX 标准和 Internet 网络。

![Alt text](image.png)

##### as汇编命令
3.2.6.1 .align abs-expr1, abs-expr2, abs-expr3
3.2.6.2 .ascii "string"...
3.2.6.3 .asciz "string"...
3.2.6.4 .byte expressions
3.2.6.5 .comm symbol, length
3.2.6.6 .data subsection
3.2.6.7 .desc symbol, abs-expr
3.2.6.8 .fill repeat, size, value
3.2.6.9 .global symbol （或者.globl symbol）
3.2.6.10 .int expressions
3.2.6.11 .lcomm symbol, length
3.2.6.12 .long expressions
3.2.6.13 .octa bignums
3.2.6.14 .org new_lc, fill
3.2.6.15 .quad bignums
3.2.6.16 .short expressions （同.word expressions）
3.2.6.17 .space size, fill
3.2.6.18 .string "string"
3.2.6.19 .text subsection
3.2.6.20 .word expressions

3.2.8 AS 汇编器命令行选项
-a 开启程序列表
-f 快速操作
-o 指定输出的目标文件名
-R 组合数据区和代码区
-W 取消警告信息

使用 gcc 汇编器编译 C 语言程序时通常会经过四个处理阶段，即预处理阶段、编译阶段、汇编阶段和
链接阶段，见图 3-3 所示。
![Alt text](image-1.png)

```
gcc [ 选项 ] [ -o outfile ] infile ...

gcc -o hello hello.c // 编译 hello.c 程序，生成执行文件 hello。
gcc -S -o hello.s hello.c // 编译 hello.c 程序，生成对应汇编程序 hello.s。
gcc -c -o hello.o hello.c // 编译 hello.c 程序，生成对应目标文件 hello.o 而不链接。

```

### 3.3.2嵌入汇编
具有输入和输出参数
的嵌入汇编语句的基本格式为：
```
asm(“ 汇编语句”
: 输出寄存器
: 输入寄存器
: 会被修改的寄存器);
```
> 除第 1 行以外，后面带冒号的行若不使用就都可以省略。

这里列出了 kernel/traps.c 文件中第 22 行开始的
一段代码作为例子来详细解说。
```
01 #define get_seg_byte(seg,addr) \
02 ({ \
03 register char __res; \ // 定义了一个寄存器变量__res。
04 __asm__("push %%fs; \ // 首先保存 fs 寄存器原值（段选择符）。
05 mov %%ax,%%fs; \ // 然后用 seg 设置 fs。
06 movb %%fs:%2,%%al; \ // 取 seg:addr 处 1 字节内容到 al 寄存器中。
07 pop %%fs" \ // 恢复 fs 寄存器原内容。
08 :"=a" (__res) \ // 输出寄存器列表。
09 :"0" (seg),"m" (*(addr))); \ // 输入寄存器列表。
10 __res;})
```

AT&T 格式 和 intel 格式