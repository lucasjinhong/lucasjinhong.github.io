---
title: "Smart Cleaning Robot: Secure User Authentication Backend"
permalink: /projects/smart-robot-auth/
date: 2022-06-18
excerpt: "Developed a robust Node.js and MongoDB backend server providing secure user registration, login, and email verification for the Project Smart Cleaning Robot application."
header:
  teaser: /assets/images/smart_banner.png
sidebar:
  - title: "Role"
    text: "Backend Developer / System Implementer"
  - title: "Core Technologies"
    text: "Node.js, Express.js, MongoDB, Mongoose, REST APIs, AWS EC2, PM2"
  - title: "Context"
    text: "Personal Project"
  - title: "Duration"
    text: "April 2022 - June 2022"
tags:
  - Node.js
  - Express.js
  - MongoDB
  - Authentication
  - REST API
  - Backend Development
  - AWS
  - Security
---

## Project Overview

This project involved building the complete backend authentication system for a "Smart Cleaning Robot" application. The primary objective was to create a secure, scalable, and reliable RESTful API to handle all user management functions, including registration with email verification, login, and token-based session management.

The system was architected to be deployed on AWS EC2, managed with PM2, and connected to a MongoDB Atlas database, providing a production-ready foundation for the client-facing application.

## Source Code

The complete server-side source code is hosted on GitHub:
*   [lucasjinhong/Project_Smart_Cleaning_Robot](https://github.com/lucasjinhong/Project_Smart_Cleaning_Robot)

## My Contributions & Key Responsibilities

*   **Full-Stack Backend Development:** Designed and implemented the entire server-side application using Node.js and Express, including the REST API, routing, and middleware.
*   **Secure Authentication & User Management:** Engineered the complete user authentication workflow, featuring secure password hashing (bcrypt), email verification via an external mail service, and stateless session management using JSON Web Tokens (JWT).
*   **Database & Deployment Architecture:** Defined the Mongoose data models for user accounts, configured the connection to a MongoDB Atlas cluster, and documented the deployment process for AWS EC2 using the PM2 process manager.
*   **Security & Configuration:** Ensured a secure design by externalizing all sensitive credentials (database URIs, API keys, JWT secrets) into environment variables (`.env`), keeping them out of the versioned codebase.

## Technical Approach

The backend was architected using a modern, scalable Node.js stack, centered around a clear separation of concerns.

1.  **API Layer (Express.js):** The core of the application, responsible for defining RESTful API endpoints, handling incoming HTTP requests, validating request bodies, and orchestrating responses.

2.  **Data Persistence Layer (MongoDB & Mongoose):** Mongoose was used as the Object Data Modeler (ODM) to define a clear schema for user data and to manage all CRUD (Create, Read, Update, Delete) operations with the MongoDB Atlas database.

3.  **Authentication Workflow:**
    *   **Registration:** A user registers, their password is securely hashed, and a verification email is dispatched.
    *   **Login:** Upon successful credential validation against the stored hash, a signed JWT is issued to the client.
    *   **Authenticated Access:** The client includes the JWT in the `Authorization` header for all subsequent requests to protected endpoints, where it is validated by server-side middleware.

## Key Challenges Addressed

*   **Securing User Credentials:** Implemented industry-standard security by using bcrypt to hash and salt user passwords, ensuring they are never stored in plaintext.
*   **Managing Application Secrets:** Solved the problem of hardcoded credentials by externalizing all sensitive keys and passwords into a `.env` file, a critical security practice.
*   **Stateless Session Management:** Utilized JSON Web Tokens (JWTs) to create a scalable, stateless authentication system that works seamlessly in distributed or load-balanced environments.
*   **Ensuring Developer Usability:** Created comprehensive `README.md` documentation detailing the setup and deployment process, enabling easy onboarding and environment replication.

## Impact & Results

*   **Delivered a Production-Ready Authentication Backbone:** The system provides all core functionalities required for secure user management, serving as a reliable foundation for the main application.
*   **Established a Secure by Design System:** By implementing password hashing and proper secret management from the start, I built a system with a strong security posture.
*   **Enabled Client-Side Development:** Provided a clean, well-defined RESTful API that allowed client-side developers to easily integrate user authentication features.

## What I Learned

*   **End-to-End Backend Development:** Gained comprehensive, hands-on experience building a Node.js backend from initial design to deployment, covering API creation, database integration, and security.
*   **Mastery of Core Authentication Patterns:** Solidified my understanding and implementation of essential web security concepts, including password hashing, email verification, and JWT-based authentication.
*   **Cloud Deployment Fundamentals:** Acquired practical knowledge in deploying and managing a Node.js application on cloud infrastructure (AWS EC2) using a process manager (PM2) for resilience.
*   **The Importance of a Security-First Mindset:** This project reinforced the critical need to prioritize security in every aspect of backend development, especially when handling user data.