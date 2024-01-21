---
layout: page
title: Posts
---

<div class="list-group">

{% for post in site.posts %}

<a class="list-group-item list-group-item-action" data-toggle="tooltip" title="Posted {{ post.date | date: "%-d %B %Y" }}" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>

{% endfor %}

</div>
