## plot {#cmd:plot}

### 概要

绘制单波形单窗口图形

### 语法

P`LOT`

### 说明

每个数据文件绘制在单独窗口中，图形的大小由
[xvport](/commands/xvport.md) 和 [yvport](/commands/yvport.md)
决定。每个图形的Y轴范围由数据的极值决定，也可以用
[ylim](/commands/ylim.md) 手动限制Y轴的范围。X轴的范围由
[xlim](/commands/xlim.md) 命令控制。用户可以用
[fileid](/commands/fileid.md) 控制每张图的文件ID，也可以用
[picks](/commands/picks.md) 控制时间标记的显示。

SAC会在每张图之间暂停给你机会检查每张图，其将会在终端输出 `Waiting`
并等待你的响应。你可以输入回车以查看下一张图，关键字 `go` 或 `g`
可以不暂停地绘制余下的所有文件，或者关键字 `kill` 或 `k`
可以中止绘制余下的文件。
