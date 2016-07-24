## changestack

### 概要

修改当前迭加文件列表中的文件属性

### 语法

``` {.bash}
CHANGESTACK filename|filenumber [WEIGHT v] [DISTANCE v] [BEGINTIME v]
    [ENDTIME v] [DELAY v SECONDS|POINTS] [INCREMENT v SECONDS|POINTS]
    [NORMAL|REVERSED]
```
``` {.bash}
CS filename|filenumber [W v] [DI v] [BE v] [END v] [DE v S|P] [I v S|P] [N|R]
```

### 输入

- `filename`: 迭加文件列表中的文件名
- `filenumber`: 迭加文件列表中的文件号
- `WEIGHT v`: 当前文件的权重因子。v的取值范围为0到1，在迭加之前会首先对文件的每个值乘以该权重因子再做迭加。
- `DISTANCE v`: 该文件所对应的震中距，单位为 。用于计算动态时间延迟
- `BEGINTIME v`: 事件开始的时间
- `ENDTIME`: 事件结束时间
- `DELAY v SECONDS|POINTS`: 该文件的静态时间延迟，单位为秒或数据点数
- `INCREMENT v SECONDS|POINTS`: 该文件的静态时间延迟增量，单位为秒或数据点数。在每次执行incrementstack命令时，静态时间延迟会增加一个常数。
- `NORMAL|REVERSED`: 文件拥有正/负极性

### 说明

该命令允许你修改修改迭加文件列表中任意文件的任意属性。详情参考
[addstack](/sss/addstack.md) 命令。
