---
layout: default
title: Home
---

<section id="projects">
  <h2>My Projects</h2>
  
  <div class="project-grid">
    {% for brief in site.project_brief_library %}
      <article class="project-card">
        <div class="project-card-content">
          <h3>{{ brief.title }}</h3>
          <p>{{ brief.description }}</p>
        </div>
      </article>
    {% endfor %}
  </div>
  
  <div style="margin-top: 20px; padding: 15px; background: #f0f0f0; border-radius: 8px;">
    <strong>Collection Check:</strong><br>
    project_brief_library size: {{ site.project_brief_library.size }}<br>
    project_archive size: {{ site.project_archive.size }}
  </div>
</section>