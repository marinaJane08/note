#全局配置
@(启动前)[配置]
###**Vue.config**对象属性
- **silent**：取消日志与警告
- **optionMergeStrategies**：父组件传值到子组件（props）
- **devtools**：是vue的开发工具，主要用于错误跟踪等
- **errorHandler**：捕获在vue生命周期或计算属性中的错误，*console.error*只会抛出error对象，因此在error对象是undefined时不会报错
- **warnHandler**：与上面相似，屏蔽警告
- **ignoredElements**：不进行解析的标签列表，注意使用*kebab-case*书写，可使用正则表达式
- **keyCodes**：键盘代码的别名，使用*kebab-case*书写
- **performance**：浏览器调试选项
- **productionTip**：取消生产提示

---

#全局API
@(Vue)[vm]
- **extend**：定义组件，data必须是个返回*对象*的*函数*
- **nextTick**：vue异步更新组件后调用的方法，可使用promise方式定义
- **set**：对vue无法监听的数据进行更新，不能对vue实例或根数据对象进行此操作
- **delete**：对vue无法监听的数据进行删除
- **directive**：定义或返回指令对象，第二位参数是函数时，只会在bind/update时调用
- **filter**：定义或返回指令对象
- **component**：定义组件，传入`id`和`extend返回的对象/自定义选项`，返回构造器
- **use**：传入定义了install方法或一个函数的plugin，同一插件只会安装一次
- **mixin**：混入
- **compile**：（在独立构建组件时）编译
- **version**：返回vue版本号

---

#数据选项
@[vm]
- **data**：`$data`访问，特殊命名如`_variable`在`$data._property访问`，胖箭头会使vue绑定的上下文失效
- **props**：子组件接收父组件的传值
- **propsData**：子组件自定义该值
- **computed**：计算属性，在`依赖`的`响应式`属性发生变化时会同时更新
- **methods**：定义vm方法
- **watch**：`$watch`访问

---

#DOM选项
- **el**：`new实例`中，用于实例挂载，手动调用`vm.$mount()`，无`render函数`和`template属性`时，提取`el`里面的HTML作为模板
- **template**：`el`中无`分发插槽`时将替换全部内容，使用`#`引用在页面中定义的`<script type="x-template">`，优先级低于`render函数`
- **render**：使用`h(createElement)`函数创建`VNode`，`函数组件`将多接收`context`参数
- **renderError**：返回`render函数`出错时的备用`VNode`，接收`error`参数

---

#生命周期钩子选项
>*  实例初始化
*   beforeCreate
*   数据观测`data observer`
*   event/watcher
*   created（无$el，未挂载）
*   beforeMount、render函数调用（服务器端渲染不调用）
*   mounted、root实例挂载（服务器端渲染不调用），`$nextTick`包含所有子组件视图渲染（服务器端渲染不调用）
*   updated非完整更新（服务器端渲染不调用）
*   activated激活了keep-alive组件（服务器端渲染不调用）
*   deactivated停用了keep-alive组件（服务器端渲染不调用）
*   beforeDestroy实例即将销毁前（服务器端渲染不调用）
*   destroyed实例、子实例销毁（服务器端渲染不调用）
*   errorCaptured接收`error`、vm、信息，返回false可阻止向上传播

---

#资源选项
- **directives**：自定义指令

---

>##错误传播规则
*   实例中的errorCaptured逐一唤起到errorHandler
*   新错误
*   false时阻止传播

- 路由
    - router({routes:[path:,name:,redirect:,component:,children:,（嵌套路由）]})
    - `router-link to= `（跳转）
    - `router-view`（显示）