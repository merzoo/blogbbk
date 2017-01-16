---
title: 浅谈URI和URL及URN的区别和联系
date: 2016-06-13 13:18:03
tags:
---
对于URL,大家都比较熟悉，其他两个词就比较陌生了。URI、URL和URN是识别、定位和命名互联网上的资源的标准途径。1989年Tim Berners-Lee发明了互联网（World Wide Web）。WWW被认为是全球互连的实际的和抽象的资源的集合–它按需求提供信息实体–通过互联网访问。实际的资源的范围从文件到人，抽象的资源包括数据库查询。

因为要通过多样的方式识别资源（人的名字可能相同，然而计算机文件只能通过唯一的路径名称组合访问），所以需要标准的识别WWW资源的途径。为了满足这种需要，Tim Berners-Lee引入了标准的识别、定位和命名的途径：URI、URL和URN。

- URI：Uniform Resource Identifier，统一资源标识符；
- URL：Uniform Resource Locator，统一资源定位符；
- URN：Uniform Resource Name，统一资源名称。

在这个体系中的URI、URL和URN是彼此关联的。URI的范畴位于体系的顶层，URL和URN的范畴位于体系的底层。这种排列显示URL和URN都是URI的子范畴。

![image](http://www.biaodianfu.com/wp-content/uploads/2011/02/url-uri-urn-relationship.jpg)

三者中，其中URL和URI特别容易混淆。

**URL**是Internet上用来描述信息资源的字符串，主要用在各种WWW客户程序和服务器程序上。采用URL可以用一种统一的格式来描述各种信息资源，包括文件、服务器的地址和目录等。

**URL**的格式由下列三部分组成：

1. 协议（或称为服务方式）；
2. 存有该资源的主机IP地址（有时也包括端口号）；
3. 主机资源的具体地址。如目录和文件名等。

第一部分和第二部分之间用”：//”符号隔开，第二部分和第三部分用”/”符号隔开。第一部分和第二部分是不可缺少的，第三部分有时可以省略。
目前最大的缺点是当信息资源的存放地点发生变化时，必须对URL作相应的改变。因此人们正在研究新的信息资源表示方法。

**URI**是以某种统一的（标准化的）方式标识资源的简单字符串，一般由三部分组成：

1. 访问资源的命名机制。
2. 存放资源的主机名。
3. 资源自身的名称，由路径表示。

典型情况下，这种字符串以scheme开头，语法如下：
```
[scheme:] scheme-specific-part
```
*http://www.google.com，其中http是scheme，//www.google.com是 scheme-specific-part，并且它的scheme与scheme-specific-part被冒号分开了。*

有的URI指向一个资源的内部。这种URI以”#”结束，并跟着一个anchor标志符（称为片断标志符）。
相对URI不包含任何命名规范信息。它的路径通常指同一台机器上的资源。相对URI可能含有相对路径（如：“..”表示上一层路径），还可以包含片断标志符。
