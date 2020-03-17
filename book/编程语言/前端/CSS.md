# CSS 简介

- CSS 指层叠样式表 (**C**ascading **S**tyle **S**heets)
- 样式定义**如何显示** HTML 元素
- 样式通常存储在**样式表**中
- 把样式添加到 HTML 4.0 中，是为了**解决内容与表现分离的问题**
- **外部样式表**可以极大提高工作效率
- 外部样式表通常存储在 **CSS 文件**中
- 多个样式定义可**层叠**为一个

# 选择器

| 选择器                     | 示例                  | 示例说明                                                  | CSS  |
| -------------------------- | --------------------- | --------------------------------------------------------- | ---- |
| .class                     | .intro                | 选择所有class="intro"的元素                               | 1    |
| #id                        | #firstname            | 选择所有id="firstname"的元素                              | 1    |
| *                          | *                     | 选择所有元素                                              | 2    |
| element                    | p                     | 选择所有`<p>`元素                                         | 1    |
| element,element            | div,p                 | 选择所有`<div>`元素和`<p>`元素                            | 1    |
| element element            | div p                 | 选择`<div>`元素内的所有`<p>`元素                          | 1    |
| element>element            | div>p                 | 选择所有父级是 `<div>` 元素的`<p> `元素                   | 1    |
| element+element            | div+p                 | 选择所有紧接着`<div>`元素之后的`<p>`元素                  | 2    |
| [attribute]                | [target]              | 选择所有带有target属性元素                                | 2    |
| [attribute=value]          | [target=-blank]       | 选择所有使用target="-blank"的元素                         | 2    |
| [attribute~=value]         | [title~=flower]       | 选择标题属性包含单词"flower"的所有元素                    | 2    |
| [attribute&#124;=language] | [lang&#124;=en]       | 选择 lang 属性以 en 为开头的所有元素                      | 2    |
| :link                      | a:link                | 选择所有未访问链接                                        | 1    |
| :visited                   | a:visited             | 选择所有访问过的链接                                      | 1    |
| :active                    | a:active              | 选择活动链接                                              | 1    |
| :hover                     | a:hover               | 选择鼠标在链接上面时                                      | 1    |
| :focus                     | input:focus           | 选择具有焦点的输入元素                                    | 2    |
| :first-letter              | p:first-letter        | 选择每一个`<p>`元素的第一个字母                           | 1    |
| :first-line                | p:first-line          | 选择每一个`<p>`元素的第一行                               | 1    |
| :first-child               | p:first-child         | 指定只有当`<p>`元素是其父级的第一个子级的样式。           | 2    |
| :before                    | p:before              | 在每个`<p>`元素之前插入内容                               | 2    |
| :after                     | p:after               | 在每个`<p>`元素之后插入内容                               | 2    |
| :lang(language)            | p:lang(it)            | 选择一个lang属性的起始值="it"的所有`<p>`元素              | 2    |
| element1~element2          | p~ul                  | 选择p元素之后的每一个ul元素                               | 3    |
| [attribute^=value]         | a[src^="https"]       | 选择每一个src属性的值以"https"开头的元素                  | 3    |
| [attribute$=value]         | a[src$=".pdf"]        | 选择每一个src属性的值以".pdf"结尾的元素                   | 3    |
| [attribute*=value]         | a[src*="runoob"]      | 选择每一个src属性的值包含子字符串"runoob"的元素           | 3    |
| :first-of-type             | p:first-of-type       | 选择每个p元素是其父级的第一个p元素                        | 3    |
| :last-of-type              | p:last-of-type        | 选择每个p元素是其父级的最后一个p元素                      | 3    |
| :only-of-type              | p:only-of-type        | 选择每个p元素是其父级的唯一p元素                          | 3    |
| :only-child                | p:only-child          | 选择每个p元素是其父级的唯一子元素                         | 3    |
| :nth-child(n)              | p:nth-child(2)        | 选择每个p元素是其父级的第二个子元素                       | 3    |
| :nth-last-child(n)         | p:nth-last-child(2)   | 选择每个p元素的是其父级的第二个子元素，从最后一个子项计数 | 3    |
| :nth-of-type(n)            | p:nth-of-type(2)      | 选择每个p元素是其父级的第二个p元素                        | 3    |
| :nth-last-of-type(n)       | p:nth-last-of-type(2) | 选择每个p元素的是其父级的第二个p元素，从最后一个子项计数  | 3    |
| :last-child                | p:last-child          | 选择每个p元素是其父级的最后一个子级。                     | 3    |
| :root                      | :root                 | 选择文档的根元素                                          | 3    |
| :empty                     | p:empty               | 选择每个没有任何子级的p元素（包括文本节点）               | 3    |
| :target                    | #news:target          | 选择当前活动的#news元素（包含该锚名称的点击的URL）        | 3    |
| :enabled                   | input:enabled         | 选择每一个已启用的输入元素                                | 3    |
| :disabled                  | input:disabled        | 选择每一个禁用的输入元素                                  | 3    |
| :checked                   | input:checked         | 选择每个选中的输入元素                                    | 3    |
| :not(selector)             | :not(p)               | 选择每个并非p元素的元素                                   | 3    |
| ::selection                | ::selection           | 匹配元素中被用户选中或处于高亮状态的部分                  | 3    |
| :out-of-range              | :out-of-range         | 匹配值在指定区间之外的input元素                           | 3    |
| :in-range                  | :in-range             | 匹配值在指定区间之内的input元素                           | 3    |
| :read-write                | :read-write           | 用于匹配可读及可写的元素                                  | 3    |
| :read-only                 | :read-only            | 用于匹配设置 "readonly"（只读） 属性的元素                | 3    |
| :optional                  | :optional             | 用于匹配可选的输入元素                                    | 3    |
| :required                  | :required             | 用于匹配设置了 "required" 属性的元素                      | 3    |
| :valid                     | :valid                | 用于匹配输入值为合法的元素                                | 3    |
| :invalid                   | :invalid              | 用于匹配输入值为非法的元素                                | 3    |

# 类型

插入样式表的方法有三种:

- 外部样式表(External style sheet)
- 内部样式表(Internal style sheet)
- 内联样式(Inline style)

## 外部样式表

当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用 <link> 标签链接到样式表。 <link> 标签在（文档的）头部：

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

## 内部样式表

当单个文档需要特殊的样式时，就应该使用内部样式表。你可以使用 `<style> `标签在文档头部定义内部样式表，就像这样:

```html
<head>
<style>
hr {color:sienna;}
p {margin-left:20px;}
body {background-image:url("images/back40.gif");}
</style>
</head>
```

## 内联样式

由于要将表现和内容混杂在一起，内联样式会损失掉样式表的许多优势。请慎用这种方法，例如当样式仅需要在一个元素上应用一次时。

要使用内联样式，你需要在相关的标签内使用样式（style）属性。Style 属性可以包含任何 CSS 属性。本例展示如何改变段落的颜色和左外边距：

```html
<p style="color:sienna;margin-left:20px">这是一个段落。</p>
```

## 多重样式

如果某些属性在不同的样式表中被同样的选择器定义，那么属性值将从更具体的样式表中被继承过来。 

例如:

```css
/**外部样式表拥有针对 h3 选择器的三个属性**/
h3
{
    color:red;
    text-align:left;
    font-size:8pt;
}
/**而内部样式表拥有针对 h3 选择器的两个属性**/
h3
{
    text-align:right;
    font-size:20pt;
}

/**假如拥有内部样式表的这个页面同时与外部样式表链接，那么 h3 得到的样式是**/
h3
{
    color:red;
    text-align:right;
    font-size:20pt;
}
```

## 多重样式优先级

样式表允许以多种方式规定样式信息。样式可以规定在单个的 HTML 元素中，在 HTML 页的头元素中，或在一个外部的 CSS 文件中。甚至可以在同一个 HTML 文档内部引用多个外部样式表。

一般情况下，优先级如下：

**内联样式）Inline style > （内部样式）Internal style sheet >（外部样式）External style sheet > 浏览器默认样式**

**通用选择器（*） > 元素(类型)选择器 > 类选择器 > 属性选择器 > 伪类 > ID 选择器 > 内联样式 **

当 **!important** 规则被应用在一个样式声明中时,该样式声明会覆盖CSS中任何其他的声明, 无论它处在声明列表中的哪里. 尽管如此, !important规则还是与优先级毫无关系.使用 !important 不是一个好习惯，因为它改变了你样式表本来的级联规则，从而使其难以调试。

一些经验法则：

- **Always** 要优化考虑使用样式规则的优先级来解决问题而不是 `!important`
- **Only** 只在需要覆盖全站或外部 css（例如引用的 ExtJs 或者 YUI ）的特定页面中使用 `!important`
- **Never** 永远不要在全站范围的 css 上使用` !important`
- **Never** 永远不要在你的插件中使用 `!important`