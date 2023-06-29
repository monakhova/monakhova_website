---
layout: about
title: about
permalink: /
subtitle: <span class="font-weight-bold"> <a href='kristina'>Prof. Kristina Monakhova</a></span>

news: true  # includes a list of news items
latest_posts: false  # includes a list of the newest posts
selected_papers: false # includes a list of papers marked as "selected={true}"
social: true  # includes social icons at the bottom of the page
project_categories: [Compressive multidimensional imaging, Physics-informed machine learning]

---
{% include figure.html path='assets/img/codesign.png' width="100%"-%}

We combine ideas from machine learning, signal processing, optics, computer vision and physics to build better imaging systems (cameras, microscopes, and telescopes) through the <b>co-design of optics, algorithms, and high-level tasks</b>. Our aim is to design the next generation of smart, computational imagers that fuel scientific discovery, robotics, and medical diagnostics. We are particularly interested in:

<ul>
<li> <span class="font-weight-bold">Differentiable optics</span> - learning the best optical designs using data</li>
<li> <span class="font-weight-bold">Physics-informed machine learning</span> - How can we effectively combine our knowledge of imaging system physics with deep learning? </li>
<li> <span class="font-weight-bold">Task-based imaging systems</span> - What's the best camera or microscope for high-level tasks, such as robotics or medical diagnostics?</li>
<li> <span class="font-weight-bold">Inverse problems and neural representations</span>: Can we leverage neural priors to improve our imaging systems for microscopy and photography? </li>
</ul>


Some of our previous projects include: 
<h2>prior projects</h2>
<div>
{%- for category in page.project_categories %}
{%- assign categorized_projects = site.data.past_projects | where: "category", category -%}
{%- assign sorted_projects = categorized_projects | sort: "importance" -%}
{%- assign categorized_descriptions = site.data.past_projects_description | where: "category", category -%}
<h5>{{category}}</h5>
{%- for descrip in categorized_descriptions -%}
<p>{{descrip.description}} </p>
{% endfor %}

<div class="row">
	{%- for project in sorted_projects -%}
		<div class="col-sm mt-3 mt-md-0">
		<a href="{{project.website}}">
	    {% if project.img contains 'mp4' -%}
		{% include video.html 
			path=project.img
			class="img-fluid z-depth-1 rounded" 
			controls=true autoplay=true muted=true caption = project.name%}
		{%- else -%}
		{% include figure.html path=project.img caption = project.name class="img-fluid rounded z-depth-1" %}
		{%- endif %}
	</a>
	</div>
	{% endfor %}
	
</div>
{% endfor %}
</div>

Check out our recent papers for more details (see [publications](publications)). 



