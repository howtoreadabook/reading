---
title: 资源
layout: page
comments: yes
---
<nav>
          <span><a title="首页" class="" href="/">首页</a></span>
          <span><a title="资源" class="" href="/resourse/">资源</a></span>
          <span><a title="贡献" class="" href="/team/">贡献</a></span>
          <span><a title="版权" class="" href="/copyright/">版权</a></span>
          <span><a title="联系" class="" href="/contract/">联系</a></span>
        <!--  <span><a title="分类" class="" href="/categories/">分类</a></span>
          <span><a title="标签" class="" href="/tags/">标签</a></span> -->
        </nav>
<div id='tag_cloud'>
{% for cat in site.categories %}
<a href="#{{ cat[0] }}" title="{{ cat[0] }}" rel="{{ cat[1].size }}">{{ cat[0] }} ({{ cat[1].size }})</a>
{% endfor %}
</div>

<ul class="listing2">
{% for cat in site.categories %}
  <li class="listing-seperator" id="{{ cat[0] }}">{{ cat[0] }}</li>
{% for post in cat[1] %}
  <li class="listing-item">
  <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
  <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
{% endfor %}
</ul>

<script src="/media/js/jquery.tagcloud.js" type="text/javascript" charset="utf-8"></script> 
<script language="javascript">
$.fn.tagcloud.defaults = {
    size: {start: 1, end: 1, unit: 'em'},
      color: {start: '#f8e0e6', end: '#ff3333'}
};

$(function () {
    $('#tag_cloud a').tagcloud();
});
</script>


<!--[![新浪微博](http://service.t.sina.com.cn/widget/qmd/{{ site.weibo }}/f78fbcd2/1.png)](http://weibo.com/u/{{ site.weibo }})-->
