---
layout: page
title: Projects
permalink: /projects/
description: A growing collection of my cool projects.
nav: true
nav_order: 3
display_categories: [Mobile, Web, Organization]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">

<p class="lead">
  Discover my projects, organized into three main categories for easy navigation: <br>
  <a href="#Softwares" class="btn btn-outline-primary my-2 mx-1">Mobile</a>
  <a href="#Websites" class="btn btn-outline-primary my-2 mx-1">Web</a>
  <a href="#Personal" class="btn btn-outline-primary my-2 mx-1">Organization</a>
</p>

{% if site.enable_project_categories and page.display_categories %}

  <!-- Display categorized projects -->

{% for category in page.display_categories %}
<a id="{{ category }}" href=".#{{ category }}">

<h2 class="category">{{ category }}</h2>
</a>
{% assign categorized_projects = site.projects | where: "category", category %}
{% assign sorted_projects = categorized_projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
