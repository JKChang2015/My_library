# Json

### 1. Introduction
JSON（ JavaScript Object Notation ），即 JavaScript 对象表示法。JSON 主要用于存储和交换文本信息，类似于XML。但是和 XML 相比，JSON 是更加轻量级的文本数据交换格式，具有更小、更快、更易解析的特点。

---
### 2. Basic syntax
Json利用Javascript语法进行描述：
* 数据在key/value对中进行存储
* 数据由逗号进行分割
* 花括号保存对象
* 方括号保存数据

---
### 3. Json data type
JSON的数据都在key/value对中存储，value type:
* 数字(整数或浮点数):`{ "number":12.34 }`
* 字符串(在双引号中):`{ "name":"qiumengchen" }`
* 逻辑值(true 或 false):`{ "isOpen":true }`
* 数组(在中括号中):`{ "array":[1.2 , "3" , true , [4,5] , {"test":"ok"} , null] }`
* 对象(在大括号中):`{ "person":{"name":"qiumengchen","isHandsome":true} }`
* null:`{ "blog":null }`

Json 的完整形式有两种：
* **Json对象：**以大括号（**{}**）为标志，对象可以包含多个key/value对，注意：对象中的每一项都必须是key/value对，不能是其他形式。但是，其中的key必须是字符串，其中的value可以是合法的JSON数据类型包括：数字、字符串、逻辑值、数组、对象、null等。

```json
{
   "name":"David",
   "alive":true,
   "blog":{
      "url":"www.google.com",
      "name":"My blog"
   }
}
```

*  **Json数组**：以中括号（**[]**）为标志，数组可以包含多个value，value可以是合法的JSON数据类型包括：数字、字符串、逻辑值、数组、对象、null等。但是，一般来说，我们会保持数据中每个项的形式和意义的一致性，方便理解和运用。

```json
[
   99,
   "qiumengchen",
   true,
   [1,2,3],
   {
      "name":"qiumengchen"
   },
   null
]
```
### 4. 和XML进行比较
* **与XML相同之处**
    - JSON 是纯文本
    - JSON 具有”自我描述性”（人类可读）
    - JSON 具有层级结构（值中存在值）
    - JSON 可通过 JavaScript 进行解析
    - JSON 数据可使用 AJAX 进行传输
* **与XML不同之处**
    - 没有结束标签
    - 更短
    - 读写的速度更快
    - 能够使用内建的 JavaScript eval() 方法进行解析
    - 使用数组
    - 不使用保留字

