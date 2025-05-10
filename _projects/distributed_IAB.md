---
title: "Distributed Link Scheduling for IAB Network By Considering Message Exchange Delay"
permalink: /distributed_IAB/
date: 2025-05-10
excerpt: "A master's thesis project focusing on a distributed, pipelined resource management architecture for IAB networks to minimize end-to-end packet delay, considering information propagation latency and half-duplex constraints."
header:
  teaser: /assets/images/automation_banner.png # Placeholder, as in your template
sidebar:
  - title: "Role"
    text: "Master's Researcher / Thesis Student"
  - title: "Core Technologies"
    text: "Wireless Networks (IAB), Distributed Systems, Network Scheduling, Resource Management, TDMA, DAG Modeling, Simulation (conceptual)"
  - title: "Institution"
    text: "National Taipei University of Technology, Department of Electronic Engineering"
  - title: "Duration"
    text: "Approx. 2 Years (Typical for Master's Thesis)"
tags:
  - IAB Networks
  - 5G/6G
  - Wireless Backhaul
  - Distributed Control
  - Network Scheduling
  - Low Latency
  - Resource Management
  - TDMA
---

## Project Overview

Integrated Access and Backhaul (IAB) networks are a key technology for flexible and cost-effective 5G/6G deployments. However, managing resources efficiently in these multi-hop wireless networks presents significant challenges. These include handling half-duplex constraints, mitigating interference, dealing with dynamic topologies (often modeled as Directed Acyclic Graphs - DAGs), and minimizing end-to-end packet delay. Centralized solutions can suffer from scalability issues and single points of failure, while distributed solutions must carefully manage coordination overhead and information propagation delays.

This master's thesis project aimed to develop a novel distributed resource management framework. The primary objective was to minimize end-to-end packet delay for downlink traffic in IAB networks by explicitly addressing the challenges of distributed decision-making, multi-path routing opportunities, and inherent information latency in multi-hop environments.

**Disclaimer:** The research and findings described herein are part of a master's thesis and, at the time of this writing, have not yet been submitted for formal publication or peer review.

## My Contributions & Key Responsibilities

As the sole researcher for this master's thesis, my responsibilities encompassed:
*   Conducting an extensive literature review of existing resource management schemes for IAB networks, identifying research gaps, particularly in distributed approaches that rigorously account for information propagation delays.
*   Formulating the system model, including the network topology (DAG), node operational modes (Transmit, Receive, Idle under half-duplex constraints), and communication assumptions (TDMA).
*   Defining the core network objective: minimization of average end-to-end packet delay.
*   Designing a novel distributed operational architecture to manage link scheduling and packet forwarding in a coordinated yet decentralized manner.
*   Conceptualizing the simulation methodology and performance metrics for evaluating the proposed framework against existing approaches.
*   Authoring the comprehensive master's thesis document detailing the research.

## Technical Approach

The project proposed a distributed forwarding mechanism operating on a cyclical, pipelined architecture within each Transmission Time Interval (TTI). Key aspects of the technical approach included:

*   **Distributed Control:** Empowering individual IAB nodes to make local scheduling and forwarding decisions, enhancing scalability and adaptability.
*   **Pipelined Operational Architecture:** Each TTI was structured into distinct phases:
    1.  **Information Exchange:** Nodes share necessary control information with neighbors.
    2.  **Operation Mode Decision:** Nodes deterministically resolve their operational mode (e.g., transmit, receive, idle) for the current TTI based on exchanged information and pre-calculated priorities, respecting half-duplex constraints.
    3.  **Link Scheduling (Proactive):** Nodes calculate link activation priorities for a *future* TTI (specifically, t+2), to account for multi-hop information propagation delays.
    4.  **Packet Forwarding Execution:** Nodes perform data transmission or reception based on the decided operation mode for the current TTI.
*   **Information Latency Management:** The two-TTI pipeline for link scheduling (scheduling in TTI `t` for execution in TTI `t+2`) was a core design choice to ensure that all necessary coordination information, even if relayed over multiple hops, is available before execution.
*   **Conflict Resolution:** A deterministic process was designed for nodes to select their operational mode, ensuring conflict-free link activations based on shared link priorities.
*   **Dynamic Routing Support:** The framework allowed for local forwarding decisions, enabling adaptability to changing network conditions and supporting potential multi-path opportunities.

*(Specific algorithms for link weight calculation or next-hop selection, as detailed in Chapter 5 of the thesis, are omitted here as per the request.)*

## Impact & Results (Generalized)

The research aimed to achieve the following impacts:
*   **Reduced Packet Delay:** The primary goal was to demonstrate a significant reduction in average end-to-end packet delay in IAB networks compared to other distributed schemes that do not explicitly manage information latency.
*   **Improved Scalability:** By adopting a distributed architecture, the solution was designed to be more scalable for larger IAB deployments than centralized approaches.
*   **Enhanced Robustness:** Decentralized decision-making can lead to increased robustness against single node failures (though not the primary focus, it's an inherent benefit).
*   **Practical Framework:** The proposed architecture provides a practical framework for implementing distributed resource management in real-world IAB systems by considering operational constraints like signaling delays.

## What I Learned

This project provided significant learning in several areas:
*   **Deep Dive into IAB Networks:** Gained in-depth knowledge of IAB architectures, challenges (half-duplex, interference, multi-hop delays), and their role in next-generation wireless systems.
*   **Distributed Systems Design:** Acquired practical understanding of designing distributed algorithms, managing state consistency, and handling communication delays in resource-constrained environments.
*   **Network Modeling and Abstraction:** Developed skills in modeling complex network behaviors (e.g., DAGs, TDMA, operational modes) for analysis and system design.
*   **Pipelined Architectures:** Understood the benefits and complexities of using pipelined processing to manage sequential dependencies and latencies in control systems.
*   **Problem Formulation and Solution Design:** Honed abilities in identifying specific research problems, defining clear objectives, and systematically designing a solution.
*   **Academic Research and Writing:** Mastered the process of conducting thorough literature surveys, structuring a research thesis, and clearly articulating complex technical concepts.