#### 介绍

##### 起步

直接用`<script>`引入

```
<!-- 开发环境版本，包含了有帮助的命令行警告 -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

```
<!-- 生产环境版本，优化了尺寸和速度 -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```



##### 声明式渲染

1.第一个`vue`应用

```
<div id="app">
  {{message}}
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      message: 'hello world!'
    }
  })
</script>
```

```
hello world!
```

2.`v-bind`指令，绑定元素 attribute

```
<div id="app">
  <span v-bind:title="message">
    鼠标悬停几秒钟查看此处动态绑定的提示信息！
  </span>
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      message: '页面加载于.' + new Date().toLocaleString()
    }
  })
</script>
```

```
鼠标悬停几秒钟查看此处动态绑定的提示信息！
```



##### 条件与循环

1.`v-if`指令，条件

```
<div id="app">
  <p v-if="seen">你现在看到我了！</p>
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      seen: true
    }
  })
</script>
```

```
你现在看到我了！
```

2.`v-for`指令，循环

```
<div id="app">
  <ol>
    <li v-for="todo in todos">
      {{todo.text}}
    </li>
  </ol>
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      todos: [
        { text: '学习JavaScript' },
        { text: '学习Vue' },
        { text: '整个项目' }
      ]
    }    
  })
</script>
```

```
1.学习JavaScript
2.学习Vue
3.整个项目
```



##### 处理用户输入

1.`v-on` 指令，添加一个事件监听器

```
<div id="app">
  <p>{{message}}</p>
  <button v-on:click="reverseMessage">反转文本</button>
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      message: 'Hello World!'
    },
    methods: {
      reverseMessage: function () {
        this.message = this.message.split('').reverse().join('')
      }
    }
  })
</script>
```

```
Hello World!
`反转文本`  // button 按钮
```

2.`v-model`指令，实现表单输入和应用状态之间的双向绑定

```
div id="app">
  <p>{{message}}</p>
  <input v-model="message">
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      message: 'Hello World!'
    }
  })
</script>
```

```
Hello World!
`Hello World!` // input 文本框
```



##### 组件化应用构建

1.注册组件

```
<div id="app">
  <ol>
    <todo-item></todo-item>
    <todo-item></todo-item>
  </ol>
 </div>

<script>
  Vue.component('todo-item', {
    template: '<li>Talk is cheap. Show me the code.</li>'
  })
  var app = new Vue({
    el: '#app'
  })
</script>
```

```
1.Talk is cheap. Show me the code.
2.Talk is cheap. Show me the code.
```

2.`prop`

```
<div id="app">
  <ol>
    <todo-item v-for="item in groceryList" v-bind:todo="item" v-bind:key="item.id"></todo-item>
  </ol>
</div>

<script>
  Vue.component('todo-item', {
    props: ['todo'],
    template: '<li>{{todo.text}}</li>'
  })
  var app = new Vue({
    el: '#app',
    data: {
      groceryList: [
        { id: 0, text: '蔬菜' },
        { id: 1, text: '奶酪' },
		{ id: 2, text: '随便其它什么人吃的东西' }
	  ]
	}
  })
</script>
```

```
1.蔬菜
2.奶酪
3.随便其它什么人吃的东西
```

