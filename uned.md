---
layout: page
title: "UNED"
permalink: /uned/
---

<p class="lede">
  A curated collection of notes prepared between 2022 and 2025 for the Economics
  degree at UNED. Some notes are handwritten and others are typed.
</p>

<p>
  I share these notes to make study resources more accessible and to reduce barriers
  created by expensive textbooks.
</p>

{% for year in site.data.uned %}
  <h2>{{ year.label }}</h2>
  <div class="notes-grid">
    {% for note in year.notes %}
      <a class="note-card" href="{{ note.file | relative_url }}" target="_blank" rel="noopener">
        <div class="note-card-content">
          <div class="note-title">{{ note.title }}</div>
          <div class="note-meta">PDF</div>
        </div>
      </a>
    {% endfor %}
  </div>
{% endfor %}
