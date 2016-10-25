## pickphase

### 概要

告诉SAC从一个用户定义的参考文件中读入震相列表（也可能是作者信息），或在
该命令行上输入震相列表

### 语法

``` {.bash}
PICKPHASE header phase author [header phase author ...]
PICKPHASE FILE [filename]
PICKPHASE AUTHOR [filename]
```
``` {.bash}
PICKPH header phase author [header phase author ...]
PICKPH FILE [filename]
PICKPH AUTHOR [filename]
```

### 输入

- `header`: 头段变量名：`t0-t9`
- `phase`: 对于给出的头段变量对应的拾取的震相名
- `author`: 告诉SAC作者列表，为某个头段所对应的作者，或者是 `-`
- `FILE`: 如果使用了 `FILE` 选项，SAC将从参考文件中读取震相列表。
    如果参考文件的文件名在命令行上给出，则SAC将读取这个指定的文件，否则
    SAC将根据上一次执行 `pickphase` 读取最近输入的文件名。如果
    未给出文件名，则SAC使用 `$SACAUX/csspickprefs`
- `AUTHOR`: 与 `FILE` 选项相似，其另一个功能是允许SAC读取指定的 头段变量信息

### 缺省值

``` {.bash}
pickphase file
```

### 说明

`pickphase` 用于在命令行上覆盖参考文件。其可以用于在命令行提供指定
的头段/震相/作者信息，或者将SAC从一个参考文件重定向到另一个。更多关于参考
文件的信息，参见 [pickprefs](/commands/pickprefs.md) 以及
[readcss](/commands/readcss.md)。

注意：如果当数据在数据缓冲区内而用户修改了参考文件，那么在SAC缓冲区中的
震相拾取将可能被修改。（缓冲区的信息可以通过
[listhdr](/commands/listhdr.md) 和 [chnhdr](/commands/chnhdr.md)
查看）。

例：如果当一些含有某些 `pP` 或 `PKiKP` 震相的SAC文件通过
命令读入时，被允许的震相包括 `pP` 以及 `PKiKP`， 那么这些拾取将出现在
`Tn` 时间标记中。如果 `pickphase` 在稍后再次使用将 `pP` 以及 `PKiKP`
从允许的震相中去除，那么 `pP` 以及 `PKiKP`
到时将不会从CSS文件中读取，已经在内存中的 数据的 `pP` 和 `PKiKP`
拾取将从 `Tn` 时间标记中去除。
