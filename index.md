---
layout: single
permalink: /
author_profile: true
entries_layout: grid
---

<div style="text-align: center; margin-bottom: 2em;">
  <h1>{{ site.name }}</h1> <!-- KOH JIN HONG, LUCAS -->
  <p class="lead" style="font-size: 1.2em; color: #555;">M.S. Computer Science Graduate | Software Engineer</p>
  <p class="lead" style="font-size: 1.1em; color: #666;">Backend, Cloud (AWS), Automation, Network Infrastructure & Security</p>
  <p style="margin-top: 1em;">
    <a href="{{ "/assets/Resume_Lucas.pdf" | relative_url }}" class="btn btn--success btn--large" target="_blank" download>Download Resume (PDF)</a>
  </p>
</div>

## Summary
{% capture resume_summary %}
Highly motivated M.S. Electronic Engineering Graduate (expected Aug 2025) with a strong foundation in software engineering, specializing in backend systems, cloud (AWS), automation, and network infrastructure. Proven ability in the full development lifecycle, network configuration, and troubleshooting. Eager to apply expertise in Python, Node.js, AWS, Docker, and Jenkins to a challenging Software Engineer role.
{% endcapture %}
{{ resume_summary | markdownify }}

---

## Education

### Master of Science, Electronic Engineering
*2023 - Present*
**National Taipei University of Technology**
*   **Researched & Authored Graduate Paper:** Investigated Distributed Link Scheduling for IAB Networks, focusing on Layer 2 5G architecture and implementing an optimized packet forwarding algorithm for half-duplex scenarios.
*   **Network Security (Taiwan Space Agency Projects):** Configured and deployed FortiGate security tunnels and firewalls, enhancing network security for critical infrastructure.
*   **Teaching Assistant(Python, C, Algorithms):** Served as Teaching Assistant for Master's level courses, providing student support and assisting instructors with course materials.
*   **Network Support (University Computer Networking Centre):** Resolved network connectivity issues, including IP conflicts and configuration errors, ensuring operational uptime for university users.

### Bachelor of Science, Electronic Engineering
*2019 - 2023*
**National Taipei University of Technology**
*   **Backend System Development (Node.js, MongoDB, AWS):** Architected and implemented a secure and scalable user login system server. Leveraged Node.js for server-side logic, MongoDB for efficient user data management, and AWS for robust cloud-based backend infrastructure.
*   **Game Prototyping & Python Architecture:** Spearheaded the development of a visual novel game prototype by architecting its core Python-based engine and game flow. Implemented the user interface and interactive elements using the PyQt6 framework.


---

## Experience

### Junior Firmware Engineer (Intern)
*2022 - 2023*
**Sierra Wireless**
*   **Automated Firmware Validation Testbed (Docker, Jenkins, Ansible):** Engineered and deployed a comprehensive automated firmware testing testbed. Leveraged Docker for containerization, Jenkins for CI/CD pipelines automating nightly validation tests, and Ansible for streamlined environment provisioning and automated test execution during testbed development. This significantly enhanced workflow efficiency and test reliability.
*   **Firmware Validation & Regression Testing:** Executed comprehensive validation and regression testing for new firmware releases. Meticulously identified, documented, and reported software defects using bug tracking systems (e.g., Jira), ensuring high product quality prior to deployment.
---

## Skills
*   **Programming Languages:** Python, JavaScript (Node.js), C, C++
*   **Backend & API Development:** Node.js, MongoDB, AWS (EC2), RESTful APIs, JWT
*   **Automation & DevOps:** Docker, Jenkins, Ansible, CI/CD Pipelines
*   **Networking & Security:** TCP/IP, FortiGate (Firewalls, Security Tunnels), Network Configuration, Network Troubleshooting, 5G Architecture Concepts, IAB Networks
*   **Development Tools & Platforms:** Git, Linux, Jira
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
I'm actively seeking challenging opportunities and am always open to discussing innovative projects, collaborations, or roles where I can contribute my skills. Please feel free to reach out through any of the channels below. I look forward to connecting with you!

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
    <strong>Nationality:</strong> Malaysian <!-- Assuming this is static or you add it to _config.yml -->
  </p>
</div>
