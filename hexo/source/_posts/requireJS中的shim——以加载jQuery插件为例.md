---
title: requireJS中的shim——以加载jQuery插件为例
date: 2016-03-28 17:17:59
tags:
     - 前端工程
---
最近玩了玩requireJS。没有requireJS框架之前，如果我们想使用jquery框架，会在HTML页面中通过`script`标签加载，这个时候jquery框架生成全局变量$和jQuery等全局变量。如果项目中引用了requireJS框架，采用模块化的方式加载jquery，那么jquery不会再添加全局变量$和 jQuery 。现在问题来了，虽然jquery框架已经开始支持AMD规范，但是jquery的众多插件还是不支持AMD，仍然像以前一样需要使用全局变量$。jquery插件大多都是如下结构：

```
(function( $, undefined ) {

})( jQuery );
```
 如果我们项目中使用了jquery插件，但是jquery框架是通过requireJS加载的（不会添加全局变量$），那怎么完成jquery插件的加载呢？使用传统的方，在HTML页面中通过`script`加载jquery插件，肯定是不行的。这个时候我们需要使用到requireJS的shim参数，来完成jquery插件的加载。下面我们以加载jquery-ui的slider插件为例：

```
requirejs.config({
  shim: {
  'jquery.ui.core': ['jquery'],
  'jquery.ui.widget': ['jquery'],
  'jquery.ui.mouse': ['jquery'],
  'jquery.ui.slider':['jquery']
    },
  paths : {
    jquery : 'jquery-2.1.1/jquery',
    domReady : 'require-2.1.11/domReady',
    'jquery.ui.core' : 'jquery-ui-1.10.4/development-bundle/ui/jquery.ui.core',
    'jquery.ui.widget' : 'jquery-ui-1.10.4/development-bundle/ui/jquery.ui.widget',
    'jquery.ui.mouse' : 'jquery-ui-1.10.4/development-bundle/ui/jquery.ui.mouse',
    'jquery.ui.slider' : 'jquery-ui-1.10.4/development-bundle/ui/jquery.ui.slider'
  }
});
```
使用的时候：

```
require([ 'jquery', 'domReady','jquery.ui.core','jquery.ui.widget','jquery.ui.mouse','jquery.ui.slider'],
    function($) {

      $("#slider" ).slider({
           value:0,
           min: 0,
           max: 4,
           step: 1,
           slide: function( event, ui ) {}    
      });      

    });
```

这样就完美解决了不支持amd规范的插件配置啦。
