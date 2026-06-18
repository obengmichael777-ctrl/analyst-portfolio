---
layout: default
title: Home
---

# Projects

<div class="project-grid">
  {% for project in site.projects %}
    <article class="project-card">
      <img src="{{ project.image   relative_url }}" alt="{{ project.title }}">
      <h3>{{ project.title }}</h3>
      <p>{{ project.description }}</p>
      <div class="notes">
        <h4>My Approach</h4>
        <p>{{ project.notes }}</p>
      </div>
      <a href="{{ project.url | relative_url }}" class="button primary">View Project</a>
    </article>
  {% endfor %}
</div>