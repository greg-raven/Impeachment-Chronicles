---
title: Archives
layout: page
---

{% for post in site.posts %}
{% assign currentdate = post.date | date: "%Y" %}
{% if currentdate != date %}
{% unless forloop.first %}</ul>{% endunless %}
<h2 id="y{{post.date | date: "%Y"}}">{{ currentdate }}</h2>
<ul>
{% assign date = currentdate %}
{% endif %}
<li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% if forloop.last %}</ul>{% endif %}
{% endfor %}

---

{% assign postsByYear =
site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h2>{{ year.name }}</h2>
<ul>
{% for post in year.items %}
<li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
{% endfor %}

---

{% for post in site.posts  %}
{% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
{% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}
{% if forloop.first %}
<h2 id="{{ this_year }}-ref">{{this_year}}</h2>
<ul>
{% endif %}
<li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% if forloop.last %}
</ul>
{% else %}
{% if this_year != next_year %}
</ul>
<h3 id="{{ next_year }}-ref">{{next_year}}</h3>
<ul>
{% endif %}
{% endif %}
{% endfor %}

---

{% assign postsByYear = site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
<h2>{{ year.name }}</h2>
{% assign postsByMonth = year.items | group_by_exp:"post", "post.date | date: '%B'" %}
{% for month in postsByMonth %}
<h3>{{ month.name }}</h3>
<ul>
{% for post in month.items %}
<li><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
{% endfor %}
{% endfor %}
