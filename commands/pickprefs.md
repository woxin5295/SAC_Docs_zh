## pickprefs

### 概要

用于控制SAC管理震相和/或从不同的输入数据格式（例如CSS、GSE、SUDS...）
读入到时间标记变量 `T0` 到 `T9`，若这个选项为OFF（缺省状态），
则载入到时间标记的震相为SAC在输入文件中发现的第一个拾取，如果这个选项为ON，
SAC将使用 [readcss](/commands/readcss.md) 命令中描述的参考文件

### 语法

``` {.bash}
PICKPREFS ON|OFF
```
``` {.bash}
PICKPR ON|OFF
```

### 输入

- `ON`: 指示SAC通过参考文件将到时信息由CSS缓冲区传送到SAC缓冲区。
    这对于需要特定到时位于特定头段变量的宏文件来说很有用
- `OFF`: 指示SAC绕过参考文件，载入给定文件的前10个震相拾取。这个是
    默认值，它允许用户注意一些在 `PICKPREFS ON` 时无法注意的拾取。

### 缺省值

``` {.bash}
pickprefs off
```

### 说明

从版本0.58开始，sac2000就有两个不同的头段缓冲区：一个根据SAC文件格式构建，
一个根据有关的CSS3.0文件格式。添加了CSS数据缓冲区使得读取如CSS、GSE、SUDS
等这里相关格式变得更加容易。两个缓冲区同时也使得下面的几个命令得以使用：
COMMIT、ROLLBACK、RECALLTRACE。有两个缓冲区的一个缺点是将到时从动态的CSS
到时表转移到SAC格式中相对静态的 `Tn` 拾取变得更加复杂了，这个问题
在0.58版本中通过设置了一个称为csspickprefs的参考文件得以解决。这个文件在
`$SACAUX` 目录下，你可以覆盖它写入你想要的信息。更多关于csspickprefs
的信息，参见 [readcss](/commands/readcss.md)
命令。关于如何覆盖默认参考文件，参看
[pickauthor](/commands/pickauthor.md) 或
[pickphase](/commands/pickphase.md)。

使用参考文件的缺点是它将只接收列在参考文件中或在命令
[pickphase](/commands/pickphase.md)、
[pickauthor](/commands/pickauthor.md)
中输入的震相或作者列表。换句话说，如果一个CSS 数据文件有一个 `pP`
的到时，不管其来自于平面文件还是Oracle数据库， 而 `pP`
未在参考文件中指定，那么用户就绝不会知道 `pP` 在那里。 `pP`
震相将读入SAC中的CSS数据缓冲区，但是它不会转变到SAC数据缓冲区中，
也不会参与任何SAC命令。它可以通过 [writecss](/commands/writecss.md)
命令写出，或者可能 通过COMMIT命令刷新然后全部丢失。

SAC给出的解决办法是允许用户绕过参考文件。在0.59版本中，默认是从CSS缓冲区
中直接读入前10个可用的拾取到SAC缓冲区中，通过这个新命令的使用，用户可以
告诉SAC使用指定的参考文件。
