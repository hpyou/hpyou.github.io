---
layout: post
title:  "脱离文档流的元素有哪些特征"
date:   2017-09-03 06:46:22 +0800
categories: jekyll update
---

## 如何脱离文档流
- float
- position -> absolute \ fixed

## 脱离文档流后元素的变化

- 行内元素可以设置宽高

- 块级元素width无法默认100%，而是由内容撑开

- margin对元素依旧有效

```html
<style>
.box{
    position: relative;
    width: 400px;
    height: 400px;
    background: #ddd;
}
.popup{
    position: absolute;
    width: 50px;
    height: 50px;
    margin: auto;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    background: blue;
}
.block{
    float: left;
    margin-top: 20px;
    margin-left: 20px;
    background: green;
}
.inline{
    float: left;
    width: 50px;
    height: 50px;
    margin-top: 10px;
    margin-left: 20px;
    background: rebeccapurple;
}
</style>
<div class='box'>
    <span class="inline">inline</span>
    <div class="block">block</div>
    <div class='popup'>popup</div>
</div>

```
![脱离文档流](/assets/images/2017-09-03/out-of-document-flow.jpg "脱离文档流")

> 需要注意的是绝对定位元素在设了`left`后，才能设`margin-left`,同理设了`right`后才能设`margin-right`

以上这些特征基本和把元素设成inline-block的特性一样