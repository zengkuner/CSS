### css样式设置的一些规则
1. 定义外部样式时（css文件：.css格式），要用link标签引用，例如：
```html
<link rel="stylesheet" type="text/css" href="mystyle.css">
```
href指定css文件路径。
>注意：具体数值与单位之间不能有空格。错误示例：margin-left：20 px；正确示例：margin-top：20px；
2. 定义内部样式直接写在&lt;style&gt;&lt;/style&gt;内。
3. 行内样式。例如：
```css
<div style="background-color: red;height: 10px;"></div>
```
4. 当相同元素以不同形式定义了多种样式时，根据从上至下的编译顺序，执行最后编译的样式。
>行内样式拥有最高优先级。