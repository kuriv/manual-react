# JSX 语法规则

> 注意，定义虚拟 DOM 的代码不能使用引号包起来，否则，以下代码将会作为字符串渲染输出。

```jsx
<script type="text/babel">
    const App = '<h1>Hello React</h1>';
    ReactDOM.render(App, document.getElementById('app'));
</script>
```

> 虚拟 DOM 必须只有一个根标签，否则，以下代码将会报错。

```jsx
<script type="text/babel">
    const App = (
        <h1>Hello</h1>
        <h2>React</h2>
    );
    ReactDOM.render(App, document.getElementById('app'));
</script>
```

> 如果虚拟 DOM 中有自闭合标签，则必须闭合。

```jsx
<script type="text/babel">
    const App = <input type="text"></input>;
    ReactDOM.render(App, document.getElementById('app'));
</script>
```

> 如果在虚拟 DOM 中使用大写字母开头的标签，则 React 默认会将其作为组件渲染输出。如果使用小写字母开头的标签，则 React 默认会将其作为 HTML 同名标签渲染输出，当 HTML 标签中不存在同名标签时，以下代码将会报错。

```jsx
<script type="text/babel">
    const App = <app>Hello React</app>;
    ReactDOM.render(App, document.getElementById('app'));
</script>
```

> 如果要在虚拟 DOM 中混入 Javascript 表达式，则需要使用大括号。

```jsx
<script type="text/babel">
    let foo = 'bar';
    const App = <h1 id={foo}>Hello React</h1>;
    ReactDOM.render(App, document.getElementById('app'));
</script>
```

> 如果需要指定类名，则不能使用 `class` 关键字，而是使用 `className` 关键字。

```jsx
<script type="text/babel">
    let foo = 'bar';
    const App = <h1 className={foo}>Hello React</h1>;
    ReactDOM.render(App, document.getElementById('app'));
</script>
```

> 如果要在虚拟 DOM 中使用内联样式，则需要使用双大括号，且样式属性名遵循小驼峰命名规则。

```jsx
<script type="text/babel">
    const App = <h1 style={{color: 'red', fontSize: '12px'}}>Hello React</h1>;
    ReactDOM.render(App, document.getElementById('app'));
</script>
```
