---
layout: page
title: Blog
---

<p>

A sidebar for personal thoughts, information on my own projects, aki.guide general updates, and anything I think would be cool enough to post about.

</p>

<p>

View blog entries sorted by Category, <a href="{{ site.baseurl }}/categories/">here</a>.

</p>

<section class="blog">

<div class="list-group">

{% for blog in site.blog %}

<a class="list-group-item list-group-item-action" style="padding: .5rem" data-toggle="tooltip" title="Posted {{ blog.date | date: "%-d %B %Y" }}" href="{{ site.baseurl }}{{ blog.url }}">{{ blog.title }}</a>

{% endfor %}

</div>

</section>
