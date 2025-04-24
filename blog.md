---
layout: default
title: Blog
permalink: /blog/
---

# 📝 Blog Posts

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}
