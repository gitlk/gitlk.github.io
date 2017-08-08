---
title: About
permalink: /about/
---
<header class="bloghead">
    <h1 class="bloghead-title">
    <a href="{{ site.url }}/">{{ site.name }}<span>&#39;s blog</span></a>
  </h1>
    <nav class="bloghead-nav">
        {% for nav in site.nav %}
        <a href="{{ nav.href }}">{{ nav.name }}<span> &nbsp;/&nbsp; </span></a> {% endfor %}
    </nav>
</header>
<p class="heavy-title">
	个人博客，用于管理个人学习心得及笔记，简历等使用。如有疑问请联系邮箱：913887798@qq.com
</p>

