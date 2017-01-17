---
title: 学习Javascript闭包（Closure）所感
date: 2016-03-13 22:14:17
tags:
     - JavaScript
---
> 接触编程时间不久，闭包这个问题也困扰了我许久。曾百度google之后无果，解释大多晦涩难懂。随着阅读的增加，对闭包也有了一些自己的较为清晰的理解。**所谓的闭包：通俗的说就是能够读取其他函数内部变量的函数**。

#### 闭包的作用
1. 读取其他函数内部变量。
2. 将变量存储在内存之中，防止js的垃圾回收机制。
3. 方便传参。
4. 形成“块级作用域”显示和隐藏一些变量，减少全局变量。

#### 闭包的影响：
1. 内存溢出。由于阻止了变量的垃圾回收，使得变量长期存在于内存之中，性能下降，可能会导致内存溢出！
2. 闭包会在父函数外部，改变父函数内部变量的值。如果你把父函数当作对象（object）使用，把闭包当作它的公用方法（Public Method），把内部变量当作它的私有属性（private value），这时一定要小心，不要随便改变父函数内部变量的值。

#### 关于闭包的思考题：
两道闭包的思考题，由输出的结果加深一下对闭包的理解.

eg.1

```
var name = "The Window";
var object = {
　　name : "My Object",
　　getNameFunc : function(){
　　　　return function(){
　　　　　　return this.name;
　　　　};
　　}
};
alert(object.getNameFunc()());
```
eg.2
```
var name = "The Window";
var object = {
    name : "My Object",
    getNameFunc : function(){
        var that = this;
        return function(){
            return that.name;
        };
    }
};
alert(object.getNameFunc()());
```
