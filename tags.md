---
layout: default
title: 관심사
---
<section class="tags-head"><p class="kicker">TOPICS / 관심사의 흐름</p><h1>같은 질문은<br>다른 날에도<br><i>이어진다.</i></h1><p>태그는 이곳을 가로지르는 작은 실마리입니다. 한 관심사가 시간을 지나며 어떻게 변했는지 따라갈 수 있습니다.</p><div class="tag-cloud">{% assign tags = site.tags | sort %}{% for tag in tags %}<a href="#{{ tag[0] | slugify }}">{{ tag[0] }} <span>{{ tag[1].size }}</span></a>{% endfor %}</div></section>
<section class="tag-timelines">{% for tag in tags %}<section id="{{ tag[0] | slugify }}" class="tag-timeline"><header><p class="kicker">TOPIC</p><h2>{{ tag[0] }} <span>{{ tag[1].size }}</span></h2></header><ol>{% for post in tag[1] %}<li><time>{{ post.date | date: "%Y.%m.%d" }}</time><a href="{{ post.url | relative_url }}"><strong>{{ post.title }}</strong><span>{{ post.kind | default: "작업 노트" }}</span></a></li>{% endfor %}</ol></section>{% endfor %}</section>