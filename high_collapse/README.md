### 高度塌陷问题
在文档流中，父元素的高度默认是被子元素撑开的，也就是子元素多高，父元素就多高。但是当给子元素设置浮动以后，子元素会完全脱离文档流，此时将会导致子元素无法撑起父元素的高度，从而导致父元素高度塌陷。

由于父元素的高度塌陷了，则父元素下的所有元素都会向上移动，这样将会导致页面布局混乱。
#### 解决父元素高度塌陷问题(一)
一般想到的是把父元素高度写死，但这样做之后，父元素的高度将不能自动适应子元素的高度，所以这种方案不推荐使用。

W3C标准：页面中的元素都有一个隐含属性叫做Block Fomatting Context ，简称BFC，该属性可以设置打开或者关闭，默认是关闭的。当开启元素的BFC以后，元素将会具有如下特性：
- 父元素的垂直外边距不会和子元素重叠。
- 开启BFC的元素不会被浮动元素所覆盖。
- 开启BFC的元素可以包含浮动的子元素。

BFC开启方式(几种)：
1. 设置元素浮动
>使用这种方式开启，虽然可以撑开父元素，但是会导致父元素的宽度丢失，还会导致下边的元素上移，不能解决问题。
2. 设置元素绝对定位
3. 设置元素为inline-block
>这种方式可以解决问题，但是会导致宽度丢失，不推荐使用。
4. 将元素的overflow设置为一个非visible的值。
- 推荐：将overflow设置为hidden是副作用最小的解决高度塌陷问题的方式。
- IE6及以下的浏览器不支持BFC。
- IE6中虽然没有BFC，但是有另一个隐含属性叫做hasLayout，该属性的作用和BFC类似，所以IE6中可以通过开启该属性解决高度塌陷问题。
- 开启方式很多，设置zoom为1副作用最小。如下：
```css
zoom:1;
/*zoom表示放大的意思，后边跟着一个数值，写几就将元素放大几倍，1没有放大，此样式除IE6以外，其他浏览器都不支持*/
```
#### 解决高度塌陷问题（二）
看下面这个例子。
```html
<style>
    .box3{
        width: 100px;
        height: 100px;
        background-color: yellow;
        float: left;
    }
    .box4{
        width: 200px;
        height: 200px;
        background-color: blue;
    }
    .box5{
        width: 300px;
        height: 300px;
        background-color: blueviolet;
    }
</style>
<body>
    <div class="box3"></div>
    <div class="box4"></div>
    <div class="box5"></div>
</body>
```
由于受到box3向左上浮动的影响，box4整体向上移动了100px，我们希望清除浮动元素对当前元素产生的影响，可以使用clear这个属性。

clear属性可选值：
- none  默认值，不清除浮动。
- left  清除左侧浮动元素对当前元素的影响。
- right  清除右侧浮动元素对当前元素的影响。
- both  清除两侧浮动元素对当前元素的影响（清除对它影响最大的那个元素的浮动）。
所以解决上例的问题可以在box4的样式中添加：
```css
clear:left;
```
清除浮动以后，当前元素会回到浮动元素浮动之前的位置。

在 **问题（一）** 中，可以直接在高度塌陷的父元素的最后，添加一个空白div，由于这个div并没有浮动，所以它是可以撑开父元素高度的，然后在对其清除浮动，该方法基本没有副作用，代码如下：
```html
<style>
    #box1{
        border: 10px red solid;
    }
    #box2{
        width: 100px;
        height: 100px;
        background-color: blue;
        float:left;
    }
    .clear{
        clear: both;
    }
</style>
<body>
    <div id="box1">
        <div id="box2"></div>
        <div class="clear"></div>
    </div>   
</body>
```
>使用这种方式虽然能解决问题，但会在页面中添加多余的结构。

基于上，可以使用after伪类向元素的最后添加一个空白的块元素，然后对其清除浮动，这样做和添加一个div的原理一样，而且不会在页面中添加多余的div，推荐使用。代码如下：
```css
#box1:after{
    content: "";
    display: block;
    clear: both;
}
```
>在IE6中不支持after伪类，所以在IE6中还需要使用hasLayout来处理：
```css
#box{
    zoom: 1;
}
```
