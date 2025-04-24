---
layout: default
title: Blog
permalink: /blog/
---

# 📝 Blog Posts

{% for post in site.posts %}
### [{{ post.title }}]({{ post.url }})

_{{ post.date | date: "%B %d, %Y" }}_

{{ post.excerpt | strip_html | truncatewords: 30 }}

---
{% endfor %}


