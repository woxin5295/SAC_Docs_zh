## timewindow

### 概要

设置迭加的时间窗范围

### 语法

``` {.bash}
TIMEWINDOW v1 v2
```
``` {.bash}
TW v1 v2
```

### 输入

- `v1 v2`: 读入数据时所使用的时间窗范围

### 缺省值

无缺省值，在迭加之前必须指定时间窗范围。

### 说明

该命令用于设置迭加时间窗，该设置会影响
[sumstack](/sss/sumstack.md)、[plotstack](/sss/plotstack.md)、[plotrecordsection](/sss/plotrecordsection.md)
等命令的执行效果，迭加时间窗必须在使用这些命令之前定义。

如果某个文件的数据落在迭加时间窗外，则对迭加时间窗内的数据补零值。
