---
title: Scalable Visual Novel Engine with Automated DevOps on GCP
permalink: /portfolio/gcp-devops-pipeline/
date: 2025-05-27
excerpt: "Architected and implemented a fully automated, scalable deployment platform on Google Cloud using Terraform, GKE, and GitHub Actions. The system supports a containerized Python application with zero-downtime rolling updates."
header:
  teaser: /assets/images/gcp_devops_banner.png
sidebar:
  - title: "Role"
    text: "DevOps Architect / Sole Developer"
  - title: "Core Technologies"
    text: "GCP, Kubernetes (GKE), Terraform, Docker, GitHub Actions, Python, Workload Identity Federation"
  - title: "Context"
    text: "Personal project to build and showcase a professional-grade, end-to-end DevOps workflow."
  - title: "Duration"
    text: "In progess"
tags:
  - GCP
  - Kubernetes
  - Terraform
  - Docker
  - CI/CD
  - DevOps
  - IaC
  - GitHub Actions

---

## Project Overview

This project's primary goal was to design and build a robust, scalable, and fully automated cloud infrastructure to host a web-based Visual Novel Engine. While the engine itself is web-based application, the core focus was on creating a professional DevOps workflow from the ground up.

The entire cloud environment on Google Cloud Platform (GCP) is managed declaratively with Terraform. The application is containerized with Docker, orchestrated on Google Kubernetes Engine (GKE), and deployed automatically via a CI/CD pipeline built with GitHub Actions, enabling rapid iteration and high availability.

## Source Code & Live Demo

*   **Live Application:** [http://34.81.249.188](http://34.81.249.188)
*   **GitHub Repository:** [lucasjinhong/vn-prototype-project](https://github.com/lucasjinhong/vn-prototype-project) *(Note: Please update with the correct link if different)*

## My Contributions & Key Responsibilities

*   **Infrastructure as Code (IaC) Provisioning:** Authored Terraform configurations to declaratively define and manage all GCP resources, including the GKE cluster, VPC networking, and Google Artifact Registry.
*   **CI/CD Pipeline Automation:** Designed and implemented a complete CI/CD pipeline using GitHub Actions. The workflow automatically builds, tests, and deploys the application to Kubernetes upon every push to the `main` branch.
*   **Containerization & Orchestration:** Containerized the Python application using a multi-stage `Dockerfile` for a lean production image. Wrote Kubernetes manifests (`deployment.yaml`, `service.yaml`) to manage the application's lifecycle, networking, and achieve zero-downtime rolling updates.
*   **Secure Cloud Integration:** Implemented **GCP Workload Identity Federation** to enable a secure, keyless authentication mechanism between GitHub Actions and GCP, eliminating the need for long-lived service account keys.
*   **Scalable Application Architecture:** Designed the system to be horizontally scalable and self-healing by leveraging Kubernetes' native capabilities.

## Technical Approach

The architecture is centered around a "Git-to-Production" automated flow, where a `git push` is the only manual step required to deploy new changes.

1.  **Foundation (Terraform):** The entire GCP infrastructure is provisioned by running `terraform apply`. This creates the GKE cluster, Artifact Registry for storing Docker images, and all necessary IAM permissions. This approach ensures the environment is reproducible and version-controlled.

2.  **Containerization (Docker):** The Application is packaged into a lightweight, portable Docker image. This decouples the application from the underlying infrastructure.

3.  **Automation (GitHub Actions CI/CD):** When code is pushed to the `main` branch, a GitHub Actions workflow is triggered:
    *   **Authenticate:** The job securely authenticates with GCP using the pre-configured Workload Identity Provider.
    *   **Build & Push:** It builds a new Docker image, tags it with the commit SHA, and pushes it to the Google Artifact Registry.
    *   **Deploy:** The workflow uses `kubectl` to apply the updated Kubernetes deployment manifest, specifying the new image tag. GKE then handles a **rolling update**, gracefully replacing old pods with new ones without any service interruption.

4.  **Orchestration (Kubernetes/GKE):** GKE runs the application containers. The `Service` manifest exposes the application to the internet via a Load Balancer with a static IP. The `Deployment` manifest ensures the desired number of replicas are running and defines the strategy for updates and self-healing.

## Key Challenges Addressed

*   **Automating Infrastructure Provisioning:** Manually configuring cloud resources is error-prone and not scalable. **Solution:** Used **Terraform** to manage all infrastructure as code, which allows for versioning, peer review, and consistent recreation of the entire environment.

*   **Securing the CI/CD Pipeline:** Storing static service account keys as GitHub secrets is a major security risk. **Solution:** Implemented **GCP Workload Identity Federation**. This modern approach allows GitHub Actions to securely impersonate a GCP service account using short-lived tokens, completely avoiding the need for static credentials.

*   **Achieving Zero-Downtime Deployments:** Pushing updates should not cause service interruptions for users. **Solution:** Leveraged **Kubernetes' rolling update** strategy. By gradually replacing old application pods with new ones, the service remains available and responsive throughout the entire deployment process.

## Impact & Results

*   **Fully Automated Workflow:** Created a true hands-off CI/CD pipeline, significantly reducing manual deployment effort and the risk of human error.
*   **High Availability & Scalability:** The GKE-based architecture ensures the application is resilient and can be easily scaled horizontally to handle increased load by simply adjusting the replica count.
*   **Infrastructure Consistency:** By using Terraform (IaC), I eliminated "environment drift" and can spin up an identical copy of the infrastructure in minutes.
*   **Enhanced Security:** Implemented a best-practice, keyless authentication method for the CI/CD pipeline, drastically improving the project's security posture.

## What I Learned

*   **End-to-End DevOps Implementation:** Gained deep, practical experience in connecting all the pieces of a modern DevOps toolchain: source control (Git), CI/CD (GitHub Actions), IaC (Terraform), containerization (Docker), and orchestration (Kubernetes).
*   **The Power of Declarative Systems:** Truly understood the value of defining the "what" (e.g., "I need a 3-node GKE cluster") with tools like Terraform and Kubernetes, and letting the system figure out the "how."
*   **Modern Cloud Security Practices:** Learned to implement and appreciate the security benefits of Workload Identity Federation over traditional key-based authentication.
*   **Kubernetes in Practice:** Moved beyond theory to implement practical deployment strategies, service exposure, and lifecycle management within Kubernetes. This project solidified my understanding of how GKE provides a robust platform for running production applications.