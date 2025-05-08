---
layout: default # Assumes you have a _layouts/default.html
title: Home
---

<img src="/assets/images/profile_picture.png" alt="Koh Jin Hong, Lucas" style="width:150px; border-radius:50%;">

# KOH JIN HONG, LUCAS
**Master of Science Candidate, Electronic Engineering**

[Email: {{ site.email }}](mailto:{{ site.email }}) | [LinkedIn]({{ site.linkedin_url }}) | [GitHub](https://github.com/{{ site.github_username }}) | [Download Resume](/assets/resume_kohjinhonglucas.pdf)

## Summary
Highly motivated Electronic Engineering Master's candidate (expected Aug 2025) with a robust foundation in networking (TCP/IP, 5G, IAB) and programming (Python, C++). Demonstrates practical experience from internships and academic projects in automating firmware testing (Docker, Jenkins), developing backend systems (Node.js, AWS, MongoDB), and researching distributed link scheduling for IAB Networks. Eager to apply expertise in system development, integration, and innovative technologies to a challenging engineering role.

## Key Skills
*   **Programming Languages:** Python, C, C++, JavaScript (Node.js)
*   **Networking & Protocols:** TCP/IP, 5G Architecture Concepts, IAB Networks, Fortinet (FortiGate)
*   **Development Tools & Platforms:** Git, Linux, Jenkins, Docker, Jira, AWS
*   **Databases:** MongoDB
*   **Languages:** Chinese (Fluent), English (Proficient, TOEIC: 825)

---

## Featured Projects
Here are some of the projects I've worked on. Click to learn more!

{% for project in site.projects reversed %}
### [{{ project.title }}]({{ project.url }})
*{{ project.short_description }}*
**Technologies:** {{ project.technologies | join: ", " }}
{% endfor %}

---
<!-- You can add an Education section here if desired, similar to your resume -->
<!-- You can add an Experience section here too, or link to resume -->