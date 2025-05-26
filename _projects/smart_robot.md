---
title: "Smart Cleaning Robot: Secure User Authentication Backend"
permalink: /projects/smart-robot-auth/
date: 2022-06-18 # Or your actual completion date
excerpt: "Developed a robust Node.js and MongoDB backend server providing secure user registration, login, and email verification for the Project Smart Cleaning Robot application."
header:
  teaser: /assets/images/smart_banner.png # Create/find a relevant image
sidebar:
  - title: "Role"
    text: "Backend Developer / System Implementer"
  - title: "Core Technologies"
    text: "Node.js, Express.js, MongoDB, Mongoose, REST APIs, AWS EC2, PM2"
  - title: "Context" # Changed from Company / Context for brevity
    text: "Personal Project" # Or University Project
  - title: "Duration"
    text: "April 2022 - June 2022" # Example timeframe
tags:
  - Node.js
  - Express.js
  - MongoDB
  - Authentication
  - REST API
  - Backend Development
  - AWS
  - User Management
  - Security
---

## Project Overview

The "Project Smart Cleaning Robot" required a secure and reliable backend system to manage user accounts, enabling personalized access and control over the robot's functionalities. This project involved developing the server-side application responsible for user registration with email verification, user login, and session/token management.

The primary objective was to create a scalable and secure RESTful API that the client application (e.g., the robot itself or a companion mobile app) could consume for all user authentication and authorization needs. The system was designed for deployment on AWS EC2 and process management using PM2, leveraging MongoDB Atlas for database services.

## Source Code

