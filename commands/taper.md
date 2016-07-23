## taper {#cmd:taper}

### 概要

对数据两端应用对称的taper函数，使得数据两端平滑地衰减到零

### 语法

TAPER \[T`YPE` HAN`NING`|HAM`MING`|C`OSINE`\] \[W`IDTH` v\]

### 输入

TYPE HANNING|HAMMIN|COSINE

:   应用Hanning、Hamming、余弦衰减窗

WIDTH v

:   设置衰减窗的宽度占数据点数的比值为v，v取值在0.0和0.5之间

### 缺省值

taper type hanning width 0.05

### 说明

taper函数是在0和1之间取值的单调函数，若将其对称地施加于数据的首尾两端，
则可实现数据的“尖灭”。

taper函数共计$npts*v$个点，第一个点值为0，最后一个点的值为1，将此函数的
每个点依次于数据的第1至$npts*v$个点相乘，使得数据数据的首端从0开始光滑地
增加到其原始值。数据的末端完全类似，此时数据由其原始值不断光滑地减小到0。

taper命令的通用形式为 $$Data(j) = Data(j)*(F_0 - F_1\cos(\omega(j-1)))$$
此公式应用于数据的首端，另一个完全对称的数据用于数据的尾端。

表 nameref-table-taper-functions 定义了不同的衰减函数的参数，其中N为
衰减窗的宽度，即$npts*v$。

  类型      $\omega$           $F_0$   $F_1$
  --------- ------------------ ------- -------
  HANNING   $\frac{\pi}{N}$    0.50    0.50
  HAMMING   $\frac{\pi}{N}$    0.54    0.46
  COSINE    $\frac{\pi}{2N}$   1.00    1.00

  : taper衰减函数参数一览

图 nameref-fig-taper-functions 给出了不同taper衰减函数的曲线图，图中可以
看出，hamming窗实际上并没有完全实现尖灭。

![taper衰减函数曲线](taper-functions){width="80.00000%"}

### 头段变量

depmin、depmax、depmen
