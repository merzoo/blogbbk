---
title: css3硬件加速小记
date: 2017-01-1 16:25:40
tags:
     - 性能优化
---
> 今天做新版的PC页面的时候，用了一些css3的变形动画（主要是一些hover效果），但是发现会出现一些掉帧卡顿的现象。最后通过transform3d开启硬件加速解决了该问题。

#### 默认不会开启GPU加速

一般来说，CSS animations, transforms 以及 transitions 不会自动开启GPU加速，而是由浏览器的缓慢的软件渲染引擎来执行。那我们怎样才可以切换到GPU模式呢，很多浏览器提供了某些触发的CSS规则。
现在，像Chrome, FireFox, Safari, IE9+和最新版本的Opera都支持硬件加速，当它们检测到页面中某个DOM元素应用了某些CSS规则时就会开启，最显著的特征的元素的3D变换。其原理是创建一个新的层，对该层进行硬件加速。

#### 1）用translate: transform3d(0,0,0)开启加速

```
.test-box {
   -webkit-transform: translate3d(0,0,0);
    transform: translate3d(0,0,0);
}
```
#### 2）用transform: translateZ(0)开启加速
适合不需要用到3d变换的场景，用此法可达到欺骗浏览器的效果。

```
.test-box {
   -webkit-transform: translateZ(0);
   -moz-transform: translateZ(0);
   -ms-transform: translateZ(0);
   -o-transform: translateZ(0);
   transform: translateZ(0);
}
```

#### 硬件加速的注意点

- GPU渲染会影响字体的抗锯齿效果。这是因为GPU和CPU具有不同的渲染机制，即使最终硬件加速停止了，文本还是会在动画期间显示得很模糊。
- 不能让每个元素都启用硬件加速，这样会暂用很大的内存，使页面会有很强的卡顿感。
- 避免嵌套太深，会导致父级元素不必要的重绘。