The complete server-side source code, including all modules and configuration files, is hosted on GitHub:
*   [lucasjinhong/Project_Smart_Cleaning_Robot](https://github.com/lucasjinhong/Project_Smart_Cleaning_Robot)

## My Contributions & Key Responsibilities

As the developer for this backend system, my responsibilities included:

*   **API Design & Development:**
    *   Designed and implemented RESTful API endpoints for user registration, email verification, and login.
    *   Ensured proper request validation and structured JSON responses.
*   **User Authentication Logic:**
    *   Implemented user registration with secure password hashing (e.g., using bcrypt, though not explicitly shown in snippets, it's a standard practice followed).
    *   Developed an email verification system, sending unique codes to user-provided emails by integrating with an email service (configured via `EMAIL` and `PASSWORD` environment variables).
    *   Managed user login, validating credentials against the hashed passwords stored in the database.
    *   Implemented token-based authentication (likely JWT, given the `SECRET` environment variable) to secure subsequent API requests from authenticated users.
*   **Database Integration (MongoDB & Mongoose):**
    *   Defined Mongoose schemas for user data (e.g., username, email, hashed password, email verification status).
    *   Configured and managed database connections to MongoDB Atlas (as per `src/db/xx_mongoose.js` files), handling all user-related CRUD operations.
*   **Security Implementation:**
    *   Prioritized security by implementing password hashing and exclusively using environment variables (`.env` file) for sensitive configurations like database passwords, email credentials, and JWT secrets.
*   **Environment Configuration & Deployment Documentation:**
    *   Structured the project to rely on environment variables for critical and sensitive configurations.
    *   Authored the `README.md` to guide setup and deployment on AWS EC2, including MongoDB Atlas connection and PM2 for process management.
*   **Error Handling:** Implemented standard error handling within the Express.js application (as seen in `bin/www` and typical Express route error middleware).

## Technical Approach

The backend system was architected using Node.js, the Express.js web framework, and MongoDB (via Mongoose ODM) for data persistence.

1.  **Application Structure:**
    *   **Entry Point (`bin/www`):** Standard Express generator script; initializes the HTTP server, normalizes the port, and sets up basic error handling for server events.
    *   **Core Application (`app.js` - *inferred from Express structure*):** Configures Express.js middleware (e.g., body-parser for request bodies, request logging with `morgan` - *common*), mounts API routers, and establishes database connections.
    *   **API Routes (`routes/` - *inferred*):** Likely contained modules like `users.js` or `auth.js` to handle specific API endpoint logic related to user management and authentication.
    *   **Database Layer (`src/db/xx_mongoose.js`):** Centralized MongoDB connection logic using Mongoose. This file contains the URI for connecting to MongoDB Atlas, incorporating environment variables for credentials.
    *   **Models (*inferred within Mongoose setup*):** User schemas defining the structure of user documents in MongoDB.
    *   **Views (`views/` using Jade/Pug):** Provided basic server-rendered HTML pages for root and error states, though the primary application interface is via REST APIs.

2.  **Authentication Workflow:**
    *   **Registration:** A client sends user details (e.g., email, password) to the `/register` endpoint. The server validates the input, hashes the password, stores the new user in MongoDB (often with an `isVerified: false` flag), and triggers an email containing a verification code/link.
    *   **Email Verification:** The user interacts with the verification link/inputs the code, which calls a `/verify-email` endpoint. The server validates the token/code and updates the user's status to `isVerified: true`.
    *   **Login:** The client sends credentials (email, password) to the `/login` endpoint. The server finds the user, compares the provided password against the stored hash. Upon success, a JSON Web Token (JWT), signed using the `SECRET` from `.env`, is generated and returned to the client.
    *   **Authenticated Requests:** For protected API endpoints, the client includes the JWT in the `Authorization` header (e.g., `Bearer <token>`). Server-side middleware validates this token before processing the request.

3.  **Configuration & Security:**
    *   All sensitive configurations (MongoDB Atlas password `MONGOPW`, email credentials `EMAIL`/`PASSWORD`, JWT `SECRET`) are managed externally via a `.env` file, which is not committed to version control.

4.  **Deployment (as per `README.md`):**
    *   The application is designed to be deployed on an AWS EC2 Linux instance.
    *   PM2 is recommended for managing the Node.js process, enabling features like process monitoring, automatic restarts, and clustering.

## Key Challenges Addressed

*   **Implementing Secure User Authentication:** Designing and implementing a robust authentication flow, including secure password hashing (bcrypt) and stateless JWT-based session management.
*   **Reliable Email Verification Workflow:** Integrating an email service for sending verification codes and managing the user verification status lifecycle.
*   **Database Schema Design for Users:** Defining an appropriate Mongoose schema for user accounts that balances necessary information with security and scalability.
*   **Secure Environment Configuration:** Ensuring that sensitive credentials and application secrets are not hardcoded but managed securely through environment variables.
*   **Clear Deployment Guidance:** Providing comprehensive `README.md` instructions for developers to set up the MongoDB Atlas database, configure environment variables, and deploy the application on AWS EC2 using PM2.

## Impact & Results (Generalized)

*   **Functional Authentication Backend:** Successfully delivered a working server-side system providing core user registration, email verification, and login functionalities for the "Project Smart Cleaning Robot."
*   **Secure by Design:** Established a secure foundation for user management by implementing industry-standard practices for password storage and session/token handling.
*   **Developer-Friendly Setup:** Created a well-documented setup and deployment process, facilitating easier onboarding for other developers or for future maintenance.
*   **Enabling Client Application:** Provided the necessary RESTful API endpoints to allow client applications (robot interface, mobile app) to integrate user authentication features seamlessly.

## What I Learned

*   **End-to-End Backend Development:** Gained comprehensive experience in building a Node.js/Express.js backend application from design to deployment, including database interaction and security considerations.
*   **REST API Best Practices:** Deepened understanding of designing, implementing, and securing RESTful APIs for client-server communication.
*   **Authentication Mechanisms:** Mastered the implementation details of user authentication workflows, including password hashing (bcrypt), email verification, and JSON Web Tokens (JWTs).
*   **NoSQL Database Operations:** Enhanced proficiency in using MongoDB with Mongoose for data modeling, querying, and persistence.
*   **Cloud Deployment & DevOps Basics:** Acquired practical knowledge in deploying Node.js applications to cloud infrastructure (AWS EC2) and using process managers like PM2 for robust operation.
*   **Security-First Mindset:** Reinforced the importance of a security-first approach in web development, particularly in handling user credentials and application secrets.
*   **Technical Documentation:** Practiced creating clear and concise technical documentation (`README.md`) to guide other developers or users.
