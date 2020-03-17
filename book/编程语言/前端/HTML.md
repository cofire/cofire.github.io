# 介绍

HTML 是用来描述网页的一种语言。

- HTML 指的是超文本标记语言: **H**yper**T**ext **M**arkup **L**anguage
- HTML 不是一种编程语言，而是一种**标记**语言
- 标记语言是一套**标记标签** (markup tag)
- HTML 使用标记标签来**描述**网页
- HTML 文档包含了HTML **标签**及**文本**内容
- HTML文档也叫做 **web 页面**

# HTML 标签

HTML 标记标签通常被称为 HTML 标签 (HTML tag)。

- HTML 标签是由尖括号包围的关键词，比如 `<html>`
- HTML 标签通常是成对出现的，比如 `<b>` 和 `</b>`
- 标签对中的第一个标签是开始标签，第二个标签是结束标签
- 开始和结束标签也被称为开放标签和闭合标签

# HTML 元素

"HTML 标签" 和 "HTML 元素" 通常都是描述同样的意思.

但是严格来讲, 一个 HTML 元素包含了开始标签与结束标签。

## HTML 元素语法

- HTML 元素以**开始标签**起始
- HTML 元素以**结束标签**终止
- **元素的内容**是开始标签与结束标签之间的内容
- 某些 HTML 元素具有**空内容（empty content）**
- 空元素**在开始标签中进行关闭**（以开始标签的结束而结束）
- 大多数 HTML 元素可拥有**属性**
- HTML 标签对大小写不敏感，但是标准中强制使用小写

## HTML 属性

- HTML 元素可以设置**属性**
- 属性可以在元素中添加**附加信息**
- 属性一般描述于**开始标签**
- 属性总是以名称/值对的形式出现，**比如：name="value"**。

| 属性            | 描述                                                       | 是否HTML5新属性 |
| --------------- | ---------------------------------------------------------- | --------------- |
| accesskey       | 设置访问元素的键盘快捷键。                                 |                 |
| class           | 规定元素的类名（classname）                                |                 |
| contenteditable | 规定是否可编辑元素的内容。                                 | New             |
| contextmenu     | 指定一个元素的上下文菜单。当用户右击该元素，出现上下文菜单 | New             |
| data-*          | 用于存储页面的自定义数据                                   | New             |
| dir             | 设置元素中内容的文本方向。                                 |                 |
| draggable       | 指定某个元素是否可以拖动                                   | New             |
| dropzone        | 指定是否将数据复制，移动，或链接，或删除                   | New             |
| hidden          | hidden属性规定对元素进行隐藏。                             | New             |
| id              | 规定元素的唯一id                                           |                 |
| lang            | 设置元素中内容的语言代码。                                 |                 |
| spellcheck      | 检测元素是否拼写错误                                       | New             |
| style           | 规定元素的行内样式（inline style）                         |                 |
| tabindex        | 设置元素的Tab键控制次序。                                  |                 |
| title           | 规定元素的额外信息（可在工具提示中显示）                   |                 |
| translate       | 指定是否一个元素的值在页面载入时是否需要翻译               | New             |

# HTML头部

## HTML`head `元素

`<head>` 元素包含了所有的头部标签元素。在 `<head>`元素中你可以插入脚本（scripts）, 样式文件（CSS），及各种meta信息。

可以添加在头部区域的元素标签为: `<title>, <style>, <meta>, <link>, <script>, <noscript>, and <base>`

## HTML `title` 元素

`<title>` 标签定义了不同文档的标题。

`<title>` 在 HTML/XHTML 文档中是必须的。

`<title>` 元素:

- 定义了浏览器工具栏的标题
- 当网页添加到收藏夹时，显示在收藏夹中的标题
- 显示在搜索引擎结果页面的标题

## HTML `base` 元素

`<base>` 标签描述了基本的链接地址/链接目标，该标签作为HTML文档中所有的链接标签的默认链接:

`<script>` 元素在以后的章节中会详细描述。

## HTML `link` 元素

`<link>` 标签定义了文档与外部资源之间的关系。

`<link>` 标签通常用于链接到样式表。

## HTML `style` 元素

`<style>` 标签定义了HTML文档的样式文件引用地址.

在`<style>` 元素中你也可以直接添加样式来渲染 HTML 文档:

## HTML `meta` 元素

meta标签描述了一些基本的元数据。

`<meta>` 标签提供了元数据.元数据也不显示在页面上，但会被浏览器解析。

META 元素通常用于指定网页的描述，关键词，文件的最后修改时间，作者，和其他元数据。

元数据可以使用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他Web服务。

`<meta>` 一般放置于 `<head>` 区域

## HTML `script` 元素

`<script>`标签用于加载脚本文件，如： JavaScript。

## HTML head 元素列表

| 标签       | 描述                               |
| ---------- | ---------------------------------- |
| `<head>`   | 定义了文档的信息                   |
| `<title>`  | 定义了文档的标题                   |
| `<base>`   | 定义了页面链接标签的默认链接地址   |
| `<link>`   | 定义了一个文档和外部资源之间的关系 |
| `<meta>`   | 定义了HTML文档中的元数据           |
| `<script>` | 定义了客户端的脚本文件             |
| `<style>`  | 定义了HTML文档的样式文件           |

