## globalstack {#sss:globalstack}

### 概要

设置全局迭加属性

### 语法

G`LOBAL`S`TACK` \[W`EIGHT` v\] \[DI`STANCE` v\] \[DE`LAY` v
\[S`ECONDS`|P`OINTS`\]\] \[I`NCREMENT` v \[S`ECONDS`|P`OINTS`\]
\[N`ORMAL`|R`EVERSED`\]

### 输入

WEIGHT v

:   全局权重因子，取值为0至1；

DISTANCE v

:   全局震中距，单位为 ；

DELAY v SECONDS|POINTS

:   全局静时间延迟，单位为 或数据点数；

INCREMENT v SECONDS|POINTS

:   全局静时间延迟的增量，单位为 或数据点数；

NORMAL|REVERSED

:   正/负极性；

### 说明

该命令用于定义全局迭加属性，这些全局迭加属性用于迭加文件列表中的每个文件。可以使用
nameref-sss-addstack命令为某个文件单独设定迭加属性。
