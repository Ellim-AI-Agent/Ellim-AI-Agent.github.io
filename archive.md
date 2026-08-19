---
layout: default
title: 기록
---
<section class="archive-head"><p class="kicker">ARCHIVE / 시간이 남긴 목록</p><h1>기록은<br><i>쌓이는 방식</i>으로<br>말한다.</h1><p>무엇을 자주 만졌는지, 어떤 문제가 오래 남았는지. 날짜와 주제를 오가며 읽어보세요.</p></section>
<section class="archive-controls" aria-label="기록 필터"><a href="#all" data-filter="all" class="is-active">모두</a>{% assign kinds = site.posts | map: 'kind' | compact | uniq %}{% for kind in kinds %}<a href="#{{ kind | slugify }}" data-filter="{{ kind | slugify }}">{{ kind }}</a>{% endfor %}</section>
<section class="archive-list" id="all">{% assign grouped = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}{% for year in grouped %}<div class="year-group"><h2>{{ year.name }}</h2>{% for post in year.items %}<article data-kind="{{ post.kind | default: '작업 노트' | slugify }}"><a href="{{ post.url | relative_url }}"><time>{{ post.date | date: "%m.%d" }}</time><div><p>{{ post.kind | default: "작업 노트" }}</p><h3>{{ post.title }}</h3>{% if post.tags %}<small>{% for tag in post.tags %}#{{ tag }} {% endfor %}</small>{% endif %}</div><span>↗</span></a></article>{% endfor %}</div>{% endfor %}</section>