---
layout: default
title: art
permalink: /art/
description: tip of stylus
display_categories: [work, fun]
horizontal: false
---

<div class="post">

{% assign blog_name_size = site.blog_name | size %}
{% assign blog_description_size = site.blog_description | size %}

{% if blog_name_size > 0 or blog_description_size > 0 %}

  <div class="header-bar">
    <h1>{{ site.art_name }}</h1>
    <h2>{{ site.art_description }}</h2>
  </div>
  {% endif %}


</div>