---
title: null和undefined的区别
date: 2016-06-20 16:51:29
tags:
     - JavaScript
---
> 目前来说，null和undefined是基本同义的，只有一些细微差别。

**null表示“没有对象”，即该处不应该有值。**
典型用法是：
1. 作为函数的参数，表示该函数的参数不是对象。
2. 作为原型链的终点。

```
Object.getPrototypeOf(Object.getPrototypeOf)  //null
```

**undefined表示“缺少值”，就是此处应该有一个值，但是还没有定义。** 典型用法是:
1. 变量被声明了，但是没有赋值，就等于undefined。
2. 调用函数时，应该提供的参数没有提供，该参数等于undefined。
3. 对象没有赋值的属性，该属性的值为undefined。
4. 函数没有返回值，默认返回undefined。


```
(function(a,b){console.log(b)})(1)  //undefined
```
