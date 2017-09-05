---
layout: post
title:  "浮动元素脱离文档流的表现"
date:   2017-09-05 22:50:22 +0800
categories: jekyll update
---

代码

```html
<style>
    .box{
        width: 50px;
        height: 50px;
    }
    .box-up{
        background: blue;
    }
    .float-box{
        float: left;
        width: 500px;
        height: 200px;
        border: 1px solid red;
        background: rgba(255, 0, 0, 0.2);
    }
    .box-down{
        background: green;
    }
</style>

<div class="box-up box">up</div>
<div class="float-box"></div>
<span>this is a text</span>
<div class="box-down box">down</div>
```

在chrome在的表现

![](/assets/images/2017-09-05/float-layout.jpg)

表现1：浮动元素只影响其在文档流下面的元素，其上面的元素不受影响，如`box-up`

表现2：浮动元素只影响块级元素，行内元素不受影响，如`span`,可以看到`box-down`里面的文字也不受影响。

>有人会问为什么`box-down`不顶到`float-box`上边线呢？

这是因为`box-down`和`span`还在文档流中，所以`box-down`会另起一行，在`span`的下面。