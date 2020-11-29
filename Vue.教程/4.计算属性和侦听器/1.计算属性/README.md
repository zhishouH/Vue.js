#### 计算属性

##### 基础例子

```
<div id="app">
  {{message}}
  <br>
  {{reversedMessage}}
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      message: 'HELLO'
    },
    computed: {
      reversedMessage: function () {
        return this.message.split('').reverse().join('')
      }
    }
  })
</script>
```

```
HELLO
OLLEH
```



##### 计算属性缓存vs方法

##### 计算属性vs侦听属性

##### 计算属性的setter