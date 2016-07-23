## ticks {#cmd:ticks}

### 概要

控制绘图上刻度轴的位置

### 语法

TICKS \[ON|OFF|ONLY\] \[A`LL`\] \[T`OP`\] \[B`OTTOM`\] \[R`IGHT`\]
\[L`EFT`\]

### 输入

ON

:   在指定的边上显示刻度，其他不变

OFF

:   在指定的边上不显示刻度，其他不变

ONLY

:   仅在指定的边上显示刻度，其他关闭

ALL

:   所有四条边

TOP

:   X轴的上边

BOTTOM

:   X轴的下边

RIGHT

:   Y轴的右边

LEFT

:   Y轴的左边

### 缺省值

ticks on all

### 说明

刻度轴可以画图形四边的一边或几边上，刻度间隔由
[xdiv](/commands/xdiv.md) 命令控制。

### 示例

显示上部刻度轴，其他不变：

``` {.bash}
SAC> ticks on top
```

关闭所有刻度轴：

``` {.bash}
SAC> ticks off all
```

只显示底部刻度轴：

``` {.bash}
SAC> ticks only bottom
```
