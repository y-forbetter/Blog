---
layout: page
title: Archives(归档)
permlink: /Archives/
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

    <li><a href="{{ post.url}}">{{ post.title}}</a>{{'('}}{{ post.date | date:"%b" }}{{')'}} </li>
  {% endfor %}

</ul>
