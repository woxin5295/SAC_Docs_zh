# 错误与警告

## 0131 sac/datagen data directory not found

[datagen](/commands/datagen.md) 在生成波形数据时需要从
`${SACAUX}/datagen` 目录下读取SAC文件，出现该错误的原因是该目录不存在。


## 1028 External command does not exist

执行 [load](/commands/load.md) 命令时找不到外部命令。产生该错误的原因很多，
可能是环境变量 `LD_LIBRARY_PATH` 不包含要载入的共享库的所在目录，或 `$SACSOLIST`
中不包含要载入的共享库的名字。


## 1103 No help package is available

没有可用的帮助文档包，可能原因是没找到 `${SACAUX}/help` 目录。


## 1106 Not a valid SAC command.

对于每一行命令，SAC首先会检查是否是SAC内部的命令，如果不是，则检查是否是系统自带
的命令，比如 `ls`、`cp` 等。

一个例外是系统命令 `rm`。在SAC中直接执行rm命令会出现如上所示的错误。出现该
错误的原因是SAC禁用了系统命令 `rm`，主要目的是为了防止将 `r *.SAC`
误敲成 `rm *.SAC` 而导致数据的误删除。可以使用
[systemcommand](/commands/systemcommand.md) 命令显式
调用系统命令，如下：

```
SAC> rm BAD*.SAC
 ERROR 1106: Not a valid SAC command.
SAC> sc rm BAD*.SAC
```


## 1301 No data files read in

内存中未读入数据。可能是未指定要读取的文件列表，或列表中的文件不可读。


## 1303 Overwrite flag is not on for file

该错误主要出现在写SAC文件时，出现该错误的原因是SAC文件的头段变量 `lovrok` 的值 为
`FALSE`，即磁盘中的数据不允许被覆盖。解决该问题的方法有两种：

-   以其他文件名写入磁盘，不覆盖磁盘文件；
-   修改 `lovrok` 的值为 `TRUE`；


## 1304 Illegal operation on data file

对数据文件的非法操作。


## 1305 Illegal operation on time series file

某些命令无法对时间序列数据进行操作。


## 1306 Illegal operation on unevenly spaced file

某些命令无法对不等间隔数据进行操作。


## 1307 Illegal operation on spectral file

命令不能对内存中的谱文件进行操作。


## 1311 No list of filenames to write

没有要写入的文件列表。


## 1312 Bad number of files in write file list

通常在使用 [write](/commands/write.md) 命令时会出现该问题。出现该错误的原因是内存中的
波形文件的数目与write命令给出的文件名的数目不想匹配。在该错误信息的后面，紧接着
会给出write命令中给出的文件数目以及内存中的波形数目。


## 1317 The following file is not a SAC data file

试图读入非SAC格式的文件所产生的错误。


## 1320 Available memory too small to read file

系统内存不足。


## 1322 Undefined starting cut for file

[cut](/commands/cut.md) 命令中时间窗的起始参考头段未定义。默认情况下，会使用磁盘
文件的起始时间代替，也可以使用 [cuterr](/commands/cuterr.md)
命令控制该错误的处理方式。

## 1323 Undefined stop cut for file

[cut](/commands/cut.md) 命令中时间窗的结束参考头段未定义。默认情况下，会使用磁盘
文件的结束时间代替，也可以使用 [cuterr](/commands/cuterr.md)
命令控制该错误的处理方式。


## 1324 Start cut less than file begin for file

[cut](/commands/cut.md) 命令中时间窗的开始时间早于磁盘文件的开始时间。默认情况下，
会使用磁盘文件的开始时间代替，也可以使用 [cuterr](/commands/cuterr.md)
命令控制该错误的 处理方式。

## 1325 Stop cut greater than file end for file

[cut](/commands/cut.md) 命令中时间窗的结束时间晚于磁盘文件的结束时间。默认情况下，
会使用磁盘文件的结束时间代替，也可以使用 [cuterr](/commands/cuterr.md)
命令控制该错误的 处理方式。

## 1326 Start cut greater than file end for file

[cut](/commands/cut.md) 命令中时间窗的开始时间晚于文件结束时间。

## 1340 data points outside allowed range contained in file

文件中数据点的值超过了所允许的范围。比如 [log](/commands/log.md)
中要求数据为正。

## 1379 No SORT parameters given

使用了 [sort](/commands/sort.md) 命令，但未指定按照哪个参数排序。

