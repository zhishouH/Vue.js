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

```
<div id="app">
  {{message}}
  <br>
  {{now}}
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      message: 'lala'
    },
    computed: {
      now: function () {
        return Date.now()
      }
    }
  })
```



##### 计算属性vs侦听属性

1.侦听属性

```
<div id="app">
  {{ fullName }}
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      firstName: 'Foo',
      lastName: 'Bar',
      fullName: 'Foo Bar'
    },
    watch: {
      firstName: function (val) {
        this.fullName = val + ' ' + this.lastName
      },
      lastName: function (val) {
        this.fullName = this.firstName + ' ' + val
      }
    }
  })
</script>
```

2.计算属性

```
<div id="app">
  {{fullName}}
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      firstName: 'Foo',
      lastName: 'Bar'
    },
    computed: {
      fullName: function () {
        return this.firstName + ' ' + this.lastName
      }
    }
  })
</script>
```



##### 计算属性的setter

```
<div id="app">
  {{fullName}}
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      firstName: 'Foo',
      lastName: 'Bar'
    },
    computed: {
      fullName: {
        // getter
        get: function () {
          return this.lastName + ' ' + this.firstName
        },
        // setter
        set: function (newValue) {
          var names = newValue.split(' ')
          this.firstName = names[0]
          this.lastName = names[names.length - 1]
        }
      }
    }
  })
```

