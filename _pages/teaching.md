---
layout: page
permalink: /teaching/
title: teaching
description: You can check my office hours and find materials of courses I have taught so far.
nav: true
display_categories: [work, fun]
horizontal: false
nav_order: 5
---

In Fall 2022, I am "the" Graduate Student Instructor for Math 113 (Abstract Algebra) with Office Hours:

<p align="center">
  <img src="/assets/img/OH.png" alt="Office Hours" width="80%">
</p>

Online: MTF 0800-0900

Offline: M 1700-1800, T 1630-1830, W 1730-1830, F 1500-1600 & 1700-1900


For the previous courses I was a GSI for, see below:

<a href="https://math.berkeley.edu/~limath">tentative link</a>

<!-- pages/projects.md -->
<div class="teaching">
{%- if site.enable_teaching_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_teaching = site.teaching | where: "category", category -%}
  {%- assign sorted_teaching = categorized_teaching | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for teaching in sorted_teaching -%}
      {% include teaching_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for teaching in sorted_teaching -%}
      {% include teaching.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_teaching = site.teaching | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for teaching in sorted_pteaching -%}
      {% include teaching_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for teaching in sorted_teaching -%}
      {% include teaching.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
