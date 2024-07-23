# 操作系统





![操作系统](image-4.png)


![CPU开机阶段做的事情](image-5.png)
```bash
go: mov ax,cs
    mov ds,ax
    mov es,ax
    mov ss,ax
    mov sp,#0xFF00


jmpi go,0x9000
```

![CPU 寄存器图](image-3.png)