---
layout: page
title: WWF Wrestlemania 2000
---

![Screenshot](../../assets/img/logo_wm2k.png){:.centered-img}

<div class="list-group">

{% for post in site.categories.wm2k %}

<a class="list-group-item list-group-item-action" data-toggle="tooltip" title="Posted {{ post.date | date: "%-d %B %Y" }}" href="{{ site.url }}{{ post.url }}">{{ post.title }}&nbsp;&nbsp;<span style="color: #dee2e6">#{{ post.category }}</span></a>

{% endfor %}

</div>





