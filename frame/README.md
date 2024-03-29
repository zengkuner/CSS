### 框架集
框架集和内联框架的作用类似，都是用于在一个页面中引入其他的外部页面，框架集可以同时引入多个页面，而内联框架只能引入一个，在H5标准中，推荐使用框架集，而不使用内联框架。

使用frameset来创建一个框架集，注意frameset不能和body出现在同一个页面中，所以要使用框架集页面中就不能使用body标签。
1. 在frameset中使用frame子标签来指定要引入的页面，引入几个页面就写几个frame。
- frameset标签属性：
      rows  指定框架集中的所有框架，一行一行的排列
      cols  指定框架集中的所有页面，一列一列的排列
>这两个属性frameset必须选择一个，并且需要在属性中指定每一部分所占的大小。
- frameset中也可以再嵌套frameset。
>frameset和iframe一样，它里面的内容都不会被搜索引擎所检索，所以如果搜索引擎检索到的页面是一个框架页的话，它是不能区判断里面的内容的。
- 使用框架集则意味着页面中不能有自己的内容，只能引入其他的页面，而每单独加载一个页面，浏览器都需要重新发送一次请求，引入几个页面就需要发送几次请求，用户体验较差。

嵌套框架页面如下：
```html
<frameset cols="30%, * , 30%">
    <frame src=""/>
    <frame src=""/>
    <frameset rows="30%, 50%, *">
        <frame src=""/>
        <frame src=""/>
    </frameset>
</frameset>
```
