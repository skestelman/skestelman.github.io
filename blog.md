---
layout: page
title: Blog
---

{% for post in site.posts %}
<article>
  <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
  <p class="post-date">{{ post.date | date: "%B %d, %Y" }}</p>
  {{ post.content }}
</article>
{% endfor %}
