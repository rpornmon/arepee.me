---
layout: default
title: photography
permalink: /photography/
description: through the viewfinder
photo_tags: ["wish you were here", "humanity's best friend", "bull city"] 
photo_categories: [work, fun]
horizontal: false
---
<!--  -->
<div class="post">

{% assign photo_name_size = site.photo_name | size %}
{% assign photo_description_size = site.photo_description | size %}

{% if photo_name_size > 0 or photo_description_size > 0 %}

  <div class="header-bar">
    <h1>{{ site.photo_name }}</h1>
    <h2>{{ site.photo_description }}</h2>
  </div>
  {% endif %}

{% if site.photo_tags and site.photo_tags.size > 0 or site.photo_categories and site.photo_categories.size > 0 %}

  <div class="tag-category-list">
    <ul class="p-0 m-0">
      {% for tag in site.photo_tags %}
        <li>
          <i class="fa-solid fa-hashtag fa-sm"></i> <a href="{{ tag | slugify | prepend: '/art/tag/' | relative_url }}">{{ tag }}</a>
        </li>
        {% unless forloop.last %}
          <p>&bull;</p>
        {% endunless %}
      {% endfor %}
      {% if site.photo_categories.size > 0 and site.photo_tags.size > 0 %}
        <p>&bull;</p>
      {% endif %}
      {% for category in site.photo_categories %}
        <li>
          <i class="fa-solid fa-tag fa-sm"></i> <a href="{{ category | slugify | prepend: '/art/category/' | relative_url }}">{{ category }}</a>
        </li>
        {% unless forloop.last %}
          <p>&bull;</p>
        {% endunless %}
      {% endfor %}
    </ul>
  </div>
  {% endif %}


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" 
        path="assets/img/MyLeaf.jpg" 
        title="My Leaf" max-height="300px" 
        width="auto" 
        class="img-fluid rounded z-depth-1"
        caption="kyoto, japan. 2026"
        zoomable=true %}
    </div>
</div>


<!-- pages/gallery.md -->
<div class="projects">
{% if site.enable_project_categories and page.photo_categories %}
  <!-- photo categorized projects -->
  {% for category in page.photo_categories %}
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

<!-- photo projects without categories -->

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
