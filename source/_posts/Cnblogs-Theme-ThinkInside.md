---
title: Cnblogs-Theme-ThinkInside
date: 2019-12-04 09:22:35
tags:
   - Blog
categories:
   - Blog
toc: true
---

## 博客园样式 DIY
 博客样式 diy 主要是争对不同皮肤页面标签，通过修改 css/js 来自定义自己喜欢的样式；

###  选择主题（博客皮肤）
选择皮肤 ThinkInside

### 页面定制CSS代码
```css
#ad_t2,#under_post_news,#under_post_kb,#HistoryToday,#ad_c1,#ad_c2{
    display: none;
}
#header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 2;
    background-color: #3f3f3f;
    -webkit-box-shadow: 0 0 10px #333;
    -moz-box-shadow: 0 0 10px #333;
    box-shadow: 0 0 10px #333;
}
#navList {
    list-style: none outside none;
    display: block;
    float: right;
    left: 0;
    right: 0;
    margin: 0 30px 0 0;
    position: relative;
    font-size: large;
}
.blogStats {
    float: inherit;
    color: #0088CC;
    margin-top: 8px;
    margin-right: 2px;
    text-align: right;
    padding: 0;
    display: none;
}
body {
    font-family:"Comic Sans MS","微软雅黑";
}
#cnblogs_post_body h2 {
    border-left-style: solid;
    border-left-width: thick;
    border-left-color: #179ede;
    margin-left: 20px;
    padding-left: 20px;
    color: #0085c7;
}
.post {
    background-color: #ffffff;
}
#cnblogs_post_body p>img {
    -webkit-box-shadow: 0 0 20px 5px #dadada;
    -moz-box-shadow: 0 0 20px 5px #dadada;
    box-shadow: 0 0 20px 5px #dadada;
    margin: 20px;
}
#tbCommentBody {
    width: 95%;
    height: 100px;
}


/*
 代码高亮开始，使用了一个叫Monokai Sublime的黑色主题皮肤，直接拿过来还不行，有一些样式冲突，还要自己稍微改一些地方
Monokai Sublime style. Derived from Monokai by noformnocontent http://nn.mit-license.org/
*/
pre {
/*控制代码不换行*/
    white-space: pre;
    word-wrap: normal;
}
.cnblogs-markdown .hljs {
    font-family:"Comic Sans MS","微软雅黑";
    display: block;
    overflow-x: auto;
    padding: 0.5em;
    background: #23241f !important;
    color: #FFF;
    white-space: pre;
    word-break: normal;
}

.hljs,
.hljs-tag,
.hljs-subst {
  color: #f8f8f2;
}

.hljs-strong,
.hljs-emphasis {
  color: #a8a8a2;
}

.hljs-bullet,
.hljs-quote,
.hljs-number,
.hljs-regexp,
.hljs-literal,
.hljs-link {
  color: #ae81ff;
}

.hljs-code,
.hljs-title,
.hljs-section,
.hljs-selector-class {
  color: #a6e22e;
}

.hljs-strong {
  font-weight: bold;
}

.hljs-emphasis {
  font-style: italic;
}

.hljs-keyword,
.hljs-selector-tag,
.hljs-name,
.hljs-attr {
  color: #f92672;
}

.hljs-symbol,
.hljs-attribute {
  color: #66d9ef;
}

.hljs-params,
.hljs-class .hljs-title {
  color: #f8f8f2;
}

.hljs-string,
.hljs-type,
.hljs-built_in,
.hljs-builtin-name,
.hljs-selector-id,
.hljs-selector-attr,
.hljs-selector-pseudo,
.hljs-addition,
.hljs-variable,
.hljs-template-variable {
  color: #e6db74;
}

.hljs-comment,
.hljs-deletion,
.hljs-meta {
  color: #75715e;
}

/*黑色主题皮肤结束*/
.cnblogs-markdown .hljs,.cnblogs-markdown code {
    font-family:"Comic Sans MS","微软雅黑"!important;
    font-size: 13px!important;
}
```

### 博客侧边栏公告（支持HTML代码）（支持JS代码）
添加自己的微信二维码
```html
<img src="https://images.cnblogs.com/cnblogs_com/aikaiqiang/1585176/o_wechat_dingyuehao.jpg" alt="Kaywall" class="img_avatar" width="250px"> 
<img src="https://images.cnblogs.com/cnblogs_com/aikaiqiang/1585176/o_WechatIMG2.png" alt="微信" class="img_avatar" width="250px">
```


### 页首Html代码
```html
<a href="https://github.com/aikaiqiang">
<img style="position: absolute; top: 0; left: 0; border: 0" src="https://camo.githubusercontent.com/567c3a48d796e2fc06ea80409cc9dd82bf714434/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f6c6566745f6461726b626c75655f3132313632312e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_left_darkblue_121621.png">
</a>
```

### 页脚Html代码
基于 openwrite 吸粉神器修改：
```html
<script src="https://my.openwrite.cn/js/readmore.js" type="text/javascript"></script>
<script>
    const btw = new BTWPlugin();
    btw.init({
        id: 'cnblogs_post_body',
        blogId: '18438-1574400926959-908',
        name: 'Kaywall 学习之路',
        qrcode: 'https://images.cnblogs.com/cnblogs_com/aikaiqiang/1585176/o_wechat_dingyuehao.jpg',
        keyword: 'kaywall',
    });
</script>
```

