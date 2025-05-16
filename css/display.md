# CSS 网页布局

<a href="#inline-grid">`inline-grid`</a>

<h2 id="flex">弹性盒子（Flexbox）</h2>

弹性盒子是一种一维的布局方式，以行或者列的方向。弹性盒子里的单项会根据剩余空间放大或者收缩。

<h2>网格（Grid）</h2>

CSS网格布局是一种二维布局。他让你能够在行和列上组织内容，并且提供了许多特征用以简化复杂布局的建立。

<h2>响应式设计（Responsive Design）</h2>

随着越来越多不同屏幕尺寸的设别出现，响应式设计的概念随之兴起：一系列能够让网页变化布局和外貌来适应屏幕尺寸、分辨率的做法。

<h2 id="inline-grid">inline-grid</h2>

`dispaly: inline-grid`是CSS中的一种布局模式，它结合了**网格布局（Grid Layout）**和**内联元素（inline element）**的特性。

**特点**

1. **网格布局：**
    - 元素本身会成为一个网格容器，可以使用`grid-template-rows`、`grid-template-columns`等属性来定义网格。
    - 子元素会成为网格项（grid-items），并按照网格规则排列。
2. **内联特性：**
    - 元素本身的显示行为类似于内联元素，不会占据整行，而是根据内容的宽度和高度决定大小。
    - 它的外部表现类似于`display:inline`，但内部是一个网格布局。