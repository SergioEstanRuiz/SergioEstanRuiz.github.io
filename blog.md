---
layout: page
title: "Blog"
permalink: /blog/
---

<p class="lede">
  Notes on research, technical topics, and ideas from mathematics, machine learning,
  and economics.
</p>

<div class="blog-grid">
  {% for post in site.posts %}
    <a href="{{ post.url | relative_url }}" class="blog-card">
      {% if post.thumbnail %}
        <img src="{{ post.thumbnail | relative_url }}" alt="Post thumbnail" class="blog-thumb" />
      {% else %}
        <img src="/assets/blog/thumbnail.png" alt="Default thumbnail" class="blog-thumb" />
      {% endif %}
      <div class="blog-card-content">
        <div class="blog-title">{{ post.title }}</div>
        <div class="blog-date">{{ post.date | date: "%B %-d, %Y" }}</div>
      </div>
    </a>
  {% endfor %}
</div>
