### fed-e-task-03-02 简答题
1. 第一题
```
答
1. new Vue  执行其原型上的_init方法
2. this._init 顺序执行 
 2.1 合并options  
 2.2 添加 _renderProxy属性
 2.3 初始化组件生命周期
 2.4 初始化组件实例事件
 2.5 初始化渲染相关  $nextTick  _render
 2.6 执行beforeCreate钩子
 2.7 初始化注入inject
 2.8 初始化 state相关 props methods data computed watch   等等
 2.9 初始化 provider 
 2.10 执行created钩子
 2.11 执行 $mount 方法
  2.11.1 判断如果是否有render 函数  如果无是否有template模板 执行对应操作
  2.11.2 执行 beforeMount 钩子
  2.11.3 针对主件实例添加监听器 监听器执行完后执行实例update方法
  2.11.4 执行组件的mounted钩子
```

2. 第二题

```
答 
1. 通过 Object.defineProperty 劫持每一个data属性
2. 给每一个属性创建一个dep
3. 通过get触发 dep收集 使用该属性的 watcher
4. 沟通set触发 dep的notify 触发对应的watcher 执行update方法；
5. watcher对应的update中会调用相关方法： vue实例的 _update， watch 和计算属性相关的 方法指性； 
```

3. 第三题

```
答
作用： 标识节点在当前层级的唯一性
好处： 便于复用节点 降低创建销毁节点成本 从而在一定程度上提高性能
```


4. 第四题

```
答： 
1. 将html模板字符串编译为对应的ast (报告标签名称,属性,事件, 子节点, 文本相关指令等等);
2. 优化ast 标记其中的 静态节点和 静态根节点 便于后期虚拟dom diff的时候跳过这些节点的更新 从而提升性能；
3. 使用优化过的ast生成js代码 包括 render函数 和statisRenderFns函数
```