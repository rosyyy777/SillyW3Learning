# CSS 网页布局：display

### `display: inline-grid`

`dispaly: inline-grid`是CSS中的一种布局模式，它结合了**网格布局（Grid Layout）**和**内联元素（inline element）**的特性。

**特点**

1. **网格布局：**

    - 元素本身会成为一个网格容器，可以使用`grid-template-rows`、`grid-template-columns`等属性来定义网格。
    - 子元素会成为网格项（grid-items），并按照网格规则排列。
2. **内联特性：**
    - 元素本身的显示行为类似于内联元素，不会占据整行，而是根据内容的宽度和高度决定大小。
    - 它的外部表现类似于`display:inline`，但内部是一个网格布局。