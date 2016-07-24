## fileid 

### 概要

控制绘图时文件ID的显示

### 语法

``` {.bash}
FILEID [ON|OFF] [T!YPE! D!EFAULT!|N!AME!|L!IST! hdrlist] [L!OCATION! UR|UL|LR|LL]
    [F!ORMAT! E!QUALS!|C!OLONS!|N!ONAMES!]
```

### 输入

ON

:   显示文件id，不改变文件id类型或位置

OFF

:   不显示文件id

TYPE DEFAULT

:   设置文件id为默认类型

TYPE NAME

:   使用文件名作为文件id

TYPE LIST hdrlist

:   定义在文件id中显示的头段列表

LOCATION UR|UL|LR|LL

:   文件id的显示位置，分别表示右上角、左上角、 右下角、左下角

FORMAT EQUALS

:   格式为 `variable=value`

FORMAT COLON

:   格式为 `variable:value`

FORMAT NONAMES

:   格式只包含头段值

### 缺省值

``` {.bash}
fileid on type default location ur format nonames
```

### 说明

文件ID用于标识绘图的内容。默认的文件ID包括事件名、台站名、分量、参考
日期及时间。如果需要也可以使用文件名代替默认的文件id，或者根据头段变量
定义一个特殊的文件ID，这个ID最多可以由10个SAC头段变量构成。文件ID的位置
以及格式也可以修改。

### 示例

将文件名放在左上角：

``` {.bash}
SAC> fileid location ul type name
```

定义一个特殊的文件id，包含台站分量、经纬度：

``` {.bash}
SAC> fileid type list kstcmp stla stlo
```

文件id为头段名后加一个冒号：

``` {.bash}
SAC> fileid format colon
```
