---
layout: default
title: Blog entries filed under 'uwa'
date: 1900-01-01
---

<h2>{{ page.title }}</h2>
<section class="posts">
{% assign categories = site.blog | group_by: 'category' | sort: "name" %}
{% for category in categories %}
 {% if category.name != "uwa" %}
    {% assign name = "null" %}
  {% else %}
    {% assign name = category.name %}
  {% endif %}
<div class="list-group" id="{{ name | slugify }}-div">
{% assign pages_list = category.items %}
{% for post in pages_list reversed %}
<a class="list-group-item list-group-item-action" style="padding: .5rem" data-toggle="tooltip" title="Posted {{ post.date | date: "%-d %B %Y" }}" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
{% endfor %}
</div>
{% endfor %}
</section>
