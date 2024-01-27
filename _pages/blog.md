---
layout: page
title: Blog
---

A sidebar for personal thoughts, information on my own projects, aki.guide general updates, and anything I think would be cool enough to post about.

View blog entries sorted by Category, <a href="{{ site.url }}/categories/">here</a>.

{% for blog in site.blog %}

<div class="list-group">

<a class="list-group-item list-group-item-action" data-toggle="tooltip" title="Posted {{ blog.date | date: "%-d %B %Y" }}" href="{{ site.url }}{{ blog.url }}">{{ blog.title }}&nbsp;&nbsp;<span style="color: #dee2e6">#{{ blog.category }}</span></a>

</div>

{% endfor %}
