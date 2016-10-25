## pickauthor

### 概要

告诉SAC从一个用户定义的参考文件中读入作者列表（也可能是震相拾取信息），
或在该命令行上输入作者列表

### 语法

``` {.bash}
PICKAUTHOR author1 [author2 author3 ...]
PICKAUTHOR FILE [filename]
PICKAUTHOR PHASE [filename]
```
``` {.bash}
PICKA author1 [author2 author3 ...]
PICKA FILE [filename]
PICKA PHASE [filename]
```

### 输入

- `authorlist`: SAC使用输入创建作者列表
- `FILE`: 如果使用了 `FILE` 选项，SAC将从参考文件中读取作者列表。
    如果参考文件的文件名在命令行上给出，则SAC将读取这个指定的文件，否则
    SAC将根据上一次执行 [pickauthor](/commands/pickauthor.md)
    读取最近输入的文件名。 如果未给出文件名，则SAC使用
    `$SACAUX/csspickprefs`

- `PHASE`: 与 `FILE` 选项相似，其另一个功能是允许SAC读取指定的 头段变量信息

### 缺省值

``` {.bash}
pickauthor file
```

### 说明

`pickauthor` 提供了一种在命令行上覆盖参考文件的方法。其可以用于
在命令行提供作者的优先列表信息，或者将SAC从一个参考文件重定向到另一个。
更多关于参考文件的信息，参考 [pickprefs](/commands/pickprefs.md) 以及
[readcss](/commands/readcss.md)。

注意：如果当数据在数据缓冲区内而用户修改了参考文件，那么在SAC缓冲区中的
震相拾取将可能被修改。（缓冲区的信息可以通过
[listhdr](/commands/listhdr.md) 和 [chnhdr](/commands/chnhdr.md)
查看）。

例：如果作者列表是“john rachel michael”，并且一些文件被用
[readcss](/commands/readcss.md) 命令读入，一些到时可能以
`author=michael` 读入。（用户可能不会
注意到对于某个给出的震相拾取其作者是谁，因为在CSS中的作者字段在SAC格式中
并不会出现）。如果用户稍后使用了 `pickauthor` 命令并修改作者列表为
“peter doug rachel”，然后 `readcss more` 读入更多文件，没有
`author=michael` 的文件读入，已经在内存中的文件将丢失以michael作为
作者的拾取。不了解这个用户可能会莫名地发现似乎震相拾取会随机消失。更多的
信息参考 `pickprefs`。
