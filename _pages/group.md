---
layout: default
title: team
permalink: /team/
description: We're hiring! If you'd like to join us, find more infomration at pages
nav: true
nav_order: 5
display_categories: [Professor, Postdocs and Visiting Scholars, PhD students, Alumni]
display_alumni: [Undergraduates mentored at UC Berkeley]
horizontal: false
---

<!-- pages/group.md -->
<!-- Display projects without categories -->
<h2>Team</h2>
<div class="projects">
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.data.team_members | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
    {%- for project in sorted_projects -%}
	<div class="container">
	  <div class="row g-0">
		  <div class ="col-sm-4">
			<a href="{{ project.redirect }}">
            {% include figure.html path=project.img alt="project thumbnail" width="100%" class = "img-fluid z-depth-1 rounded-circle hoverable"%}</a></div>
	          <div class ="col-sm-7">
                <h4>{{ project.name }}</h4>
			    <p>{{ project.info }}<br><br>
                  {% include social_group.html %}
			</p>
	        </div>
		</div>
	</div>
    {%- endfor %}
	{%- endfor %}
	{%- for category in page.display_alumni %}
	<h4>{{ category }}</h4>
	<div>
	{%- assign categorized_alumni = site.data.alumni | where: "category", category -%}
	{%- assign sorted_alumni = categorized_alumni | sort: "importance" -%}
	{%- for alum in sorted_alumni -%}
	{{ alum.name }}, {{ alum.info }} &nbsp;
	{%- if alum.website -%}
            <a href="{{ alum.website }}" title="website"><i class="fas fa-home"></i></a>
            {% endif %} <br>
	{%- endfor %}
    </div>
	{%- endfor %}
<div class="projects">