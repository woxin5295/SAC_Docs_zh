## 如何学习SAC？

学习SAC最好的方式是找一个有经验且有耐心的人，让他/她给你演示SAC是如何
工作的。如果没有这样一个人的话，那么你就需要打开终端从头开始自学。

学习SAC的过程大致可以分成三个阶段，下面列出了每个阶段的具体要求。
普通用户需要达到SAC进阶才能满足日常数据处理的要求。

### SAC初阶

1.  掌握SAC中最常用的命令，包括但不限于 [help](/commands/help.md)、
    [read](/commands/read.md)、 [write](/commands/write.md)、
    [plot](/commands/plot.md)、 [quit](/commands/quit.md)、
    [plotpk](/commands/plotpk.md)、
    [listhdr](/commands/listhdr.md)、
    [chnhdr](/commands/chnhdr.md)、 [rmean](/commands/rmean.md)、
    [rtrend](/commands/rtrend.md)、 [taper](/commands/taper.md)、
    [bandpass](/commands/bandpass.md)、
    [plot1](/commands/plot1.md)、 [plot2](/commands/plot2.md)、
    [cut](/commands/cut.md)、 [fft](/commands/fft.md)、
    [transfer](/commands/transfer.md)；
2.  理解地震数据处理流程，见 [SAC数据处理](/data-process)一章；
3.  了解 [SAC文件格式](/fileformat)，掌握常见的 [SAC头段变量](/fileformat/header-variables.md)，理解 [SAC中的时间概念](/fileformat/sac-time.md)
4.  SAC 相关工具： [saclst](/tools/saclst.md)

### SAC进阶

1.  掌握SAC的大部分命令，至少要知道哪个命令可以实现什么功能；
2.  掌握如何绘制波形图，见 [SAC绘图](/graphics) 一章；
3.  了解 [SAC编程](/macros) 以及 [如何在脚本中调用SAC](/call-in-script)
4.  学会在自己的程序中读写SAC文件，见 [SAC函数库](/libs) 和 [SAC I/O](/sacio)

### SAC高阶

1.  了解SAC软件包的内部结构；
2.  自己写程序实现SAC I/O库；
3.  阅读SAC源码，了解命令的技术细节；
4.  向SAC贡献代码；
