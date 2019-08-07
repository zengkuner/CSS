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
<br/> **Tips：** width和height只是设置的盒子内容区的大小，而不是盒子的整个的大小，盒子可见框的大小由内容区、内边距和边框共同决定。在不大部分的浏览器中，边框的宽度和颜色都是有默认值的，而边框的样式默认值都是none。

(4) border  边框简写样式

- 通过边框的简写样式border可以同时设置四个边框的样式、宽度、颜色，而且没有任何顺序要求。如下：
```css
border：red solid 10px;
```
- border指定样式后会应用于上下左右四个边框，不能分别指定。
- border-xxx(xxx可选值为top、left、right、bottom)可单独设置四个边框的样式，规则与border相同。
### 2. 内边距（padding）
指的是盒子的内容区与盒子边框之间的距离，一共有四个方向的内边距， 可以通过padding-xxx(xxx可选值为top、right、bottom、left)分别设置上右下左的内边距。

内边距会影响盒子的可见框的大小，元素的背景会延申到内边距。如下：
```css
<style>
    #box1{
        width: 100px;
        height: 100px;
        background-color: aqua;
        border-width: 3px;
        /*border-width: 3px 4px 5px 6px;*/
        border-color: red;
        border-style: solid;
        padding-top: 50px;
    }
    #box2{
        width: 100%;
        height:100%;
        background-color: yellow;
    }
</style>
<body>
    <div id="box1">
        <div id="box2"></div>
    </div>   
</body>
```
使用padding可以同时设置四个边框的样式，规则和border-width一致。
### 3. 外边距（margin）
外边距指的是当前盒子与其他盒子之间的距离，它不会影响盒子的大小，而是会影响到盒子的位置。有四个方向的外边距margin-xxx（xxx可选值为top、right、bottom、left分别表示上右下左）。

1. margin可以设置为auto，auto一般只设置给水平方向的margin。
2. 如果只指定左外边距(margin-left)或右外边距(margin-right)为auto，则会将外边距设置为最大值。
3. 如果将left和right同时设置为auto，则会将两侧的外边距设置为相同的值。即可使元素自动在父元素中水平居中。
4. 垂直方向外边距如果设置为auto，则外边距默认为0。
5. 外边距同样可以使用简写属性margin，规则同上。水平居中显示：
```CSS
margin:0 auto;
```
6. 垂直外边距重叠：

在网页中垂直方向的相邻外边距会发生外边距的重叠，即兄弟元素之间的相邻外边距会取最大值而不是取和。

如果父子元素的垂直外边距相邻了，则子元素的外边距会设置给父元素。
### 4. 浏览器默认样式
浏览器为了在页面中没有样式时也可以有一个比较好的显示效果，所以为很多的元素都设置了一些默认的margin和padding，而它的这些默认样式在正常情况下是不需要使用的。清除浏览器默认样式：
```css
*{
    margin:0;
    padding:0;
}
```
### 5. 内联元素的盒模型
 - 内联元素不能设置width和height。
 - 可以设置水平方向的内边距垂直方向的内边距，设置垂直方向的内边距不会影响页面的布局（即不会影响其他元素的摆放位置）。
 - 内联元素可以设置边框，但是垂直的边框不会影响到页面的布局。
 - 内联元素支持水平方向的外边距，该方向相邻外边距不会重叠而是求和。内敛元素不支持垂直外边距。