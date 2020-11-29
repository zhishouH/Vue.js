#### 侦听器

```
<div id="app">
  <p>是否询问问题：
    <input v-model="question">
  </p>
  <p>{{awswer}}</p>
</div>

<script>
  var app = new Vue({
    el: '#app',
    data: {
      question: 'a',
      awswer: '你的问题是？'
    },
    watch: {
      question: function (newQuestion, oldQuestion) {
        console.log(newQuestion, oldQuestion)
        this.awswer = '好的！'
      }
    }
  })
</script>
```

