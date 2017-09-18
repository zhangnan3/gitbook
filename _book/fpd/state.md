一个React组件接受的数据有两类。一类就是我们介绍过的 props（属性值），另一类就是state （状态值）。Props 是组件跟外部世界沟通的桥梁，而组件内部的数据，则会存放到state中。
state 中存放的是组件中**会变化**的数据，变化的原因一般是用户交互，也有其他原因。

## 赋值和使用

一个组件初始化的时候，一般会对它用到的所有state赋值，如下六行：

```js
import React, { Component } from 'react'
import './app.css'

class App extends Component {

  state = {
    count: 0
  }

  handleClick = () => {
    this.setState({
      count: this.state.count + 1
    })
  }

  render () {
    return (
      <div onClick={this.handleClick} className='app'>
        <div id="count" className='count'>
          {this.state.count}
        </div>
      </div>
    )
  }
}

export default App
```

## 使用state值

采用 ```this.state.stateName```的形式来在JSX代码中使用，见上面的```{this.state.count}```这一句。

## state 变，render，就会自动重新执行

render里面都是标签代码，render 重新执行，类似于我们动手刷新了页面，但是，整个页面不会被刷新，而刷新的只是当前组件。

每次我们在事件响应函数（handleClick）中修改了state值（采用setState方法），render函数都会自动重新执行，于是网页中，我们就会看到更新后的结果了。

注：setState 英文本意是：设置状态。Raeact组件中，修改state值，必须通过setState（）来完成。

## state 的只读性

一个要特别注意的点，就是上面

```
this.setState({
  count: this.state.count + 1
})
```
不能写成

```
this.state.count++
```

直接修改state 值本身是不允许的。

## 视频

* state
