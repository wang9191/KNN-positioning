**重新整理了定位相关代码，位置指纹法可参考：[http://www.cnblogs.com/rubbninja/p/6134481.html](http://www.cnblogs.com/rubbninja/p/6134481.html)**

**对应的Github地址：[https://github.com/jiangqideng/codeInBlogs](https://github.com/jiangqideng/codeInBlogs)**

## 一个精简的knn定位算法（包含数据集，可直接运行）

### 文件说明
|文件|说明 |
|---|---|
|data.mat|数据集|
knn_positioning_simulation.m|算法代码|

### 使用说明
在matlab里，将这两个文件放入同一个文件夹中，运行nn_positioning_simulation。

运行结果如图：![](https://raw.githubusercontent.com/jiangqideng/resources/master/knn_positioning_simulation.jpg)
蓝色的线b-o是真实路径，红星r*是定位算出的位置。

命令行显示KNN平均误差。

### Q&A

+ 请问楼主建立RM的20\*15的空间是怎么分布的，是空旷的空间？还是哪儿有墙体

	有墙，20\*15\*3m的空旷房间，数据是用射线跟踪仿真出来的，考虑直射路径和六条一次反射路径。

+ 指纹数据库中坐标是不是就是行数和列数？

	可以近似这么认为。实际是20m\*15m的区域，坐标就是坐标，把20\*15的区域划分成网格，那些网格点（不包含边界）就是19\*14个，这个就对应于指纹库中的行数和列数。

+ 在求knn\_x,knn\_y为啥公式不一样，都用MOD不可以吗？

	我把欧式距离reshape成了一维的，然后再排的序，这个一维数组再与之前的二维的index对应的话，就分别是求商和取余了。

+ 请问您所取的指纹数据库中坐标间隔是多少（X,Y两个坐标）？

	1m，1m\*1m的网格。
