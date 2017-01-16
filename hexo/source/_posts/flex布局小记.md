---
title: flex布局小记
date: 2016-11-16 14:35:40
tags:
---
> 最近一直在做移动端h5的页面，用的了大量的flex布局。遂整理整理几个常见的用法作为一篇笔记博文发出。

![image](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071002.png)

# 什么是flex布局

- flex布局由w3c组织于2009年提出，旨在解决传统盒子模型布局中的多种局限性，提高布局的简洁性和便利性。
- flex布局可以十分便利的构建响应式的页面。
- 目前绝大部分现代浏览器已经可以支持，移动端浏览器全面支持。

# 怎么使用flex布局


```
<div id="parent">
    <p class="child1">1</p>
    <div class="child2">2</div>
    <h3 class="child3">3</h3>
</div>
```
以示例结构为例，我们分别来实现以下5种常见布局（注释纯属偷懒）：
- 水平排列

```
#parent{
    display: flex; //关键代码
}
```

- 水平居中排列

```
#parent{
    display: flex; //关键代码
    justify-content: center; //水平居中代码
}
```

- 垂直排列

```
#parent{
    display: flex; //关键代码
    flex-direction: column; //纵向排布
}
```
- 垂直居中排列

```
#parent{
    display: flex; //关键代码
    flex-direction: column; //纵向排布
    align-items: center; //垂直居中代码
}
```
- 垂直水平居中排列

```
#parent{
    display: flex; //关键代码
    justify-content: center; //水平居中代码
    align-items: center; //垂直居中代码
}
```

- 两端固定宽度，中间自适应（圣杯布局）

```
#parent{
    display: flex; //关键代码
}
.child1{
    width:30px;
    height:50px;
}
.child2{
    flex: 1;    // 等同于flex:1 1 0%;
    height:50px;
}
.child3{
    width:40px;
    height:50px;
}
```

---

未完待续...
