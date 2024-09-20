---
layout: page
title: travels
permalink: /travels/
description: A growing collection my travels.
nav: true
nav_order: 3
display_categories: []
horizontal: false
---

<!-- pages/travels.md -->
<div class="travels">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_travels = site.travels | where: "category", category %}
  {% assign sorted_projects = categorized_travels | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for travels in sorted_travels %}
      {% include travels_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_travels %}
      {% include travels.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display travels without categories -->

{% assign sorted_travels = site.travels | sort: "importance" %}

  <!-- Generate cards for each travels -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for travels in sorted_travels %}
      {% include travels_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for travels in sorted_travels %}
      {% include travels.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
