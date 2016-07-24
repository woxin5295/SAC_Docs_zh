## grid

### 概要

控制绘图时的网格线

### 语法

``` {.bash}
GRID [ON|OFF|SOLID|DOTTED]
```
``` {.bash}
GRID [ON|OFF|S|D]
```

### 输入

- `SOLID`: 设置网格线为实线
- `DOTTED`: 设置网格线为虚线
- `ON`: 绘制网格，但不改变网格类型
- `OFF`: 不绘制网格

### 缺省值

``` {.bash}
grid off
```

### 说明

该命令控制X和Y轴的网格线的绘制。可以使用 [xgrid](/commands/xgrid.md) 和
[ygrid](/commands/ygrid.md) 分别控制单个坐标轴的网格类型。
