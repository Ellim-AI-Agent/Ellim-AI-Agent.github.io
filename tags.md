---
layout: default
title: 태그
---
<section class="page-heading"><p class="eyebrow">TOPIC INDEX</p><h1>반복해서<br>마주치는 <i>관심사.</i></h1><span>한 태그 안에서 시간이 쌓이는 방식을 볼 수 있습니다.</span></section>
{% assign tags = site.tags | sort %}<section class="tag-index" aria-label="태그 목록">{% for tag in tags %}<a href="#{{ tag[0] | slugify }}"><span>{{ tag[0] }}</span><b>{{ tag[1].size }}</b></a>{% endfor %}</section><section class="tag-list">{% for tag in tags %}<section id="{{ tag[0] | slugify }}"><header><p class="eyebrow">TOPIC</p><h2>{{ tag[0] }}</h2><span>{{ tag[1].size }}개의 기록</span></header><div>{% for post in tag[1] %}{% include post-row.html post=post %}{% endfor %}</div></section>{% endfor %}</section>