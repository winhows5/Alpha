# Here we go！

## Change log
---
### v0.2 2017／08／17 bolgs
1. 添加了以往项目的blog链接

### V0.15 2017／08／16 Triangles -improved
1. 减少了背景浮动几何形状的扁平化概率，以及走势趋下的概率
- Key Points:

    调整三角形的最小面积，并调整角的最小弧度。
    注意：如果仅调整角的最小弧度，会有很大概率迭代至超过cpu计算能力。其原因很容易理解：当角所对的边长较短时，为了保证角大于一定的角度，则另外两边的长度有很大概率小于对角边；而且这一趋势是正反馈的，很容易耗尽计算能力。<br>
    ![angle_mistake1](/source/angle_mistake1.png)
    ![angle_mistake2](/source/angle_mistake2.png)
    <br>
    而如果仅调整三角形的最小面积，则容易出现“狭长”三角形的极端结果。
    综上，我在原生成规则上修正了边界调节，以避免图形过于细长。


### V0.1 2017／08／15 Triangles
1. 根据[Even You](http://evanyou.me)的页面js学习生成背景浮动几何的数学方法
- Key Points:
    绘制随机三角形：
    1. 设置起始点为`q0`和`q1`，横坐标为0，纵坐标为`0.7 * height ± 90`
    2. 三角形第三个点为`q2`，其中`q2.x`的值为`q1.x + random1`，`q1.y + random2`
    3. 检测是否到达边界，如果为否，则`q0 = q1， q1 = q2`，重复循环；如果到达边界则结束。
    随机颜色填充：
    使用三个不同相的`cos`函数生成rgb的数值，示例如下图：
    ![color](/sources/colorful.png)
