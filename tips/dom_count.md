# 打开一个页面，我想知道这个页面有多少dom节点

emmmmmmmmmmmmmmmmmmmmmmmmmmmm

```js
document.querySelectorAll('*').length;
// ..
```

拜拜～

修的麻袋，那我再问一个，求一个dom节点下的所有子孙节点...

```js
x.querySelectorAll('*').length;
// ...
```

如果不是dom树，是其他树呢...

![rua](https://github.com/shiyangzhaoa/easy-tips/blob/master/img/rua.jpg)

```js
const getChildren = (node) => {
  return Array.from(node.children).reduce((acc, cur) => cur.children.length
    ? acc.concat(cur, getChildren(cur))
    : acc.concat(cur)
    , []);
}
```

我们来使用上面的方法求页面的dom节点数:

![biu](https://github.com/shiyangzhaoa/easy-tips/blob/master/img/dom_count.jpg)

哎嘿嘿，是不是觉得这样就有趣多了～