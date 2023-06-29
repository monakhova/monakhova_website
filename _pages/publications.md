---
layout: page
permalink: /publications/
title: publications
description:
years: [2023,2022,2021,2020,2019]
nav: true
nav_order: 1
display_categories: [PhD, journal]
---
<!-- _pages/publications.md -->
See <a href="https://scholar.google.com/citations?user=X71o1ykAAAAJ&hl=en">Google scholar</a> for a full publication list.

<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f {{ site.scholar.bibliography }} -q @*[year={{y}}]* %}
{% endfor %}

</div>
