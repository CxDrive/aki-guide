---
layout: page
title: WCW/nWo 레벤지 (REVENJI)
logo: revenji
---

<div class="list-group">

{% for post in site.categories.revenji %}

<a class="list-group-item list-group-item-action" data-toggle="tooltip" title="Posted {{ post.date | date: "%-d %B %Y" }}" href="{{ site.url }}{{ post.url }}">{{ post.title }}&nbsp;&nbsp;<span style="color: #dee2e6">#{{ post.category }}</span></a>

{% endfor %}

</div>





