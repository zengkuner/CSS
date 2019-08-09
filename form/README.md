### 表单（form）
表单的作用就是用来将用户输入的信息提交给服务器的。
```html
<form action=""></form>
```
form标签中必须指定一个action属性，该属性指向的是一个服务器的地址，当我们提交表单时将会提交到action属性对应的地址。
#### 表单项
1. 使用input创建一个文本框，它的type属性值是text。
2. 提交按钮可以将表单中的信息提交给服务器，使用input创建一个提交按钮，它的type属性值是submit。
- 如果希望表单项中的数据能提交到服务器中，还必须给表单项指定一个name属性，name表示提交内容的名字。
- 用户填写的信息会附在url地址的后边以查询字符串的形式发送给服务器，格式：url地址?查询字符串。查询字符串：属性名=属性值&属性名=属性值&...&...。
```html
<input type="text" name="username" />
<input type="text" name="hello"/> 
```
上例中，username即为属性名，输入框中输入的内容即为属性值。
- 在提交按钮中可以通过value属性来指定按钮上的文字。
```html
<input type="submit" value="登录"/>
```
- 在文本框中也可以指定value属性值，该值将会作为文本框的默认值显示。
3. 使用input创建一个密码框，它的type属性值是password。
4. 单选按钮
- 使用input创建一个单选按钮，它的type属性使用radio。
```html
<input type="radio"/>
```
- 单选按钮通过name属性进行分组，name属性相同的是一组按钮。
```html
<input type="radio" name="gender"/>男
<input type="radio" name="gender"/>女
```
- 像这种需要用户选择但是不需要用户直接填写内容的表单项，还必须指定一个value属性值，这样被选中的表单项的value属性值将会最终提交给服务器。
5. 多选框
- 使用input创建一个多选框，它的type属性值使用checkbox。
6. 下拉列表
- 使用一个select属性来创建一个下拉列表。
- 在下拉列表中使用option来创建一个一个列表项。
- 下拉列表中name属性需要指定给select，而value属性需要指定给option。
- 可以通过在option中添加selected="selected"来将选项设置为默认选中。
- 如果希望在单选按钮或多选框中指定默认选中的选项，则可以在希望选中的的项中添加checked="checked"属性。
- 当为select添加一个multiple="multiple",则下拉列表变为一个多选的下拉列表。
- 在select中可以使用optgroup对选项进行分组，同一个optgroup中的选项是一组。
- 可以通过label属性来指定分组的名字。
6. 使用textarea标签创建一个文本域。
7. &lt;input type="reset" /&gt;可以创建一个重置按钮，点击重置按钮以后表单中的内容将会恢复默认值。
8. 使用input type="button"可以用来创建一个单纯的按钮，这个按钮没有任何功能，只能被点击。
- 除了使用input，也可以使用button标签来创建按钮，与input效果相同。代码如下：
```html
<button type="submit">提交</button>
<button type="reset">重置</button>
<button type="button">按钮</button>
```
9. html中还提供了label标签，专门用来选中表单中的提示文字，该标签可以指定一个for属性，该属性的值需指定一个表单项的id值，如下：
```html
<label for="um">用户名</label>
<input id="um" type="text" name="username"/>
<br/><br/>
<label for="">性别</label>
<input type="radio" name="gender" value="male" id="male"/>
<label for="male">男</label>
<input type="radio" name="gender" value="female" id="female"/>
<label for="female">女</label>
```
10. 在表单中可以使用fieldset来为表单项进行分组，可以将表单中的同一组放到一个fieldset中。
- 在fieldset可以使用legend子标签来指定组名。