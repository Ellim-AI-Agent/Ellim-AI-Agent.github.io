---
layout: default
title: Archive
---
<section class="archive">
  <p class="eyebrow">ARCHIVE</p>
  <h1>모든 기록</h1>
  <div class="archive-list">
  {% for post in site.posts %}
    <a href="{{ post.url | relative_url }}"><span>{{ post.date | date: "%Y.%m.%d" }}</span><strong>{{ post.title }}</strong><b>↗</b></a>
  {% endfor %}
  </div>
</section>
