---
layout: layouts/post.njk
title: 给个人博客网站添加pjax最简单的代码，以帝国cms/Typecho为例
description: 我的个人博客之前使用的cms是帝国cms，经过一番折腾发现了一种最最简单的方法给给个人博客网站添加pjax，这不又换Typecho，继续给网站加上pjax。最简单的代码当然要分享出来。演示地址：本站最...
date: 2024-04-13
---

<p>我的个人博客之前使用的cms是帝国cms，经过一番折腾发现了一种最最简单的方法给给个人博客网站添加pjax，这不又换Typecho，继续给网站加上pjax。<br>最简单的代码当然要分享出来。<br>演示地址：本站</p><p>最简单的代码当然要分享出来。<br>演示地址：<a href="https://www.zhengcaiyang.com/">拂晓梦话</a>（本站）<br>代码如下：</p><pre><code>&lt;!--引入文件--&gt;

&lt;script src=&quot;http://cdn.bootcss.com/jquery.pjax/1.9.5/jquery.pjax.min.js&quot;&gt;&lt;/script&gt;
&lt;script&gt;
var pjax = new Pjax({
  // 在页面进行 PJAX 时需要被替换的元素或容器，一条一个 CSS 选择器，数组形式
  selectors: [
    &quot;title&quot;,
    &quot;meta[name=keywords]&quot;,
    &quot;meta[name=description]&quot;,
    &quot;main&quot;,   //main表示执行pjax后会发生变化的id，改成你主题的内容主体id或class。 
  ],
  cacheBust: false
})
&lt;/script&gt;

</code></pre>