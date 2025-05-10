---
layout: single
permalink: /
author_profile: true
entries_layout: grid
---

<div style="text-align: center; margin-bottom: 2em;">
  <h1>{{ site.name }}</h1>
  <p class="lead" style="font-size: 1.2em; color: #555;">Master of Science Candidate, Electronic Engineering</p>
  <p style="margin-top: 1em;">
    <a href="{{ "/assets/Resume_Lucas.pdf" | relative_url }}" class="btn btn--success btn--large" target="_blank" download>Download Resume (PDF)</a>
  </p>
</div>

## Summary
{% capture resume_summary %}
Highly motivated Electronic Engineering Master's candidate (expected Aug 2025) with a robust foundation in networking (TCP/IP, 5G, IAB) and programming (Python, C++). Demonstrates practical experience from internships and academic projects in automating firmware testing (Docker, Jenkins), developing backend systems (Node.js, AWS, MongoDB), and researching distributed link scheduling for IAB Networks. Eager to apply expertise in system development, integration, and innovative technologies to a challenging engineering role.
{% endcapture %}
{{ resume_summary | markdownify }}

---

## Education

### Master of Science, Electronic Engineering
*2023 - Present*
**National Taipei University of Technology**
*   Authored graduate paper on Distributed Link Scheduling for IAB Networks, investigating Layer 2 5G architecture and implementing an optimized packet forwarding algorithm for half-duplex scenarios.
*   Configured and deployed security tunnels and firewalls using FortiGate technology for Taiwan Space Agency projects.
*   Served as Teaching Assistant for Master's level courses (Python, C, Algorithms), providing student support and assisting instructors with course materials.
*   Resolved network connectivity issues (e.g., IP conflicts, configuration errors) as a part-time member of the university's computer networking centre.

### Bachelor of Science, Electronic Engineering
*2019 - 2023*
**National Taipei University of Technology**
*   Developed a user login system server using Node.js, integrating it with a MongoDB database and utilizing Amazon Web Services (AWS) for backend infrastructure.
*   Designed and implemented a visual novel game prototype using PyQt6, developing the core Python-based architecture.

---

## Experience

### Junior Firmware Engineer (Intern)
*2022 - 2023*
**Sierra Wireless**
*   Engineered an automated firmware testing testbed using Docker and Jenkins, automating daily validation tests to run nightly, significantly streamlining the validation workflow.
*   Executed comprehensive validation and regression testing on new firmware releases; identified, documented, and reported bugs to ensure quality prior to deployment.

---

## Skills
*   **Programming Languages:** Python, C, C++, JavaScript (Node.js)
*   **Networking & Protocols:** TCP/IP, 5G Architecture Concepts, IAB Networks, Fortinet (FortiGate)
*   **Development Tools & Platforms:** Git, Linux, Jenkins, Docker, Jira, AWS
*   **Databases:** MongoDB
*   **Languages:** Chinese (Fluent), English (Proficient, TOEIC: 825)

---

<h2 id="my-projects">My Projects Debug</h2>
<p>Here are some of the key projects I've worked on. Click to learn more about each one.</p>

{% assign sorted_projects = site.projects | sort: "date" | reverse %}
{% if sorted_projects.size > 0 %}
  <div class="entries-grid">
    {% for project in sorted_projects %}
      {% if project.title %}
        {% include archive-single.html type="grid" post=project %}
      {% endif %}
    {% endfor %}
  </div>
{% else %}
  <p><em>Detailed project descriptions coming soon. You can see an overview of my experience in the sections above.</em></p>
{% endif %}

---

<h2 id="contact">Get in Touch</h2>
I'm actively seeking challenging opportunities and am always open to discussing innovative projects, collaborations, or roles where I can contribute my skills in networking and software development.

Please feel free to reach out through any of the channels below. I look forward to connecting with you!

<div class="contact-methods" style="margin-top: 1.5em;">
  {% assign email_link = site.author.links | where: "label", "Email" | first %}
  {% if email_link %}
  <p>
    <i class="fas fa-fw fa-envelope-square" aria-hidden="true"></i>
    <strong>Email:</strong> <a href="{{ email_link.url }}">{{ email_link.url | remove_first: 'mailto:' }}</a>
  </p>
  {% endif %}

  {% assign linkedin_link = site.author.links | where: "label", "LinkedIn" | first %}
  {% if linkedin_link %}
  <p>
    <i class="fab fa-fw fa-linkedin" aria-hidden="true"></i>
    <strong>LinkedIn:</strong> <a href="{{ linkedin_link.url }}" target="_blank" rel="noopener noreferrer">{{ linkedin_link.url | remove_first: 'https://www.' }}</a>
  </p>
  {% endif %}

  {% assign github_link = site.author.links | where: "label", "GitHub" | first %}
  {% if github_link %}
  <p>
    <i class="fab fa-fw fa-github" aria-hidden="true"></i>
    <strong>GitHub:</strong> <a href="{{ github_link.url }}" target="_blank" rel="noopener noreferrer">{{ github_link.url | remove_first: 'https://www.' }}</a>
  </p>
  {% endif %}

  {% assign phone_link = site.author.links | where: "label", "Phone/WhatsApp" | first %}
  {% if phone_link %}
  <p>
    <i class="fas fa-fw fa-phone-square-alt" aria-hidden="true"></i>
    <strong>Phone/WhatsApp:</strong> {{ phone_link.url | remove_first: 'tel:' }}
  </p>
  {% endif %}

  <p style="margin-top: 1em;">
    <i class="fas fa-fw fa-home" aria-hidden="true"></i>
    <strong>Home Town:</strong> Johor, Malaysia <!-- Assuming this is static or you add it to _config.yml -->
  </p>
</div>