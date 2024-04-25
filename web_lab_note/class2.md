# 1.html的必要因素

HTML 的全称是 HyperText Markup Language,中文意思是"超文本标记语言"。

解释一下各部分的含义:

1. Hyper是超级、超链接的意思,指 HTML 能够通过链接将各种资源连接在一起。
2. Text 是文本的意思,HTML 本身是一种文本文件。
3. Markup 指的是标记,HTML 使用标签(tags)对文本等数据进行标记。
4. Language 表示它是一种语言,是计算机与人交互的一种语言工具。

例如我们看一个实例

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Title!</title>
    </head>
    <body>
        <h1>Heading!</h1>
        <p>Paragraph!</p>
    </body>
</html>
```

解释一下各行的含义：

```html
<!DOCTYPE html>
```
这一行是 DOCTYPE 声明,告诉浏览器使用什么规范来渲染网页。`<!DOCTYPE html>`表示使用 HTML5 标准模式渲染，这也是目前最新的方式。

```html
<html>
...
<\html>
```
`<html>`标签是HTML文档的根元素,所有其他元素都应该包含在`<html>`与`<\html>`之间。

```html
    <head>
    </head>
```
`<head>`元素用于说明文档的某些信息，比如定义文档的元数据、链接资源、设置title等,这些内容不会在网页上直接显示出来。

像一些检索软件，就是通过搜索其中的内容(元数据等)来进行检索。

```html  
 <title>Title!</title>
```
`<title>`标签设置了文档的标题,这会显示在浏览器标签页上。

```html
<body>
</body>
```
`<body>`元素包含了网页上可见的内容,比如标题、段落、图像、链接等等。

这是我们网页上的主题元素，所有的段落，标题会出现在`<body>`与`</body>`内部。

```html
<h1>Heading!</h1>
```
`<h1>`是一种标题标签,`<h1>`表示最大的一级标题。

```html
<p>Paragraph!</p>
```
`<p>`标签定义了一个段落。

注意，`html`内不允许同级标签互相嵌套，即`<a><b></a></b>`的形式，这个相对复杂。

# 2.html的标签与参数

实际上html拥有非常多的tag，以及这些tag中可以出现很多参数从而控制这些tag的内容，比如说

## 1.锚

或者说我认为是一个类似于obsidian中的链接功能，其实现的代码为：

```html
<a href="url">some sentences</a>
```

其应该放在`<body>`之处，这样这个some sentences会可以点击，点击之后会定向到前面这个`url`对应的网址处

## 2.图像

这里也是一个常见的方法，即：

```html
<img src=""></img>
```

这里可能并不需要再插入文字，因此可以使用`<img src="" />`

这里`""`应该输入图片的路径与名字，我们会视`此html`所在的路径为根目录，因此如果创建了一个`image`文件夹，语法应该为：

```html
<img src="image/image_name" \>
```

## 3.div

`div`相当于一个空盒子，他包裹的内容就是一个整体，比如说:

```html
<div>
    <h1>something</h1>
    <p>something</p>
</div>
```

这样的话就包裹了两个东西，因此我如果在`<div>`中输入参数，会改变整个盒子内的内容，但是我们还是要谨慎使用，因为我们要保证代码语义比较鲜明，全都是`div`会让人或者爬虫读不懂你的代码。

由于`html`中的标签和参数非常多，我们也记不过来，这里MIT的老师推荐了一个[网址]([HTML（超文本标记语言） | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/HTML))

## 4.一个 HTML 中常用标签及其参数的表格:

| 标签            | 描述               | 常用属性                                                |
| --------------- | ------------------ | ------------------------------------------------------- |
| `<a>`           | 定义超链接         | `href`(链接地址), `target`(打开方式), `title`(提示信息) |
| `<img>`         | 插入图片           | `src`(图片路径), `alt`(替代文本), `width`, `height`     |
| `<div>`         | 定义文档区块       | `class`(CSS类), `id`(唯一标识符), `style`(CSS样式)      |
| `<span>`        | 定义行内元素       | `class`, `id`, `style`                                  |
| `<h1>` - `<h6>` | 定义标题(由大到小) | `class`, `id`, `style`                                  |
| `<p>`           | 定义段落           | `class`, `id`, `style`                                  |
| `<ul>`, `<ol>`  | 无序/有序列表      | `class`, `id`, `style`                                  |
| `<li>`          | 列表项             | `value`(有序列表项值)                                   |
| `<table>`       | 定义表格           | `border`(边框宽度)                                      |
| `<tr>`          | 定义表格行         | -                                                       |
| `<th>`          | 定义表头单元格     | `colspan`(横跨单元格数), `rowspan`(纵跨单元格数)        |
| `<td>`          | 定义表格数据单元格 | `colspan`, `rowspan`                                    |
| `<form>`        | 定义表单           | `action`(提交地址), `method`(提交方式)                  |
| `<input>`       | 定义输入控件       | `type`(控件类型), `value`(值), `name`(名称)             |
| `<button>`      | 定义按钮           | `type`(按钮类型)                                        |
| `<select>`      | 定义下拉列表       | `name`(名称), `multiple`(是否多选)                      |
| `<option>`      | 定义下拉选项       | `value`(值), `selected`(默认选中)                       |
| `<textarea>`    | 定义多行文本框     | `rows`(行数), `cols`(列数), `name`(名称)                |

