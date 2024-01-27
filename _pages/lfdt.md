---
layout: page
title: La Fin Du Tour - Virtual Pro Wrestling Alpha
logo: lfdt
---

<div class="list-group">

{% for post in site.categories.lfdt %}

<a class="list-group-item list-group-item-action" data-toggle="tooltip" title="Posted {{ post.date | date: "%-d %B %Y" }}" href="{{ site.url }}{{ post.url }}">{{ post.title }}&nbsp;&nbsp;<span style="color: #dee2e6">#{{ post.category }}</span></a>

{% endfor %}

</div>





