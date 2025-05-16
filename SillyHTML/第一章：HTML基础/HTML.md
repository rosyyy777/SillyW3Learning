# 	HTML Learning (Start from 15/May/2025)

## What is HTML?

**HTML**  全称是超文本标记语言(HyperText Markup Language)。最新规范HTML5是现代网页技术的重要组成部分，用于描述网页的结构以及各部分的含义。其他重要成员有CSS（描述网页中元素的样式）和JavaScript（描述网页交互和一些动态行为）。

"Hypertext"指代的是将一个web页面连接到另一个，他们可能处于同一个网站或者是不同网站（网站：一系列Web页面的集合或者归属）。链接（Links）是Web一个关键的方面。通过向Internet上传内容并且将他们连接到别人的页面，你成为了万维网（World Wide Web/3W）活跃的一员。

## HTML元素（Element）

一个HTML文档由HTML元素嵌套组成，一个元素的基本结构如下：

```html
<tag>content</tag>
```

**Notes**

- 标签（Tag）对大小写不敏感，即`<title>`和`<Title>`,`<TITLE>`都能够被识别，但一般建议统一小写。
- 元素可以嵌套，但就像编程语言那样，最近的闭合括号对应上一个开括号，不能交叉嵌套。

```html
<p>Here is a <strong>right</strong> example.</p>
```

显示效果：

<p>Here is a <strong>right</strong> example.</p>

- HTML5建议将HTML的功能限定在定义结构和含义而非样式。即便有一些标签（Tag）能够改变文字的显示效果（如`<h1>`,`<b>`），但不建议因为这个去使用他们。单纯想改变样式可以借助CSS，但如果想要表达具体的含义，如强调就可以使用`<strong>`。

### Void Element

不是所有的元素都有闭合Tag，有一些元素用单个标签表示，例如`<img>`。

## 属性（Attributes）

元素拥有属性，看起来就像这样：

```html
<p class="editor-note">Here is a good example.</p>
```

一个元素可能会拥有多个属性，他们不会显示在你的浏览器中，但是会辅助你的元素的显示效果。

下面给出一个图片元素作为例子，我想要在浏览器中显示这个文件夹下的图片example.png，该怎么办呢？

```html
<img src="./example.jpg" />
```

意思是我要加载一个图片，图片的源（source，略写为src）路径是当前目录下（`./`表示当前目录）名为`example.jpg`的文件，这就是图片的一个属性。效果如下：

<img src="./example.jpg" width=50%/>

我感觉这个图片太大了，怎么办呢？

```
<img src="./example.jpg" width=50px />
```

<img src="./example.jpg" width=50px />

`width`属性决定了图片的宽度，你还可以通过改变`height`属性来改变图片大小。如果没有同时指定`width`和`height`，图片会按照原有比例自动显示。

有时候图片会因为意外加载失败，为了减轻这种情况导致的体验感变差，我们还可以加上`alt`属性来描述图片本应该呈现的样子。此外，在朗读模式或者其他用户不便阅读的情况下，`alt`描述也会代替图片传达给用户。

```html
<img src="./doNotExist.png" alt="一个可爱的头像。">
```

### 布尔属性（Boolean Attributes）

有时候一些属性没有被赋值，这是完全可以接受的，他们被称为布尔属性。布尔属性可以接收任何值：空字符串（`attribute=""`）、长得像自己的字符串（`attribute="attribute"`），甚至是长得像false的字符串（`attribute="false"`）。但是哪怕字符串长得像false，只要布尔属性被设置了，布尔属性的布尔值始终是`true`。反之，如果布尔属性没被设置，即没出现在标签里，那么它的值就是`false`。

例如：

```html
<input type="text" disabled="" />
<input type="text" disabled="disabled" />
<input type="text" disabled="false" />
<!-- 上面三个例子是一样的，disabled都被设置成true -->
<!-- 你也可以这么写： -->
<input type="text" disabled />
<!-- 使用这个属性会让用户没办法在这个输入框内输入内容 -->

<input type="text" />
<!-- 这个就可以 -->
```

## 一个基础的HTML文档

```html
<!doctype html>
<html lang="en-US">
    <head>
        <meta charset="utf-8" />
        <title>Hello</title>
    </head>
    <body>
        <p>
            Hello, world!
        </p>
    </body>
</html>
```

