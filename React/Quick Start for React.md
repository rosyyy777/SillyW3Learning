[TOC]

# Quick Start for React

You will learn

- How to create and nest components
- How to add markup and styles
- How to display data
- How to render conditions and lists
- How to respond to events and update the screen
- How to share data between components

## Creating and nesting components (组件)

React 应用程序由组件构成。组件是 UI（用户界面）的一部分，具有自己的逻辑和外观。一个组件可以很小，比如一个按钮，也可以很大，如整个页面。

React 组件是构建 React 应用程序的基本构建块。它们是可重用的、自包含的 UI 元素，可以用于构建用户界面的不同部分。每个 React 组件都有自己的状态（如果需要）和生命周期方法，以及用于渲染它们的视图部分。

React 组件通常分为两种类型：

1. **函数组件**：函数组件是一种定义为 JavaScript 函数的组件，接受一些输入（称为 props），并返回一个描述了 UI 外观的 React 元素。函数组件是React 16.8之后引入的 Hooks 特性后，用来替代类组件的方式。

   例如：
   ```jsx
   function Welcome(props) {
     return <h1>Hello, {props.name}</h1>;
   }
   ```

2. **类组件**：类组件是使用 ES6 类语法定义的组件，它们可以包含状态（state）和生命周期方法。类组件通常用于更复杂的场景，需要处理组件状态的变化和生命周期事件。

   例如：
   ```jsx
   class Counter extends React.Component {
     constructor(props) {
       super(props);
       this.state = { count: 0 };
     }
   
     render() {
       return <div>{this.state.count}</div>;
     }
   }
   ```

React 组件可以嵌套在彼此之中，构建复杂的用户界面，因此你可以创建一个组件，该组件内部包含其他组件，以模块化和组织代码。这种嵌套和组合组件的方式使得 React 应用程序更易于维护和扩展。

## Displaying data

## Conditional rendering (条件渲染)

## Rendering lists

## Responding to events

