一、 React是什么？
React是Facebook开源的用于构建用户界面的javascript库。

二、React的特点即它与其他js库相比好在哪里？
1、专注MVC架构中的V（view），使React很容易和开发者已有的开发栈进行融合
2、组件化，React顺应了web开发组件化趋势，从UI抽象出不同的组件，方便多次使用
3、提高造作性能，React抛弃html而应用JSX语法，因为DOM操作非常慢，所以引入虚拟DOM的概念

三、JSX
注意点：HTML 里的 class 在 JSX 里要写成 className，因为 class 在 JS 里是保留关键字。

四、组件
1、组件初始化
    初始化this.state的值，只在组件装载之前调用一次
    但是在ES6中，可以在构造函数中初始化状态
   
```javasvript
class Counter extends Component {
  constructor(props) {
    super(props); // props 是预先定义好的对象值：
    this.state = { count: props.initialCount };
  }
  render() {
    // ...
  }   //render是必须的，是组装成这个组件的HTML结构
}

```
2、生命周期函数     
装载组件触发：
（1）componentWillMount
只会在装载之前调用一次，在 render 之前调用，你可以在这个方法里面调用 setState 改变状态，并且不会导致额外调用一次 render
 
（2）componentDidMount
只会在装载完成之后调用一次，在 render 之后调用，从这里开始可以通过 ReactDOM.findDOMNode(this)获取到组件的 DOM 节点。

更新组件触发：
这些方法不会在首次 render 组件的周期调用

* componentWillReceiveProps
* shouldComponentUpdate
* componentWillUpdate
* componentDidUpdate

卸载组件触发：
* componentWillUnmount


五、 state和props
组件先根据自己的props渲染一次自己，props是不可变的，它们从父节点传递过来，被父节点拥有。
为了实现交互，我们给组件引进了可变的state。this.state 是组件私有的，可以通过调用 this.setState() 来改变它，当状态改变时，组件重新渲染自己。



