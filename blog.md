---
layout: page
title: "Blog"
permalink: /blog/
---

# Blog

Here I write about research notes, technical explanations, and random ideas.

<div class="card-grid">
  {% for post in site.posts %}
    <a class="card" href="{{ post.url | relative_url }}">
      <div class="card-title">{{ post.title }}</div>
      <div class="card-meta">
        {{ post.date | date: "%B %-d, %Y" }}
      </div>
    </a>
  {% endfor %}
</div>
