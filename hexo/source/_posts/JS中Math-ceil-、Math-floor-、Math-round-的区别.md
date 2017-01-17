---
title: JS中Math.ceil() 、Math.floor() 、Math.round()的区别
date: 2016-04-18 18:05:06
tags:
     - JavaScript
---
> 在工作中经常会使用到Math.ceil() 、Math.floor()和Math.round()这三个函数，并且经常记不清楚产生混淆，这次通过JavaScript: The Definitive Guide, 4th Edition对这三个函数的原型定义的理解，彻底厘清三者的区别。

##### 话不多说，先来一波官方定义：
- **Math.ceil()**
    - round a number ==up==  
    - Arguments: Any numeric value or expression
    - Returns: The closest integer greater than or equal to x.

- **Math.floor()**
     - round a number ==down==
     - Arguments: Any numeric value or expression
     - Returns: The closest integer less than or equal to x.

- **Math.round()**
    - round to the nearest ==integer==
    - Arguments: Any number.
    - Returns: The integer closest to x.


##### 总而言之：
~~~~
1. Math.ceil()用作向上取整。
2. Math.floor()用作向下取整。
3. Math.round() 我们数学中常用到的四舍五入取整。
