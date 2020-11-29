#### 模板语法

1.插值

- 文本

  1.“Mustache”语法 (双大括号) 的文本插值

  2.` v-once 指令`,执行一次性地插值，当数据改变时，插值处的内容不会更新

- 原始HTML

  1.`v-html`指令

- Attribute

- 使用JavaScript表达式

  

  插值完整代码：

  ```
  <div id="app">
    <!-- 文本 -->
    <h2>文本</h2>
    <span>Message: {{msg}}</span>
    <br>
    <!-- v-once指令，执行一次性地插值，当数据改变时，插值处的内容不会更新。-->
    <span v-once>这个将不会改变: {{ msg }}</span>
    <br>
    <hr>
  
    <!-- 原始HTML -->
    <h2>原始HTML</h2>
    <!-- v-html指令 -->
    <p>Using mustaches: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    <hr>
  
    <!-- Attribute-特性 -->
    <h2>Attribute-特性</h2>
    <!-- v-bind指令 -->
    <div v-bind:class="color"> test </div>
    <hr>
  
    <!-- 使用 JavaScript 表达式 -->
    <h2>使用 JavaScript 表达式</h2>
    <p>{{number + 1 }}</p>
    <p>{{ok ? 'YES' : 'NO'}}</p>
    <p>{{message.split('').reverse().join('')}}</p>
  </div>
  
  <script>
    var app = new Vue({
      el: '#app',
      data: {
        msg: 'hello zhishouh!',
        rawHtml: '<span style="color:red">this is red</span>',
        color: 'red',
        number: 10,
        ok: true,
        message: 'hello'
      }
    })
  </script>
  <style>
    .red {
      color: red;
    }
  </style>
  ```

  ```
  文本
  Message: hello zhishouh!
  这个将不会改变: hello zhishouh!
  
  原始HTML
  Using mustaches: <span style="color:red">this is red</span>
  Using v-html directive: this is red
  
  Attribute-特性
  test
  
  使用 JavaScript 表达式
  11
  YES
  olleh
  ```

2.指令

- 参数

- 动态参数

- 修饰符

  

  指令完整代码：

  ```
  <div id="app">
    <p v-if="seen">你现在看到我了</p>
    <a v-bind:href="url">我是一个链接</a>
    <div @click="click1">
      <div @click.stop="click2">
        click me
      </div>
    </div>
  </div>
  
  <script>
    var app = new Vue({
      el: '#app',
      data: {
        seen: true,
        url: 'http:www.baidu.com'
      },
      methods: {
        click1: function () {
          console.log('click1...')
        },
        click2: function () {
          console.log('click2...')
        }
      }
    })
  </script>
  ```

  ```
  你现在看到我了
  我是一个链接
  click me
  ```

  

3.缩写

- v-bind缩写

- v-on缩写

  

  缩写完整代码：

  ```
  <div id="app">
    <!-- v-bind指令 -->
    <a v-bind:href="url">这是一个链接</a>
    <br>
    <a :href="url">这是一个链接</a>
  
    <!-- v-on指令 -->
    <p v-on:click="click1">click me</p>
    <p @click="click1">click me</p>
  </div>
  
  <script>
    var app = new Vue({
      el: '#app',
      data: {
        url: 'http:www.baidu.com'
      },
      methods: {
        click1: function () {
          console.log('click1')
        }
      }
    })
  </script>
  ```

  