~~~html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>文档标题</title>
    <base href="http://www.runoob.com/images/" target="_blank">
    <link rel="stylesheet" type="text/css" href="mystyle.css">
    <meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript">
    <meta name="description" content="免费 Web & 编程 教程">
    <meta name="author" content="Runoob">
    <meta http-equiv="refresh" content="30">
    <script src=""></script>
    <style type="text/css">
    </style>
</head>

<body>
</body>

</html>
~~~

# HTML 字符实体

## 结合音标符

| 音标符       | 字符 | Construct   | 输出结果 |
| ------------ | ---- | ----------- | -------- |
| &nbsp;&nbsp;̀ | a    | a&amp;#768; | à        |
| &nbsp;&nbsp;́ | a    | a&amp;#769; | á        |
| ̂             | a    | a&amp;#770; | â        |
| &nbsp;&nbsp;̃ | a    | a&amp;#771; | ã        |

## HTML字符实体

ps:实体名称对大小写敏感！

| 显示结果 | 描述        | 实体名称             | 实体编号    |
| -------- | ----------- | -------------------- | ----------- |
| &nbsp;   | 空格        | &amp;nbsp;           | &amp;#160;  |
| &lt;     | 小于号      | &amp;lt;             | &amp;#60;   |
| &gt;     | 大于号      | &amp;gt;             | &amp;#62;   |
| &amp;    | 和号        | &amp;amp;            | &amp;#38;   |
| "        | 引号        | &amp;quot;           | &amp;#34;   |
| '        | 撇号&nbsp;  | &amp;apos;(IE不支持) | &amp;#39;   |
| ￠       | 分          | &amp;cent;           | &amp;#162;  |
| £        | 镑          | &amp;pound;          | &amp;#163;  |
| ¥        | 人民币/日元 | &amp;yen;            | &amp;#165;  |
| €        | 欧元        | &amp;euro;           | &amp;#8364; |
| §        | 小节        | &amp;sect;           | &amp;#167;  |
| ©        | 版权        | &amp;copy;           | &amp;#169;  |
| ®        | 注册商标    | &amp;reg;            | &amp;#174;  |
| ™        | 商标        | &amp;trade;          | &amp;#8482; |
| ×        | 乘号        | &amp;times;          | &amp;#215;  |
| ÷        | 除号        | &amp;divide;         | &amp;#247;  |

# HTML 速查列表

## HTML 基本文档

```html
<!DOCTYPE html>
<html>

<head>
    <title>文档标题</title>
</head>

<body>
    可见文本...
</body>

</html>
```

## 基本标签（Basic Tags）

```html
<h1>最大的标题</h1>
<h2> . . . </h2>
<h3> . . . </h3>
<h4> . . . </h4>
<h5> . . . </h5>
<h6>最小的标题</h6>
 
<p>这是一个段落。</p>
<br> （换行）
<hr> （水平线）
<!-- 这是注释 -->
```

## 文本格式化（Formatting）

```html
<b>粗体文本</b>
<code>计算机代码</code>
<em>强调文本</em>
<i>斜体文本</i>
<kbd>键盘输入</kbd> 
<pre>预格式化文本</pre>
<small>更小的文本</small>
<strong>重要的文本</strong>
 
<abbr> （缩写）
<address> （联系信息）
<bdo> （文字方向）
<blockquote> （从另一个源引用的部分）
<cite> （工作的名称）
<del> （删除的文本）
<ins> （插入的文本）
<sub> （下标文本）
<sup> （上标文本）
```

## 链接（Links）

```html
普通的链接：<a href="http://www.example.com/">链接文本</a>
图像链接： <a href="http://www.example.com/"><img src="URL" alt="替换文本"></a>
邮件链接： <a href="mailto:webmaster@example.com">发送e-mail</a>
书签：
<a id="tips">提示部分</a>	
<a href="#tips">跳到提示部分</a>
```

## 图片（Images）

```html
<img src="URL" alt="替换文本" height="42" width="42">
```

## 样式/区块（Styles/Sections）

```html
<style type="text/css">
h1 {color:red;}
p {color:blue;}
</style>
<div>文档中的块级元素</div>
<span>文档中的内联元素</span>
```

## 无序列表

```html
<ul>
    <li>项目</li>
    <li>项目</li>
</ul>
```

## 有序列表

```html
<ol>
    <li>第一项</li>
    <li>第二项</li>
</ol>
```

## 定义列表

```html
<dl>
  <dt>项目 1</dt>
    <dd>描述项目 1</dd>
  <dt>项目 2</dt>
    <dd>描述项目 2</dd>
</dl>
```

## 表格（Tables）

```html
<table border="1">
  <tr>
    <th>表格标题</th>
    <th>表格标题</th>
  </tr>
  <tr>
    <td>表格数据</td>
    <td>表格数据</td>
  </tr>
</table>
```

## 框架（Iframe）

```
<iframe src="demo_iframe.htm"></iframe>
```

## 表单（Forms）

```html
<form action="demo_form.php" method="post/get">
<input type="text" name="email" size="40" maxlength="50">
<input type="password">
<input type="checkbox" checked="checked">
<input type="radio" checked="checked">
<input type="submit" value="Send">
<input type="reset">
<input type="hidden">
<select>
<option>苹果</option>
<option selected="selected">香蕉</option>
<option>樱桃</option>
</select>
<textarea name="comment" rows="60" cols="20"></textarea>
 
</form>
```

## 实体（Entities）

```
&lt; 等同于 <
&gt; 等同于 >
&#169; 等同于 ©
```

