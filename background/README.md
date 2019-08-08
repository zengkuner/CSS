### 背景
1. 使用background-color设置背景样式：
```css
background-color: #bfa;
```
2. 使用background-image来设置背景图片。
- 语法：background-image: url(图片的相对路径);
- 如果背景图片大于元素，默认会显示图片的左上角。
- 如果背景图片和元素一样大，则会将背景图片完全显示。
- 如果背景图片小于元素的大小，则会默认将背景图片平铺以充满元素。
>可以同时为一个元素指定背景图片和背景颜色，这样背景样式将会作为背景图片的底色，一般情况下设置背景图片时都会指定一个背景颜色。
3. background-repeat用于设置背景图片的重复方式。
可选值：
- repeat 默认值，背景图片会双方向重复（平铺）。
- no-repeat 背景图片不会重复，有多大就显示多大。
- repeat-x 背景图片沿水平方向重复。
- repeat-y 背景图片沿垂直方向重复。
4. 背景图片默认是贴着元素的左上角显示，通过background-position可以调整背景图片在元素中的位置。

可选值：该属性可以使用top、right、left、bottom center中的两个值来指定一个背景图片的位置。
```css
background-position: top left; /*左上*/
background-posotion: bottom right /*右下*/
```
>如果只出现一个值，则第二个值默认是center。

也可以直接指定两个偏移量：
- 第一个值是水平偏移量，如果是正值，则图片会向右移动指定的像素；如果指定的是一个负值，则图片会向左移动指定的像素。
- 第二个值是是垂直偏移量，设置规则与上类似。
```css
background-position: 100px 0px;
```
5. background-attachment用来设置背景图片是否随页面一起滚动。

可选值：
- scroll  默认值，背景图片随着窗口滚动。
- fixed  背景图片会固定在某一位置，不随页面滚动。
>当背景图片的background-attachment设置为fixed时，背景图片的定位永远相对于浏览器窗口。不随窗口滚动的图片一般设置给body，而不设置给其他元素。

