---
layout: post
title:  "垂直居中的几个写法"
date:   2017-09-05 23:50:22 +0800
categories: jekyll update
---

## 父元素定高

代码

```html
<style>
    .block-fix-height{
        width: 500px;
        height: 200px;
        border: 1px solid red;
        font-size: 0;
    }
    .block-fix-height:before{
        content: '';
        height: 100%;
        display: inline-block;
        vertical-align: middle;
    }
    .box1{
        width: 50px;
        height: 50px;
        background: green;
        display: inline-block;
        vertical-align: middle;
    }
    .box2{
        width: 150px;
        height: 150px;
        background: green;
        display: inline-block;
        vertical-align: middle;
    }
    img{
        vertical-align: middle;
    }
    span{
        font-size: 14px;
        vertical-align: middle;
    }
</style>
<div class="block-fix-height">
    <div class="box1"></div>
    <img src="images/dog.jpg" alt="">
    <div class="box2"></div>
    <span>this is a text</span>
</div>
```

表现

![](/assets/images/2017-09-05/fix-height.png)

说明1：父元素`font-size: 0`是为了消除chrome带来的间距

说明2：父元素的伪类设置成`inline-block`，并且高度为`100%`

说明3：所有要居中的元素设置`vertical-align: middle`


## 父元素不定高

把上面的例子中的父元素换成

```html
.block-no-height{
    width: 500px;
    border: 1px solid red;
    font-size: 0;
}
```

这样的父元素就不需要写伪类

表现

![](/assets/images/2017-09-05/no-height.png)

> 总结

只要子元素中有跟父元素一样高度的元素，并都设置了`vertical-align: middle`，都可以实现居中，如果没有就要造一个。


