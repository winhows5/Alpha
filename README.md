# Here we go

## Change log
---

### V0.1 The beginning
1. 根据[Even You](http://evanyou.me)的页面js学习生成背景浮动几何的数学方法
- Key Points:
    绘制随机三角形：
    1. 设置起始点为`q0`和`q1`，横坐标为0，纵坐标为`0.7 * height &plusmn; 90`
    2. 三角形第三个点为`q2`，其中`q2.x`的值为`q1.x + random1`，`q1.y + random2`
    3. 检测是否到达边界，如果为否，则`q0 = q1， q1 = q2`，重复循环；如果到达边界则结束。
    随机颜色填充：
    使用三个不同相的`cos`函数生成rgb的数值，示例如下图：
    ![img](/sources/colorful.png)
