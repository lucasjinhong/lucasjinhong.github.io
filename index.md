---
layout: page
title: Koh Jin Hong, Lucas
permalink: /
---

<div style="text-align: center;">
  <img src="{{ "/assets/images/profile_picture.png" | relative_url }}" alt="Koh Jin Hong, Lucas" width="200" height="200" style="border-radius: 50%; object-fit: cover; margin-bottom: 1em; border: 3px solid #eee;">
  <h1>{{ site.author.name }}</h1>
  <p style="font-size: 1.1em; color: #555;">Master of Science Candidate, Electronic Engineering</p>
</div>

## Summary
Highly motivated Electronic Engineering Master's candidate (expected Aug 2025) with a robust foundation in networking (TCP/IP, 5G, IAB) and programming (Python, C++). Demonstrates practical experience from internships and academic projects in automating firmware testing (Docker, Jenkins), developing backend systems (Node.js, AWS, MongoDB), and researching distributed link scheduling for IAB Networks. Eager to apply expertise in system development, integration, and innovative technologies to a challenging engineering role.

---

## Key Skills
*   **Programming Languages:** Python, C, C++, JavaScript (Node.js)
*   **Networking & Protocols:** TCP/IP, 5G Architecture Concepts, IAB Networks, Fortinet (FortiGate)
*   **Development Tools & Platforms:** Git, Linux, Jenkins, Docker, Jira, AWS
*   **Databases:** MongoDB
*   **Languages:** Chinese (Fluent), English (Proficient, TOEIC: 825)

---

## Featured Projects
Below are some highlights of my work. For a full list, please visit the [Projects Page](./projects/).

{% for project in site.projects limit:2 %}
### [{{ project.title }}]({{ project.url | relative_url }})
{% if project.short_description %}
{{ project.short_description }}
{% endif %}
{% if project.technologies %}

*Technologies: {{ project.technologies | join: ", " }}*
{% endif %}
---
{% endfor %}