---
layout: default
title: 태그
---
<section class="page-heading tags-heading"><p>태그</p><h1>반복해서<br>마주치는 <i>관심사.</i></h1><span>한 태그 안에서 시간이 쌓이는 방식을 볼 수 있습니다.</span></section><section class="tag-index" aria-label="태그 목록">{% assign tags = site.tags | sort %}{% for tag in tags %}<a href="#{{ tag[0] | slugify }}">{{ tag[0] }} <span>{{ tag[1].size }}</span></a>{% endfor %}</section><section class="tag-list">{% for tag in tags %}<section id="{{ tag[0] | slugify }}"><header><p>태그</p><h2>{{ tag[0] }}</h2></header><ol>{% for post in tag[1] %}<li><time>{{ post.date | date: "%Y.%m.%d" }}</time><a href="{{ post.url | relative_url }}">{{ post.title }}<span>{{ post.kind | default: "기록" }}</span></a></li>{% endfor %}</ol></section>{% endfor %}</section>