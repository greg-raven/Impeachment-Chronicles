---
title: Archives
layout: page
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title | smartify }}</a> ({{ post.date | date_to_string: "ordinal", "US" }})
    </li>
  {% endfor %}
</ul>
