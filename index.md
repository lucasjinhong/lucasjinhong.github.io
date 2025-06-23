---
layout: single
permalink: /
author_profile: true
entries_layout: grid
---

<div style="text-align: center; margin-bottom: 2em;">
  <h1>KOH JIN HONG, LUCAS</h1>
  <p class="lead" style="font-size: 1.2em; color: #555;">Master of Science Candidate, Electronic Engineering</p>
  <p class="lead" style="font-size: 1.1em; color: #666;">Cloud Infrastructure (GCP, AWS) | DevOps | Network Engineering</p>
  <p style="margin-top: 1em;">
    <a href="{{ "/assets/Resume_Lucas.pdf" | relative_url }}" class="btn btn--success btn--large" target="_blank" download>Download Resume (PDF)</a>
  </p>
</div>

## Summary
{% capture resume_summary %}
Proactive M.S. in Electronic Engineering candidate specializing in network engineering and automation. Proven expertise in building and managing scalable infrastructure using GCP, Kubernetes, Terraform, and Docker. Experienced in configuring FortiGate firewalls, automating CI/CD pipelines, and troubleshooting complex network issues. Eager to apply skills in cloud infrastructure and network automation to a challenging DevOps or Network Engineering role.
{% endcapture %}
{{ resume_summary | markdownify }}

---

## Education

### Master of Science, Electronic Engineering
*Sep 2023 - Expected Aug 2025*
**National Taipei University of Technology**
*   **Network Infrastructure & Security:** Gained hands-on experience by configuring and deploying FortiGate security tunnels and firewalls for Taiwan Space Agency projects. Resolved critical network connectivity issues (IP conflicts, configuration errors) at the university's networking centre to ensure operational uptime.
*   **Graduate Research (5G/IAB Networks):** Researched and authored a graduate paper on Distributed Link Scheduling for IAB Networks, investigating Layer 2 5G architecture and developing an optimized packet forwarding algorithm.

### Bachelor of Science, Electronic Engineering
*Sep 2019 - Jun 2023*
**National Taipei University of Technology**
*   **Full-Stack Web Service:** Architected and deployed a secure, full-stack web service using Node.js for the backend, MongoDB for the database, and AWS for cloud hosting.

---

## Experience

### Junior Firmware Engineer (Intern)
*Sep 2022 - Jun 2023*
**Sierra Wireless**
*   **Automated Testing & CI/CD:** Engineered and deployed an automated firmware testing testbed using Docker, Jenkins, and Ansible. Orchestrated CI/CD pipelines to automate nightly validation workflows, significantly improving testing efficiency.
*   **Quality Assurance & Defect Triage:** Executed comprehensive validation and regression testing for new firmware releases. Meticulously identified, documented, and triaged defects using Jira to ensure high product quality.

---

## Projects

### Scalable Cloud Application with Automated DevOps Pipeline
*   **CI/CD Architecture:** Architected an automated CI/CD pipeline on **GCP** using **GitHub Actions** and **Kubernetes (GKE)** to achieve zero-downtime deployments via rolling updates.
*   **Infrastructure as Code (IaC):** Provisioned all cloud infrastructure (GKE, VPC) as code using **Terraform**, creating a version-controlled, scalable, and reproducible environment from the ground up.
*   **Pipeline Security:** Secured the CI/CD pipeline with **GCP Workload Identity Federation**, implementing a modern, keyless authentication method to eliminate the risk of static credentials.

---

## Skills
*   **Cloud & Containerization:** GCP, AWS, Kubernetes (GKE), Docker, Terraform
*   **Automation & CI/CD:** Python, Bash, Ansible, Jenkins, GitHub Actions, CI/CD Design
*   **Networking & Security:** TCP/IP, FortiGate (Firewalls, Tunnels), Network Troubleshooting, 5G/IAB Architecture, CCNA (In Progress)
*   **Backend & Development:** Node.js, JavaScript, C/C++, MongoDB, RESTful APIs
*   **Tools & Platforms:** Git, Linux, Jira
*   **Languages:** Chinese (Fluent), English (TOEIC: 825)

---

<h2 id="my-projects">Portfolio Showcase</h2>
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
    <strong>Nationality:</strong> Malaysian
  </p>
</div>