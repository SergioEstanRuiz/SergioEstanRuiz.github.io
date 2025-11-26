---
layout: page
title: "Blog"
permalink: /blog/
---

# Blog

Here I write about research notes, technical explanations, and random ideas.

<style>
.blog-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 20px;
  margin-top: 30px;
}

.blog-card {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  overflow: hidden;
  transition: transform 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
  background: white;
}

.blog-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 12px rgba(0,0,0,0.12);
}

.blog-thumb {
  width: 100%;
  height: 160px;
  object-fit: cover;
}

.blog-title {
  font-weight: bold;
  font-size: 1.1rem;
  margin: 10px 0 5px;
}

.blog-date {
  color: #666;
  font-size: 0.85rem;
}

.blog-card-content {
  padding: 10px 15px 15px 15px;
}
</style>

<div class="blog-grid">
{% for post in site.posts %}
  <a href="{{ post.url | relative_url }}" class="blog-card">

    {% if post.thumbnail %}
      <img src="{{ post.thumbnail | relative_url }}" alt="thumbnail" class="blog-thumb">
    {% else %}
      <img src="/assets/blog/default.jpg" class="blog-thumb">
    {% endif %}

    <div class="blog-card-content">
      <div class="blog-title">{{ post.title }}</div>
      <div class="blog-date">{{ post.date | date: "%B %-d, %Y" }}</div>
    </div>

  </a>
{% endfor %}
</div>
