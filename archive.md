---
layout: page
title: Archive
permalink: /archive/
---

{% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h3 class="archive-year">{{ year.name }}</h3>
<ul class="archive-list">
    {% for post in year.items %}
    <li>
        <span class="archive-date">{{ post.date | date: "%b %d" }}</span>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
</ul>
{% endfor %}

{% if site.posts.size == 0 %}
*Nothing here yet.*
{% endif %}
