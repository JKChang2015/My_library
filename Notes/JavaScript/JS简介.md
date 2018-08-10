# [JavaScript 教程](http://www.w3school.com.cn/js/)

### JavaScript 是脚本语言
* JavaScript 是一种轻量级的编程语言。
* JavaScript 是可插入 HTML 页面的编程代码。
* JavaScript 插入 HTML 页面后，可由所有的现代浏览器执行。



### Examples

-------

**JavaScript： 写入**
```html
<!DOCTYPE html>
<html>
<body>
    <p>
    JavaScript 能够直接写入 HTML 输出流中：
    </p>

    <script>
    document.write("<h1>This is a heading</h1>");
    document.write("<p>This is a paragraph.</p>");
    </script>
</body>
</html>
```
您只能在 HTML 输出流中使用 <strong>document.write</strong>。
如果您在文档已加载后使用它（比如在函数中），会覆盖整个文档。

-------

**JavaScript：对事件作出反应**
```html
<!DOCTYPE html>
<html>
<body>
    <p>
    JavaScript 能够对事件作出反应。比如对按钮的点击：
    </p>
    
    <button type="button" onclick="alert('Welcome!')">点击这里</button>
</body>
</html>
```
onclick 是js诸多事件之一，按键
alert( ) 弹出窗口内容

-------

**JavaScript：改变 HTML 内容**
```html
<!DOCTYPE html>
<html>

<body>
    <p>
        JavaScript 能够对事件作出反应。比如对按钮的点击：
    </p>

    <button type="button" onclick="alert('Welcome!')">点击这里</button>

</body>
</html>
```
您会经常看到 document.getElementByID("some id")。这个方法是 HTML DOM 中定义的。
DOM（文档对象模型）是用以访问 HTML 元素的正式 W3C 标准。

-------
**JavaScript：改变 HTML 图像**

```html
<html>
<body>
    <script>
        function changeImage() {
            element = document.getElementById('myimage')
            if (element.src.match("bulbon")) {
                element.src = "/i/eg_bulboff.gif";
            } else {
                element.src = "/i/eg_bulbon.gif";
            }
        }
    </script>

    <img id="myimage" onclick="changeImage()" src="/i/eg_bulboff.gif">

    <p>点击灯泡来点亮或熄灭这盏灯</p>

</body>
</html>
```

动态地改变 HTML <image> 的来源 (src)： 点击灯泡就可以打开或关闭这盏灯

-------
**JavaScript：改变 HTML 样式**
改变 HTML 元素的样式，属于改变 HTML 属性的变种。

```html
<!DOCTYPE html>
<html>
<body>

    <p id="demo">
        JavaScript 能改变 HTML 元素的样式。
    </p>

    <script>
        function myFunction() {
            x = document.getElementById("demo") // 找到元素
            x.style.color = "#ff0000"; // 改变样式
        }
    </script>

    <button type="button" onclick="myFunction()">点击这里</button>

</body>
</html>
```