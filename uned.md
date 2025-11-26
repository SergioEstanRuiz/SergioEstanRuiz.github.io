---
layout: page
title: "UNED"
permalink: /uned/
---

# UNED Lecture Notes

<style>
.uned-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
  gap: 20px;
  margin-top: 20px;
}

.uned-card {
  display: block;
  padding: 16px;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  background: #fafafa;
  text-decoration: none;
  color: inherit;
  transition: transform 0.15s ease-in-out, box-shadow 0.15s ease-in-out, background 0.15s ease-in-out;
}

.uned-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 12px rgba(0,0,0,0.12);
  background: #fff;
}

.uned-card-title {
  font-weight: 700;
  margin-bottom: 8px;
}

.uned-card-meta {
  color: #666;
  font-size: 0.9rem;
}
</style>

{% assign year_labels = "year1,year2,year3,year4" | split: "," %}
{% assign uned_notes = site.static_files | where_exp: "file", "file.path contains '/assets/uned_pdfs/'" | sort: "name" %}

{% if uned_notes.size > 0 %}
  {% for year in year_labels %}
    {% assign prefix = '/assets/uned_pdfs/' | append: year | append: '/' %}
    {% assign notes_for_year = uned_notes | where_exp: "file", "file.path contains prefix" %}
    {% if notes_for_year.size > 0 %}
      <h2>{{ year | replace: 'year', 'Year ' }}</h2>
      <div class="uned-grid">
        {% for note in notes_for_year %}
          <a class="uned-card" href="{{ note.path | relative_url }}" target="_blank" rel="noopener">
            <div class="uned-card-title">{{ note.name | split: '.' | first | replace: '-', ' ' | replace: '_', ' ' }}</div>
            <div class="uned-card-meta">PDF - {{ note.modified_time | date: "%Y-%m-%d" }}</div>
          </a>
        {% endfor %}
      </div>
    {% endif %}
  {% endfor %}
{% else %}
<p>No lecture notes found in assets/uned_pdfs.</p>
{% endif %}
