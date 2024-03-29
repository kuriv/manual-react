# Props

可以像使用 HTML 属性一样，将所需的数据内容传递给组件。

```jsx
<script type="text/babel">
    class Person extends React.Component {
        render() {
            return (
                <ul>
                    <li>
                        <label>name:</label>
                        <span>{this.props.name}</span>
                    </li>
                    <li>
                        <label>age:</label>
                        <span>{this.props.age}</span>
                    </li>
                </ul>
            );
        }
    }

    ReactDOM.createRoot(document.getElementById('app')).render(<Person name="Tom" age="18"/>);
</script>
```

也可以使用展开语法传递对象数据给组件。

```jsx
<script type="text/babel">
    class Person extends React.Component {
        render() {
            return (
                <ul>
                    <li>
                        <label>name:</label>
                        <span>{this.props.name}</span>
                    </li>
                    <li>
                        <label>age:</label>
                        <span>{this.props.age}</span>
                    </li>
                </ul>
            );
        }
    }

    const Props = {
        name: 'Tom',
        age: 18
    }
    ReactDOM.createRoot(document.getElementById('app')).render(<Person {...Props}/>);
</script>
```

引入 prop-types 库文件，即可校验传递给组件的数据，如果数据不符合校验规则，则代码将会报错。

```jsx
<script type="text/javascript" src="prop-types.js"></script>
<script type="text/babel">
    class Person extends React.Component {
        static propTypes = {
            name: PropTypes.string.isRequired,
            age: PropTypes.number
        }

        render() {
            return (
                <ul>
                    <li>
                        <label>name:</label>
                        <span>{this.props.name}</span>
                    </li>
                    <li>
                        <label>age:</label>
                        <span>{this.props.age}</span>
                    </li>
                </ul>
            );
        }
    }

    ReactDOM.createRoot(document.getElementById('app')).render(<Person/>);
</script>
```

为组件所需的数据内容设置默认值，示例代码如下。

```jsx
<script type="text/javascript" src="prop-types.js"></script>
<script type="text/babel">
    class Person extends React.Component {
        static propTypes = {
            name: PropTypes.string.isRequired,
            age: PropTypes.number
        }

        static defaultProps = {
            name: 'Tom',
            age: 18
        }

        render() {
            return (
                <ul>
                    <li>
                        <label>name:</label>
                        <span>{this.props.name}</span>
                    </li>
                    <li>
                        <label>age:</label>
                        <span>{this.props.age}</span>
                    </li>
                </ul>
            );
        }
    }

    ReactDOM.createRoot(document.getElementById('app')).render(<Person/>);
</script>
```

