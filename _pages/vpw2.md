---
layout: page
title: Virtual Pro Wrestling 2
logo: vpw2
---

<div class="list-group">

{% for post in site.categories.vpw2 %}

<a class="list-group-item list-group-item-action" data-toggle="tooltip" title="Posted {{ post.date | date: "%-d %B %Y" }}" href="{{ site.url }}{{ post.url }}">{{ post.title }}&nbsp;&nbsp;<span style="color: #dee2e6">#{{ post.category }}</span></a>

{% endfor %}

</div>





