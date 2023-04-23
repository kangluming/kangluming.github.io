# cs631 APUE

## env setup

```shell

$ ftp https://stevens.netmeister.org/631/apue-code.tar.gz
$ tar zxvf apue-code.tar.gz

```

#### echo

$ echo "CFLAGS='-Wall -Werror -Wextra'" >> ~/.shrc
$ echo "alias cc='c \${CFLAGS}'">>~/.shrc



编译代码 <br>

cc -Wall -Werror -Wextra simple-ls.c <br>
