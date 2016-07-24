## distanceaxis

### 概要

定义剖面图的距离轴参数

### 语法

``` {.bash}
DISTANCEAXIS FIXED v | SCALED v
```
``` {.bash}
DA F v | S v
```

### 输入

- `FIXED v`: 固定距离轴的长度为v厘米
- `SCALED v`: 设定距离轴的长度为总距离范围除以v

### 缺省值

``` {.bash}
distanceaxis fixed 35
```

### 示例

若剖面图的距离范围为150到300 km，则如下命令设置 距离轴长度为75 cm：

``` {.bash}
SAC> distanceaxis scaled 2.0
```
