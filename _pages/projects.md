---
layout: page
title: vietnam
permalink: /vietnam/
description: Vietnam is my home. Once one of the world’s poorest and most isolated countries from nearly 120 years in ghastly war, Vietnam is now a middle-income country with a dynamic, young population and a promising future. Here's to Vietnam's resilience beauty and its future!
nav: true
nav_order: 3
display_categories: [food, places]
horizontal: false
---

<!-- pages/projects.md -->

::: projects
{% if site.enable_project_categories and page.display_categories %} <!-- Display categorized projects --> {% for category in page.display_categories %} <a id="{{ category }}" href=".#{{ category }}">

<h2 class="category">

{{ category }}

</h2>

</a> {% assign categorized_projects = site.projects \| where: "category", category %} {% assign sorted_projects = categorized_projects \| sort: "importance" %} <!-- Generate cards for each project --> {% if page.horizontal %}

::: container
```         
<div class="row row-cols-2">
{% for project in sorted_projects %}
  {% include projects_horizontal.liquid %}
{% endfor %}
</div>
```
:::

{% else %}

::: grid
```         
{% for project in sorted_projects %}
  {% include projects.liquid %}
{% endfor %}
```
:::

{% endif %} {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects \| sort: "importance" %}

<!-- Generate cards for each project -->

{% if page.horizontal %}

::: container
```         
<div class="row row-cols-2">
{% for project in sorted_projects %}
  {% include projects_horizontal.liquid %}
{% endfor %}
</div>
```
:::

{% else %}

::: grid
```         
{% for project in sorted_projects %}
  {% include projects.liquid %}
{% endfor %}
```
:::

{% endif %} {% endif %}
:::
