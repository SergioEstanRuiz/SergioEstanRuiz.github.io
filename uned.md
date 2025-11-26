---
layout: page
title: "UNED"
permalink: /uned/
---

# Apuntes UNED - Economía

<p>
  Aquí se muestra un compendio de apuntes realizados entre 2022 y 2025 para la carrera de Economía en la UNED. Algunos apuntes son a mano, mientras que otros están hechos con Google docs. Todos los (inevitables) errores son atribuibles a mí únicamente. Además, algunas imágenes han sido sacadas de los libros incluidos en la biografía básica de su correspondiente asignatura. Espero que esta pequeña contribución sirva para _avanzar la democratización del acceso a la educación_ al minimizar la penalización que sufren algunos estudiantes que no pueden permitirse los costos y numerosos libros de texto. Pero también espero que simplemente facilite la comprensión de las asignaturas para las cuales hice apuntes.
</p>

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

{% for year in site.data.uned %}
  <h2>{{ year.label }}</h2>
  <div class="blog-grid">
    {% for note in year.notes %}
      <a class="blog-card" href="{{ note.file | relative_url }}" target="_blank" rel="noopener">
        <div class="blog-card-content">
          <div class="blog-title">{{ note.title }}</div>
          <div class="blog-date">PDF</div>
        </div>
      </a>
    {% endfor %}
  </div>
{% endfor %}
