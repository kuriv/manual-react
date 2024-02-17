# Refs

以下代码为按钮绑定了一个点击事件，当用户点击按钮时，控制台将打印输入框中的数据。

```jsx
<script type="text/babel">
    class Component extends React.Component {
        render() {
            return (
                <section>
                    <input ref={this.saveInputNode} type="text"/>
                    <button onClick={this.printInputValue}>print</button>
                </section>
            );
        }

        saveInputNode = currentNode => this.inputNode = currentNode;

        printInputValue = () => {
            console.log(this.inputNode.value);
        }
    }

    ReactDOM.createRoot(document.getElementById('app')).render(<Component/>);
</script>
```

也可以使用 React 内置 API 来实现相关操作。

```jsx
<script type="text/babel">
    class Component extends React.Component {
        inputRef = React.createRef();

        render() {
            return (
                <section>
                    <input ref={this.inputRef} type="text"/>
                    <button onClick={this.printInputValue}>print</button>
                </section>
            );
        }

        printInputValue = () => {
            console.log(this.inputRef.current.value);
        }
    }

    ReactDOM.createRoot(document.getElementById('app')).render(<Component/>);
</script>
```

