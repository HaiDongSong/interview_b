![](/assets/import1.png)![](/assets/import2.png)

##### BFC基本概念：

* 块级格式化上下文

##### BFCjd的原理：

1. 在BFC这个元素的垂直方向边距发生重叠
2. BFC的区域不会与浮动元素的box重叠（用来清除浮动）
3. BFC中的元素是一个独立的区域
4. 计算BFC高度的时候，浮动元素也会参与计算

##### 如何创建BFC：

1. float部位null
2. position部位static、relative ， 比如：absolute、fixed
3. display是为inline-block、table-cell、table-caption、table
4. overflow部位visible （overflow:hidden, overflow:auto都可以触发）



