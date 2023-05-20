---
title: Search
layout: page
---

**Note:** Our search page is still trying to get caught up with the new changes we implemented. Sorry for any inconvenience.

<script async src="https://cse.google.com/cse.js?cx=004234720413995998423:vyup6kxwuhp"></script>
<div class="gcse-search"></div>

Files on this site:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

