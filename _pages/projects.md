---
layout: page
title: teaching
permalink: /projects/
description: The collection of my previous (teaching) courses
nav: true
nav_order: 2
display_categories: [53, 54, 110, 126]
horizontal: false
---
In Fall 2022, I am "the" Graduate Student Instructor for Math 113 (Abstract Algebra) with Office Hours:<br>

<p align="center">
  <img src="/assets/img/OH.png" alt="Office Hours" width="80%">
</p>

Online: MTF 0800-0900

Offline: M 1700-1800, T 1630-1830, W 1730-1830, F 1500-1600 & 1700-1900

Just FYI, I am GSIing (alone) for eight different lectures (with six distinct lecturers).

<hr>

<h4>For the previous courses I was a GSI for, see below:</h4>

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
