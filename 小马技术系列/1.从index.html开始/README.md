## 从index.html开始 
- html5文档
- vue.js引入
- vue对象

> index.html
- 从第一个index.html开始

> vue.js引用
- `<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>`

> html代码块
```
<div id="myApp">
  {{message}}
</div>
```
> javascript脚本部分
```
var myApp = new vue({
  el:'#myApp',
  data: {
    message: 'hello vue.js world!'
  }
})
```

>完整代码
```
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>从index.html开始</title>
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</head>

<body>
  <div id="myApp">
    {{message}}
  </div>

  <script>
    var myApp = new Vue({
      el: '#myApp',
      data: {
        message: 'hello vue.js world!'
      }
    })
  </script>
</body>

</html>
```