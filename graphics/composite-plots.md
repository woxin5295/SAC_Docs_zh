## 组合图

前面介绍的绘图命令五花八门，但无论是 `plot`、`plot1` 或是
`plot2`，同一个窗口内绘制的所有波形总是共用同一个X轴。实际绘图时，
经常需要在一张图中绘制多个不同X轴的图，即组合图。

SAC提供了绘制组合图的功能，这其中牵涉到一些新的概念，其中之一是
`frame`。一般而言，在执行绘图命令时会首先对整个窗口进行擦除。
比如，先执行 `plot` 命令，窗口中会显示出相应的波形，然后执行 `plot1`
命令，首先会将窗口中的已有图像全部擦除，再绘制相应波形。

在frame中，每次执行绘图命令时，不会擦除窗口中的已有图像，从而实现了将
多个命令的绘图效果同时显示在一个窗口中。使用
[beginframe](/commands/beginframe.md)
打开frame时，首先会擦除整个窗口，进入“组合图模式”；当组合图绘制完成时，
需要使用 [endframe](/commands/endframe.md) 命令关闭frame。

除了frame之外，在绘制组合图时还需要了解与窗口有关的几个概念，如下图：

-   viewspace：window内可以用于绘图的部分；
-   viewport：执行单个绘图命令时，图像的显示区域；

![window、viewspace和viewport](/figures/viewspace-viewport.png)

上图中给出了window、viewspace、
viewport的相互关系。可以使用 [window](/commands/window.md)
命令设定窗口相对于
整个屏幕的位置以及X、Y方向的范围；[vspace](/commands/vspace.md)
用于设定整个 绘图区的比例；[xvport](/commands/xvport.md) 和
[yvport](/commands/yvport.md) 则分别定义
了单个绘图命令所能使用的X、Y方向的范围。

一个典型的组合图的绘制如下所示：

``` {.bash}
SAC> fg seis                        // 生成数据
SAC> beginframe                     // 打开frame，开始绘制组合图
SAC> xvport 0.1 0.9                 // 设定第一个绘图命令的viewport
SAC> yvport 0.7 0.9
SAC> title 'Seismic Trace'          // 设定标题
SAC> fileid off                     // 不显示文件id
SAC> qdp off
SAC> p
SAC> fft wmean                      // FFT
SAC> xvport .1 .45                  // 设定第二个绘图命令的viewport
SAC> yvport .15 .55
SAC> title 'Amplitude Response (linlog)'
SAC> ylim 1e-5 1                    // Y轴范围
SAC> psp am linlog                  // 绘制振幅谱
SAC> xvport .55 .9                  // 设定第三个绘图命令的viewport
SAC> title 'Amplitude Response (loglog)'
SAC> xlim 1 60
SAC> psp am loglog                  // 绘制振幅谱
SAC> endframe                       // 关闭frame
```

![绘制组合图](/figures/composite-plot.png)
