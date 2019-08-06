### 否定伪类

1. 作用：可以从已选定的元素中删除出某些元素

2. 语法  :not(选择器)
- 为所有p元素设置一个背景颜色为黄色，除了class值为hello的

```css
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>否定伪类</title>
    </head>
<style>
    p:not(.hello){
        background-color: yellow;
    }
</style>
<body>
    <p>I am a p element</p>
    <p>I am a p element</p>
    <p>I am a p element</p>
    <p>I am a p element</p>
    <p>I am a p element</p>
    <p>I am a p element</p>
    <p class="hello">I am a p element</p>
</body>
</html>
```