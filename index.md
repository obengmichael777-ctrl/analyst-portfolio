---
layout: default
title: Home
---

<section id="projects">
  <h2>My Projects</h2>
  
  <div class="project-grid">
    {% for brief in site.project_brief_library %}
      {% assign project_slug = brief.slug | default: brief.title | slugify %}
      {% assign full_project = site.project_archive | where: "slug", project_slug | first %}
      
      <article class="project-card">
        {% if brief.image %}
        <div class="project-card-image">
          <img src="{{ brief.image | relative_url }}" alt="{{ brief.title }}">
        </div>
        {% endif %}
        
        <div class="project-card-content">
          <h3>{{ brief.title }}</h3>
          <p>{{ brief.description }}</p>
          
          {% if brief.tools %}
          <div class="project-tools-mini">
            {% for tool in brief.tools limit:4 %}
            <span class="mini-tool">{{ tool }}</span>
            {% endfor %}
          </div>
          {% endif %}
          
          <div class="project-card-actions">
            {% if full_project %}
            <a href="{{ full_project.url | relative_url }}" class="button primary">
              View Project
            </a>
            {% endif %}
            {% if brief.repository %}
            <a href="{{ brief.repository }}" class="button accent" target="_blank">
              GitHub
            </a>
            {% endif %}
          </div>
        </div>
      </article>
    {% endfor %}
  </div>
</section>