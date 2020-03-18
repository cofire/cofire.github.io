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

# CSS 盒子模型

所有HTML元素可以看作盒子，在CSS中，"box model"这一术语是用来设计和布局时使用。

CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容。

盒模型允许我们在其它元素和周围元素边框之间的空间放置元素。

下面的图片说明了盒子模型(Box Model)：

![盒子模型](../../static/img/编程语言/css/box-model.gif "盒子模型")

不同部分的说明：

- **Margin(外边距)** - 清除边框外的区域，外边距是透明的。
- **Border(边框)** - 围绕在内边距和内容外的边框。
- **Padding(内边距)** - 清除内容周围的区域，内边距是透明的。
- **Content(内容)** - 盒子的内容，显示文本和图像。

# 元素常见样式

## CSS 边框

| 属性                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [border](https://www.runoob.com/cssref/pr-border.html)       | 简写属性，用于把针对四个边的属性设置在一个声明。             |
| [border-style](https://www.runoob.com/cssref/pr-border-style.html) | 用于设置元素所有边框的样式，或者单独地为各边设置边框样式。   |
| [border-width](https://www.runoob.com/cssref/pr-border-width.html) | 简写属性，用于为元素的所有边框设置宽度，或者单独地为各边边框设置宽度。 |
| [border-color](https://www.runoob.com/cssref/pr-border-color.html) | 简写属性，设置元素的所有边框中可见部分的颜色，或为 4 个边分别设置颜色。 |
| [border-bottom](https://www.runoob.com/cssref/pr-border-bottom.html) | 简写属性，用于把下边框的所有属性设置到一个声明中。           |
| [border-bottom-color](https://www.runoob.com/cssref/pr-border-bottom-color.html) | 设置元素的下边框的颜色。                                     |
| [border-bottom-style](https://www.runoob.com/cssref/pr-border-bottom-style.html) | 设置元素的下边框的样式。                                     |
| [border-bottom-width](https://www.runoob.com/cssref/pr-border-bottom-width.html) | 设置元素的下边框的宽度。                                     |
| [border-left](https://www.runoob.com/cssref/pr-border-left.html) | 简写属性，用于把左边框的所有属性设置到一个声明中。           |
| [border-left-color](https://www.runoob.com/cssref/pr-border-left-color.html) | 设置元素的左边框的颜色。                                     |
| [border-left-style](https://www.runoob.com/cssref/pr-border-left-style.html) | 设置元素的左边框的样式。                                     |
| [border-left-width](https://www.runoob.com/cssref/pr-border-left-width.html) | 设置元素的左边框的宽度。                                     |
| [border-right](https://www.runoob.com/cssref/pr-border-right.html) | 简写属性，用于把右边框的所有属性设置到一个声明中。           |
| [border-right-color](https://www.runoob.com/cssref/pr-border-right-color.html) | 设置元素的右边框的颜色。                                     |
| [border-right-style](https://www.runoob.com/cssref/pr-border-right-style.html) | 设置元素的右边框的样式。                                     |
| [border-right-width](https://www.runoob.com/cssref/pr-border-right-width.html) | 设置元素的右边框的宽度。                                     |
| [border-top](https://www.runoob.com/cssref/pr-border-top.html) | 简写属性，用于把上边框的所有属性设置到一个声明中。           |
| [border-top-color](https://www.runoob.com/cssref/pr-border-top-color.html) | 设置元素的上边框的颜色。                                     |
| [border-top-style](https://www.runoob.com/cssref/pr-border-top-style.html) | 设置元素的上边框的样式。                                     |
| [border-top-width](https://www.runoob.com/cssref/pr-border-top-width.html) | 设置元素的上边框的宽度。                                     |

## CSS 轮廓（outline）

轮廓（outline）是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。

CSS outline 属性规定元素轮廓的样式、颜色和宽度。

![Outline](../../static/img/编程语言/css/box_outline.gif "CSS轮廓")

| 属性                                                         | 说明                           | 值                                                           | CSS  |
| :----------------------------------------------------------- | :----------------------------- | :----------------------------------------------------------- | :--- |
| [outline](https://www.runoob.com/cssref/pr-outline.html)     | 在一个声明中设置所有的轮廓属性 | outline-color outline-style outline-width inherit            | 2    |
| [outline-color](https://www.runoob.com/cssref/pr-outline-color.html) | 设置轮廓的颜色                 | color-name hex-number rgb-number invert inherit              | 2    |
| [outline-style](https://www.runoob.com/cssref/pr-outline-style.html) | 设置轮廓的样式                 | none dotted dashed solid double groove ridge inset outset inherit | 2    |
| [outline-width](https://www.runoob.com/cssref/pr-outline-width.html) | 设置轮廓的宽度                 | thin medium thick length inherit                             | 2    |

## CSS margin(外边距)

margin 清除周围的（外边框）元素区域。margin 没有背景颜色，是完全透明的。

margin 可以单独改变元素的上，下，左，右边距，也可以一次改变所有的属性。

## padding（填充）

当元素的 padding（填充）内边距被清除时，所释放的区域将会受到元素背景颜色的填充。

单独使用 padding 属性可以改变上下左右的填充。

![img](../../static/img/编程语言/css/VlwVi.png)

| 属性                                                         | 描述                                       |
| :----------------------------------------------------------- | :----------------------------------------- |
| [margin](https://www.runoob.com/cssref/pr-margin.html)       | 简写属性。在一个声明中设置所有外边距属性。 |
| [margin-bottom](https://www.runoob.com/cssref/pr-margin-bottom.html) | 设置元素的下外边距。                       |
| [margin-left](https://www.runoob.com/cssref/pr-margin-left.html) | 设置元素的左外边距。                       |
| [margin-right](https://www.runoob.com/cssref/pr-margin-right.html) | 设置元素的右外边距。                       |
| [margin-top](https://www.runoob.com/cssref/pr-margin-top.html) | 设置元素的上外边距。                       |
| [padding](https://www.runoob.com/cssref/pr-padding.html)     | 使用简写属性设置在一个声明中的所有填充属性 |
| [padding-bottom](https://www.runoob.com/cssref/pr-padding-bottom.html) | 设置元素的底部填充                         |
| [padding-left](https://www.runoob.com/cssref/pr-padding-left.html) | 设置元素的左部填充                         |
| [padding-right](https://www.runoob.com/cssref/pr-padding-right.html) | 设置元素的右部填充                         |
| [padding-top](https://www.runoob.com/cssref/pr-padding-top.html) | 设置元素的顶部填充                         |

## CSS 尺寸 (Dimension)

所有CSS 尺寸 (Dimension)属性

| 属性                                                         | 描述                 |
| :----------------------------------------------------------- | :------------------- |
| [height](https://www.runoob.com/cssref/pr-dim-height.html)   | 设置元素的高度。     |
| [line-height](https://www.runoob.com/cssref/pr-dim-line-height.html) | 设置行高。           |
| [max-height](https://www.runoob.com/cssref/pr-dim-max-height.html) | 设置元素的最大高度。 |
| [max-width](https://www.runoob.com/cssref/pr-dim-max-width.html) | 设置元素的最大宽度。 |
| [min-height](https://www.runoob.com/cssref/pr-dim-min-height.html) | 设置元素的最小高度。 |
| [min-width](https://www.runoob.com/cssref/pr-dim-min-width.html) | 设置元素的最小宽度。 |
| [width](https://www.runoob.com/cssref/pr-dim-width.html)     | 设置元素的宽度。     |