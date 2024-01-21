---
layout: page
title: Posts
---

<section class="posts">

<div class="list-group">

{% for post in site.posts %}

<a class="list-group-item list-group-item-action" style="padding: .5rem" data-toggle="tooltip" title="Posted {{ post.date | date: "%-d %B %Y" }}" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>

{% endfor %}

</div>

</section>
