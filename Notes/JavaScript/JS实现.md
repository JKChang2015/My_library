# JavaScript 使用

### 标签
* HTML 中的脚本必须位于 <script> 与 </script> 标签之间。
* 脚本可被放置在 HTML 页面的 <body> 和 <head> 部分中。

-------


### `<script>` 标签
如需在 HTML 页面中插入 JavaScript，请使用 `<script>` 标签。
`<script>` 和 `</script>`会告诉 JavaScript 在何处开始和结束。
`<script>` 和 `</script>` 之间的代码行包含了 JavaScript：

```javascript
<script>
alert("My First JavaScript");
</script>
```
-------

### `<body>` 中的 JavaScript
在本例中，JavaScript 会在页面加载时向 HTML 的 `<body>` 写文本：
```html
<!DOCTYPE html>
<html>
<body>
.
.
    <script>
    document.write("<h1>This is a heading</h1>");
    document.write("<p>This is a paragraph</p>");
    </script>
.
.
</body>
</html>
```
-------


### JavaScript 函数和事件
上面例子中的 JavaScript 语句，会在页面加载时执行。
通常，我们需要在某个事件发生时执行代码，比如当用户点击按钮时。
如果我们把 JavaScript 代码放入函数中，就可以在事件发生时调用该函数。

-------
### `<head>` 或 `<body>` 中的 JavaScript
* 可以在 HTML 文档中放入不限数量的脚本。
* 脚本可位于 HTML 的 <body> 或 <head> 部分中，或者同时存在于两个部分中。
* 通常的做法是把函数放入 <head> 部分中，或者放在页面底部。这样就可以把它们安置到同一处位置，不会干扰页面的内容。

#### <font color='red'> `<head> `中的函数 </font>

```html
<!DOCTYPE html>
<html>

<head>
    <script>
        function myFunction() {
            document.getElementById("demo").innerHTML = "My First JavaScript Function";
        }
    </script>
</head>

<body>
    <p id="demo">A Paragraph</p>

    <button type="button" onclick="myFunction()">Try it</button>
</body>

</html>
```
按键过后，执行`<script>` 中的myFunction 将文字内容从 A Paragraph 改变成My First JavaScript Function。

#### <font color='red'> `<body> `中的函数 </font> 

```html
<!DOCTYPE html>
<html>
<body>

    <h1>My Web Page</h1>
    <p id="demo">A Paragraph</p>

    <button type="button" onclick="myFunction()">Try it</button>

    <script>
        function myFunction() {
            document.getElementById("demo").innerHTML = "My First JavaScript Function";
        }
    </script>

</body>
</html>
```

#### <font color='red'> 外部的 JavaScript </font> 

也可以把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。
外部 JavaScript 文件的文件扩展名是 .js。如需使用外部文件，请在 `<script>` 标签的 "src" 属性中设置该 .js 文件：

```html
<!DOCTYPE html>
<html>
<body>
    <script src="myScript.js"></script>
</body>
</html>
```

提示：外部脚本不能包含 `<script>` 标签。