## 1380 Too many SORT parameters

[sort](/commands/sort.md) 命令中用于排序的参数太多。

## 1381 Not a valid SORT parameter

无效的 [sort](/commands/sort.md) 参数。

## 1383 SORT failed

排序失败。

## 1606 Maximum allowable DFT is 16777216

SAC中与FFT相关的命令，所能允许的最大数据点数是 $$2^{24}=16777216$$。

## 1611 Corner frequency greater than Nyquist for file

对数据进行滤波时，拐角频率超过了文件的Nyquist采样率。

## 1613 Minimum size of data file for Hilbert transform is 201

在做Hilbert变换时，要求数据的最小长度是201个数据点。

## 1701 Can’t divide by zero

除零的非法操作。

## 1702 Non-positive values found in file

数据文件中存在非正值。

## 1801 Header field mismatch

该错误出现在
[addf](/commands/addf.md)、[subf](/commands/subf.md)、[divf](/commands/divf.md)、[mulf](/commands/mulf.md)
以及 [merge](/commands/merge.md) 和 [beam](/commands/beam.md) 中。

出现该错误的原因是多个数据文件中的头段变量不匹配。该命令会明确给出不匹配的头段变量名，以及
出现不匹配的数据文件，以供用户查错。会出现不匹配的头段变量包括npts、delta、kstnm、knetwk、
kcmpnm。

## 1802 Time overlap

要进行操作的两个数据的时间段不完全重合。

## 1803 No binary data files read in.

[addf](/commands/addf.md)、[subf](/commands/subf.md)、[merge](/commands/merge.md)
等命令需要先读入二进制数据，再对数据做操作。

## 1805 Time gap

使用 [merge](/commands/merge.md) 命令时，两段数据间存在时间间断。

## 2001 Command requires an even number of data files

使用 [rotate](/commands/rotate.md)
命令进行数据对的旋转时，需要内存中有成对的
数据文件（即偶数个），若内存中数目不为偶数个，则报错。注意检查是否有
数据漏读。

## 2002 Following files are not an orthogonal pair

出现该错误的原因是使用 [rotate](/commands/rotate.md)
旋转的两个分量不完全正交， 此时应注意检查两个分量的头段变量 `cmpinc` 和
`cmpaz`。
若两个头段变量未定义，则需要根据仪器的其他信息确定两个头段变量的值；
若两个头段变量有定义，但的确不正交，则无法进行分量旋转。

## 2003 Following files are not both horizontals

[rotate](/commands/rotate.md) 命令的 `TO` 选项只能用于将两个水平的分量
旋转到某个角度，出现该错误时应注意检查两个分量的头段变量 `cmpinc`
是否等于 $$90^\circ$$。

## 2004 Insufficient header information for rotation

[rotate](/commands/rotate.md) 命令的 `TO GCP` 选项要求头段变量中
`stla`、`stlo`、`evla` 和 `evlo` 必须定义。
该选项会读取一对分量中的第一个文件中的头段变量，并计算反方位角，而不是
直接使用头段变量中已有的反方位角值。

## 2008 Requested begin time is less than files begin time. Output truncated.

[interpolate](/commands/interpolate.md)
命令中指定的开始时间小于文件起始时间，此时 输出会被截断。

## 2111 Taper frequency limits are invalid. No taper applied.

该警告出现在 [transfer](/commands/transfer.md)
命令中，出现该错误的原因是 `freqlimits`
选项的参数设置有误。四个频率应满足 `f1<f2<f3<f4`。

出现该警告时，[transfer](/commands/transfer.md) 会忽略 `freqlimits`
选项，
即在去仪器响应时，不使用taper函数，进而可能导致去仪器响应后的波形出现问题。

## 2405 Cannot PRINT: no SGF files produced

无法打印，原因是未生成SGF文件。

## 5003 No correlation function calculated

未计算相关函数。

## 5004 No spectral estimate calculated

未计算谱估计。

## 9005 Amplitude mismatch

要合并的两段数据之间存在时间重叠，且在重叠的时间段内振幅不匹配。出现这样的错误可能
是数据的绝对时间有问题。

## Environmental variable SACAUX not defined.

出现该错误的原因是环境变量 `$SACAUX` 未定义，参考 [在Linux下安装SAC](/introduction/linux-install.md)。

## Enviornment variable SACAUX too long: max: 128 SACAUX: xxx

环境变量 `$SACAUX` 超过128字符。
