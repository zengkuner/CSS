### 表格(table)
>table是一个块元素

在HTML中，使用table标签来创建一个表格。在table标签中使用tr来表示表格中的一行，有几行就有几个tr。在tr中需要使用td来创建一个单元格，有几个单元格就有几个td。
1. colspan：横向合并单元格。
2. rowspan: 纵向合并单元格。
#### 表格样式
```css
<style>
    table{
        width: 300px;
        margin: 0 auto;
        border-spacing: 0;
        border-collapse: collapse;
    }
    td{
        border: 1px solid black;
    }
</style>
```
1. table和td边框之间默认有一个距离，通过border-spacing属性可以设置这个距离。
2. border-collapse可以用来设置表格的边框合并，如果设置了边框合并，则border-spacing自动失效
3. 可以使用th标签来表示表头中的内容，它的用法和td一样，不同的是它有一些默认效果。
4. 设置隔行变色。
```css
tr:nth-child(even){
    background-color: #bfa;
}
/*鼠标移入到tr以后变色*/
tr:hover{
    background-color: yellow;
}
```
有一些情况下表格是非常长的，这时就需要将表格拆分为三个部分，表头、表格的主题、表格底部。在HTML中提供了三个标签：
- thead 表头
- tbody 表格主题
- tfoot 表格底部
这三个标签的作用用来区分表格的不同部分，它们都是table的子标签,tr需要写在这些标签里面。
```html
<table>
    <thead>
        <tr>
            <th>日期</th>
            <th>收入</th>
            <th>支出</th>
            <th>合计</th>
        </tr>
    </thead>
    <tfoot>
        <tr>
            <td>...</td>
            <td>...</td>
            <td>...</td>
            <td>...</td>
        </tr>
    </tfoot>
    <tbody>
        <tr>
            <td>...</td>
            <td>...</td>
            <td>...</td>
            <td>...</td>
        </tr>
    </tbody>
   </table>
```
thead中的内容，永远会显示在表格的头部。tfoot中的内容，永远会显示在表格的底部。tbody中的内容，永远都会显示在表格的中间。
-  如果table下没有tbody，浏览器会自动在表格中添加tbody，并且将所有的tr都放到tbody中。
- 注意tr并不是table的子元素，而是tbody的子元素，通过table > tr无法选中行，需要通过tbody > tr 。代码如下：
```css
tbody > tr:nth-child(even){
    background-color: #bfa;
}
```
表格的列数由td最多的那行决定，表格是可以嵌套的，可以在td中再放置一个表格，示例如下：
```html
<table border="1" width="100%">
    <tr height="100px">
        <td colspan="2"></td>
    </tr>
    <tr height="400px">
        <td width="20%"></td>
        <td width="80%">
            <table border="1" width="100%" height="100%">
                <tr>
                    <td></td>
                </tr>
                <tr>
                    <td></td>
                </tr>
            </table>
        </td>
    </tr>
    <tr height="100px">
        <td colspan="2"></td>
    </tr>
</table>
```
既解决高度塌陷，又可以确保父元素和子元素的垂直外边距不会重叠的方法：
```css
.clearfix:before,.clearfix:after{
    content: "";
    display: table;
    clear: both;
}
.clearfix{
    zoom: 1;
}
```