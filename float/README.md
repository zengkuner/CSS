### 浮动
块元素在文档流中默认自上向下垂直排列，如果希望块元素在页面中水平排列，可以使块元素脱离文档流，使用float来使元素浮动，从而脱离文档流。

float可选值：
- none 默认值，元素默认在文档流中排列。
- left 元素会立即脱离文档流，向页面的左侧浮动。
- right 元素会立即脱离文档流，向页面的右侧浮动。

当一个元素设置浮动以后（float属性是一个非none值），元素会立即脱离文档流，元素脱离文档流以后，它下边的元素会向上移动，元素浮动以后，会尽量向页面的左上或右上漂浮直到遇到父元素的边框。

如果浮动元素上边是一个没有浮动的块元素，则浮动元素不会超过块元素。例如：
```css
<style>
    /*.box{
        display: inline-block;
    }*/
    #box1{
        float:none;
        width: 100px;
        height: 100px;
        background-color: red;
    }
    #box2{
        float: right;
        width: 100px;
        height: 100px;
        background-color: yellow;
    }
    #box3{
        width: 100px;
        height: 100px;
        background-color: blue;
    }
</style>
<body>
    <div class="box" id="box1"></div>
    <div class="box" id="box2"></div>
    <div class="box" id="box3"></div>
</body>
```
>浮动元素不会超过它上边的已经设置了浮动的兄弟元素，最多最多一边齐。

浮动的元素不会盖住文字，文字会自动环绕在浮动元素的周围，所以可以通过浮动来设置文字环绕图片的效果。

在文档流中，子元素的默认宽度会占父元素的全部，当元素设置浮动以后，会完全脱离文档流,块元素脱离文档流以后，其宽度和高度只能被内容撑开。

>内联元素脱离文档流以后，会变成块元素。