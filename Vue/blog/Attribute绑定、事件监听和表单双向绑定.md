# Attribute绑定、事件监听和表单双向绑定

## Attribute绑定

在vue中，双大括号只能用于文本插值。为了给attribute绑定一个动态值，需要`v-bind`指令。

```vue
<div v-bind:id="dynamicId"></div>
```

也有简写语法：

```vue
<div :id="dynamicId"></div>
```

## 事件监听

使用`v-on`监听DOM事件。也可以简写为`@`。