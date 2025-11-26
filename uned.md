---
layout: page
title: "UNED"
permalink: /uned/
---

# UNED Lecture Notes

<p>
  These are lecture notes I’ve written while studying Economics at UNED.
  They may contain mistakes and are a work in progress.
</p>

{% for year in site.data.uned %}
  <h2>{{ year.label }}</h2>
  <div class="card-grid">
    {% for note in year.notes %}
      <a class="card" href="{{ note.file | relative_url }}" target="_blank" rel="noopener">
        <div class="card-title">{{ note.title }}</div>
        <div class="card-meta">PDF</div>
      </a>
    {% endfor %}
  </div>
{% endfor %}