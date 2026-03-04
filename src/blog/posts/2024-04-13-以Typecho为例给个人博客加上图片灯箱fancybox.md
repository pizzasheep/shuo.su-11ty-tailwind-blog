---
layout: layouts/post.njk
title: 以Typecho为例给个人博客加上图片灯箱fancybox
description: 原理：将fancybox的js和css引入你个人博客需要开启灯箱的页面，一般是文章页面，同时给文章页面的img标签加上a标签，这样就完成了图片灯箱的部署。当然fancybox官网还有关于PDF，MP4...
date: 2024-04-13
---

<p>原理：将fancybox的js和css引入你个人博客需要开启灯箱的页面，一般是文章页面，同时给文章页面的img标签加上a标签，这样就完成了图片灯箱的部署。当然fancybox官网还有关于PDF，MP4等进阶的适配方法，喜欢摄影、网站需要开启图片灯箱的和喜欢折腾的个人博客站长可以行动起来了。</p><p>演示如下：</p><pre><code>[一张耐看的草地桃心壁纸][1]
</code></pre><p>代码如下：<br>在内容模板头部加上</p><pre><code>&lt;link rel=&quot;stylesheet&quot; href=&quot;https://cdn.jsdelivr.net/npm/@fancyapps/ui/dist/fancybox.css&quot;/&gt;
</code></pre><p>在内容模板尾部加上</p><pre><code>&lt;script src=&quot;https://cdn.jsdelivr.net/npm/@fancyapps/ui@4.0/dist/fancybox.umd.js&quot;&gt;&lt;/script&gt;

&lt;script&gt;
$(function () {
        $('.content').find('img').each(function () {
                var _this = $(this);
                var _src = _this.attr(&quot;src&quot;);
                var _alt = _this.attr(&quot;alt&quot;);
                _this.wrap('&lt;a data-fancybox=&quot;images&quot; href=&quot;' + _src + '&quot; data-caption=&quot;' + _alt + '&quot;&gt;&lt;/a&gt;');
        })
})
&lt;/script&gt;

</code></pre>