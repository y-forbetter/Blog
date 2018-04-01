---
layout: page
title: Categories/Tags(标签)
permalink: /Categories/
---

{% for category in site.categories %}
<h2>{{ category | first }}{{'('}}{{category | last | size}}{{')'}}</h2>
<ul class="arc-list">
    {% for post in category.last %}
        <li><a href="{{ post.url }}">{{ post.title }}</a>
        {{'('}}{{ post.date | date:"%Y/%M/%D"}}{{')'}}</li>
    {% endfor %}
</ul>
{% endfor %}