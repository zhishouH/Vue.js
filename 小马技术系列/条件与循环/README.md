## 条件与循环
- v-if
- v-for

> v-if
- 条件判断式，根据表达式的真伪进行页面处理
- html:
```
<p v-if="seen">"快看我！"</p>
```

> v-for
- 处理数组循环，将数据循环显示到页面上
- html:
```
<ol>
  <li v-for="game in games">
    {{game.title}}
  </li>
</ol>
```

>综合例
- html
```
<div id="myApp">
  <h3>游戏列表</h3>
  <div v-if="seen">2020最新：</div>
  <ol>
    <li v-for="game in games">
      {{game.title}} / {{game.price}}元
    </li>
  </ol>
</div>
```