# Note

## 1. 两种不同组件
尽量使用受控组件，更符合 react 风格。
#### (1) 受控组件
只操纵state 不操纵DOM

#### (2) 非受控组件
操纵 DOM

## 2. 生命周期

#### (1) 生命周期图
![生命周期](https://blogname.github.io/img/ajs-life.png)

#### (2) 一些说明
初始化阶段:<br>
componentWillMount() - 将要挂载， 挂载即放置到页面中的过程 <br>
render之后， 做componentDidMount() - 即进行挂载<br>

销毁阶段:<br>
手动掉用 unmountComponentAtNode() 可以移除组件，如果调用了这个方法
在真正移除之前，react会先调用 componentWillUnmount(), 如果有一些内存需要释放，定时器需要释放，在这个函数进行


#### (3) 总结
初始化
```
constructor
componentWillMount
render
componentDidMount
```
更新组件
```
setState
componentWillUpdate
componentDidUpdate
```
移除组件
```
componentWillUnmount
unmountComponentAtNode
```

有些没用到的方法用到了再更新

## 3. Virtual DOM 与 DOM Diff

提升界面更新效率 <br>

初始化：创建虚拟dom树 -> 真实dom树 -> 绘制 <br>

更新：setState()更新 -> 重新创建虚拟dom树 -> 新/旧比较 -> 更新差异对应的DOM -> 局部界面重绘 <br>


