## mtw

### 概要

设置某些测量命令中的测量时间窗（measurement time window）

### 语法

``` {.bash}
MTW [ON|OFF|pdw]
```

### 输入

- `ON`: 打开测量时间窗选项但不改变窗的值
- `OFF`: 关闭测量时间窗选项，测量命令将对整个文件进行操作
- `pdw`: 打开测量时间窗并设置其新值，参考 [pdw](/data-process/cut-data.md) 一节

### 缺省值

``` {.bash}
mtw off
```

### 说明

SAC中与测量有关的命令有 [markptp](/commands/markptp.md) 和
[markvalue](/commands/markvalue.md)。
当不设置mtw时，测量命令会对整个文件进行操作；当设置了mtw时，测量命令仅mtw
时间窗内的数据执行测量命令。
