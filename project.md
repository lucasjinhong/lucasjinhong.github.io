---
layout: page
title: Projects
permalink: /projects/
---

# My Projects

Here you'll find a selection of projects I've worked on, spanning academic research, internship contributions, and personal development. Click on any project to learn more about the challenges, solutions, and technologies involved.

{% for project in site.projects reversed %}
## [{{ project.title }}]({{ project.url | relative_url }})
{% if project.image %}
<a href="{{ project.url | relative_url }}"><img src="{{ project.image | relative_url }}" alt="{{ project.title }} thumbnail" width="200" style="border-radius: 4px; border: 1px solid #ddd; margin-bottom: 0.5em;"></a>
{% endif %}

{% if project.short_description %}
{{ project.short_description }}
{% endif %}

{% if project.technologies %}

*Technologies: {{ project.technologies | join: ", " }}*
{% endif %}

[Read More »]({{ project.url | relative_url }})
---
{% endfor %}