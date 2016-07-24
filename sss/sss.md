## 信号迭加子程序

Signal Stack Subprocess，是SAC提供的一个用于信号迭加的子程序。

在SAC中键入“`sss`”即可进入该子程序；在子程序中键入 [quitsub](/commands/quitsub.md)
即可 退出子程序并回到主程序；也可键入 [quit](/commands/quit.md)
直接从子程序中退出SAC。

在对多个信号进行迭加时，每个信号都有各自的属性，比如静延迟、震中距、权重因子、
数据极性，也可以根据normal moveout或折射波速度模型计算动延迟。

该子程序具有如下特点：

-   延迟属性可以在迭加过程中自动递增；
-   文件可以很容易地从迭加文件列表中增添；
-   迭加时间窗也可以很容易调整；
-   若文件在迭加时间窗内不含数据，则将其置零值；
-   迭加文件列表可以单独绘制，也可以绘制迭加后的结果；
-   每次迭加结果都可以保存到磁盘上；
-   支持绘制记录剖面图；

在SSS子程序中，你可以执行一系列SSS专属的命令，以及部分SAC主程序中的命令。下面仅列出SSS专属的命令：

- [addstack](/sss/addstack.md) 向迭加文件列表中加入新文件
- [changestack](/sss/changestack.md) 修改当前迭加文件列表中的文件属性
- [deletestack](/sss/deletestack.md) 从迭加文件列表中删除一个或多个文件
- [deltacheck](/sss/deltacheck.md) 修改采样率检测选项
- [distanceaxis](/sss/distanceaxis.md) 定义剖面图中距离轴的参数
- [distancewindow](/sss/distancewindow.md) 控制接下来的剖面图的距离窗属性
- [globalstack](/sss/globalstack.md) 设置全局迭加属性
- [incrementstack](/sss/incrementstack.md) 迭加文件列表中文件的增量属性
- [liststack](/sss/liststack.md) 列出当前迭加文件列表中文件的属性
- [plotrecordsection](/sss/plotrecordsection.md) 用迭加文件列表中的文件绘制剖面图
- [plotstack](/sss/plotstack.md) 绘制迭加文件列表中的文件
- [sumstack](/sss/sumstack.md) 对迭加文件列表中的文件进行迭加
- [timeaxis](/sss/timeaxis.md) 控制接下来剖面图的时间轴属性
- [timewindow](/sss/timewindow.md) 设置迭加的时间窗
- [traveltime](/sss/traveltime.md) 根据预定义的模型计算走时
- [velocitymodel](/sss/velocitymodel.md) 用于计算动延迟的迭加速度模型参数
- [velocityroset](/sss/velocityroset.md) 控制剖面图中速度roset的放置
- [writestack](/sss/writestack.md) 将迭加结果写入磁盘
- [zerostack](/sss/zerostack.md) 重新初始化信号迭加
