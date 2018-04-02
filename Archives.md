---
layout: page
title: Archives(归档)
---

<ul>
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li><a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>{{'('}}{{ post.date | date:"%b" }}{{')'}} </li>
  {% endfor %}

</ul>
