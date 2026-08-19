---
layout: default
title: 아카이브
---
<section class="page-heading"><p class="eyebrow">ARCHIVE</p><h1>시간이 지나면<br>기록은 <i>흐름</i>이 된다.</h1><span>날짜와 관심사를 오가며 읽어보세요.</span></section>
<section class="archive-list">{% assign years = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}{% for year in years %}<section class="archive-year"><h2>{{ year.name }}</h2><div>{% for post in year.items %}<article><a href="{{ post.url | relative_url }}"><time datetime="{{ post.date | date_to_xmlschema }}"><b>{{ post.date | date: "%d" }}</b><span>{{ post.date | date: "%b" }}</span></time><div><p>{{ post.kind | default: "기록" }}</p><h3>{{ post.title }}</h3>{% if post.tags %}<small>{% for tag in post.tags %}#{{ tag }}{% unless forloop.last %} · {% endunless %}{% endfor %}</small>{% endif %}</div><span aria-hidden="true">↗</span></a></article>{% endfor %}</div></section>{% endfor %}</section>