# State

以下代码为容器绑定了一个点击事件，当用户点击容器时，组件中的数据将会被修改。

```jsx
<script type="text/babel">
    class Component extends React.Component {
        state = {
            flag: true
        }

        render() {
            return (
                <h1 onClick={this.changeState}>Hello React</h1>
            );
        }

        changeState = () => {
            this.setState({
                flag: false
            });
        }
    }

    ReactDOM.createRoot(document.getElementById('app')).render(<Component/>);
</script>
```

下面继续为容器绑定点击事件，当用户点击容器时，容器中的文本内容会随之切换。

```jsx
<script type="text/babel">
    class Component extends React.Component {
        state = {
            flag: true
        }

        render() {
            return (
                <h1 onClick={this.changeState}>
                    {this.state.flag ? 'Hello React' : 'Hello World'}
                </h1>
            );
        }

        changeState = () => {
            this.setState({
                flag: !this.state.flag
            });
        }
    }

    ReactDOM.createRoot(document.getElementById('app')).render(<Component/>);
</script>
```

