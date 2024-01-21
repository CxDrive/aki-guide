---
layout: page
title: Tags
---

<section class="posts">

<ul class="list-group">

{% assign tags = site.tags | sort %}

{% for tag in tags %}

<li class="list-group-item list-group-item-action" style="padding: .5rem" >

<a href="{{ site.baseurl }}/tag/{{ tag | first | slugify }}/">#{{ tag[0] | replace:'-', ' ' }}</a>

&nbsp;&nbsp;

({{ tag | last | size }})

</li>

{% unless forloop.last %}

{% endunless %}

{% endfor %}

</ul>

</section>
