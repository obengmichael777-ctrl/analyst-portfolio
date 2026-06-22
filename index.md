---
layout: default
title: Home
---

<section id="projects">
  <h2>My Projects</h2>
  
  <div class="project-grid">
    {% for project in site.projects %}
      <article class="project-card">
        {% if project.image %}
        <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
        {% endif %}
        
        <div class="project-card-content">
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
          
          {% if project.tools %}
          <div class="project-tools-mini">
            {% for tool in project.tools limit:3 %}
            <span class="mini-tool">{{ tool }}</span>
            {% endfor %}
          </div>
          {% endif %}
          
          <div class="project-card-actions">
            <a href="{{ project.url | relative_url }}" class="button primary">
              Read More
            </a>
            {% if project.repository %}
            <a href="{{ project.repository }}" class="button accent" target="_blank">
              View Code
            </a>
            {% endif %}
          </div>
        </div>
      </article>
    {% endfor %}
  </div>
</section>