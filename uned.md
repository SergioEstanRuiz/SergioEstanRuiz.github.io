---
layout: page
title: "UNED"
permalink: /uned/
---

# UNED Lecture Notes

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
          {% assign display_name = note.name | split: '.' | first %}
          {% assign display_name = display_name
            | replace: '- ', ' '
            | replace: '-', ' '
            | replace: '_', ' '
            | replace: '  ', ' '
            | strip %}
          <a class="uned-card" href="{{ note.path | relative_url }}" target="_blank" rel="noopener">
            <div class="uned-card-title">{{ display_name }}</div>
            <div class="uned-card-meta">PDF - {{ note.modified_time | date: "%Y-%m-%d" }}</div>
          </a>
        {% endfor %}
      </div>
    {% endif %}
  {% endfor %}
{% else %}
<p>No lecture notes found in assets/uned_pdfs.</p>
{% endif %}
