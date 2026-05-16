---
layout: default
title: Journal
permalink: /journal/
---
{% assign sorted_categories = site.categories | sort %}

{% for category in sorted_categories %}
  <h2>{{ category[0] | capitalize }}</h2>
  <ul>
    {% assign posts = category[1] | sort: "date" | reverse %}
    {% for post in posts %}
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
        <small>({{ post.date | date: "%Y-%m-%d" }})</small>
      </li>
    {% endfor %}
  </ul>
{% endfor %}