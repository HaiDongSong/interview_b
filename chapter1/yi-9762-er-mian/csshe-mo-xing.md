![](/assets/import5.png)

##### 1. 标准模型和IE模型区别：

* IE模型宽高包含border

##### 2.  CSS如何设置这两种模型：

![](/assets/import6.png)

##### 3. JS如何设置获取盒模型对应的宽高

![](/assets/Import4.png)

##### 4. 实例题（根据盒模型解释编剧重叠）

![](/assets/import7.png)

##### 

##### BFC基本概念：

* 块级格式化上下文

##### BFC基本的原理：

1. 在BFC这个元素的垂直方向上边距发生重叠
2. BFC的区域不会与浮动元素的box重叠（用来清除浮动）
3. BFC中的元素是一个独立的区域
4. 计算BFC高度的时候，浮动元素也会参与计算

##### 如何创建BFC：

1. float不位null
2. position不位static、relative ， 比如：absolute、fixed
3. display为inline-block、table-cell、table-caption、table、flex、inline-flex
4. overflow不位visible （overflow:hidden, overflow:auto都可以触发）

##### BFC的使用场景：

##### 



