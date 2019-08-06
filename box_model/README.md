# 盒模型
### 1. 边框（border）
 (1) border-width 设置边框的高度
- border-width指定了四个值，则四个值分别设置给上、右、下、左边框。
- 如果指定三个值，则三个值分别指定给 上、左右、下。
- 如果指定两个值，则这两个值分别指定给 上下、左右。
- 如果指定一个值，则四边全是该值。
- 除了border-width ,CSS 中还提供了四个属性：border-XXX-width(xxx的值可能是top、left、bottom、right)专门用来设置指定边的宽度。

 (2) border-color 边框颜色
- 设置规则同上

 (3) border-style 边框样式
 
可选值：
- solid 实线 
- none  默认值，没有边框
- dotted 点状边框
- dashed  虚线
- double  双实线
- border-xxx-style规则同上
<br/>**width和height只是设置的盒子内容区的大小，而不是盒子的整个的大小，盒子可见框的大小由内容区、内边距和边框共同决定**