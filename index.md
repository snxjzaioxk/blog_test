---
layout: default # 假设你有一个名为 default.html 的布局文件
title: 我的博客首页
---

<h1>最新文章</h1>

<ul>
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="post-meta">
        {{ post.date | date: "%Y年%m月%d日" }}
        {% if post.author %} - {{ post.author }}{% endif %}
      </p>
      <p>{{ post.excerpt | strip_html | truncatewords: 50 }}</p> {# 显示摘要，移除HTML标签，截断至50字 #}
      <a href="{{ post.url | relative_url }}">阅读全文 &raquo;</a>
    </li>
  {% endfor %}
</ul>
