---
title: "Distributed Link Scheduling for IAB Network By Considering Message Exchange Delay"
permalink: /distributed_iab/
date: 2025-05-10
excerpt: "A master's thesis project focusing on a distributed, pipelined resource management architecture for IAB networks to minimize end-to-end packet delay, considering information propagation latency and half-duplex constraints."
header:
  teaser: /assets/images/iab_banner.png
sidebar:
  - title: "Role"
    text: "Master's Researcher / Thesis Student"
  - title: "Core Technologies"
    text: "Wireless Networks (IAB), Distributed Systems, Network Scheduling, Resource Management, TDMA"
  - title: "Institution"
    text: "National Taipei University of Technology, Department of Electronic Engineering"
  - title: "Duration"
    text: "Ongoing"
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
*   Designing the novel distributed operational architecture to manage link scheduling and packet forwarding in a coordinated yet decentralized manner.
*   Developing the core 'Proposed Method' (the specific algorithms and logic) that enables the designed architecture to function effectively and achieve its objectives.

## Technical Approach

The project proposed a distributed forwarding mechanism operating on a cyclical, pipelined architecture within each Transmission Time Interval (TTI). This framework was designed to empower individual IAB nodes with local decision-making capabilities while ensuring network-wide coordination and adherence to operational constraints. Key aspects of the technical approach included:

*   **Distributed Control:** Empowering individual IAB nodes to make local scheduling and forwarding decisions, enhancing scalability and adaptability compared to centralized solutions.
*   **Pipelined Operational Architecture:** Each TTI was structured into distinct operational phases for information exchange, mode decision, future link scheduling, and current packet forwarding. This pipelining was central to managing dependencies and latencies.
*   **Proactive Information Latency Management:** The core of the design involved a multi-TTI pipeline for link scheduling. This ensured that necessary coordination information, even if relayed over several hops, was available at each node *before* it made decisions for the current TTI, thus explicitly accounting for propagation delays.
*   **Prioritized Conflict Resolution:** A deterministic process was designed for nodes to select their operational mode (e.g., Transmit, Receive, or Idle). This process utilized shared link priorities, calculated in advance, to ensure conflict-free link activations that respect half-duplex constraints.
*   **Support for Dynamic Forwarding:** While scheduling was coordinated, nodes retained local control over packet forwarding choices when a transmission opportunity arose. This allowed for adaptability to changing network conditions and could leverage local forwarding tables to support potential multi-path opportunities.
**Key Challenges Addressed:**
## Impact & Results (Generalized)

The research aimed to achieve the following impacts:
*   **Reduced Packet Delay:** The primary goal was to demonstrate a significant reduction in average end-to-end packet delay in IAB networks compared to other distributed schemes that do not explicitly manage information latency.
*   **Improved Scalability:** By adopting a distributed architecture, the solution was designed to be more scalable for larger IAB deployments than centralized approaches.
*   **Enhanced Robustness:** Decentralized decision-making is intended to improve overall network resilience, including better handling of severe congestion and increased robustness against single node failures.
*   **Practical Framework:** The proposed architecture provides a practical framework for implementing distributed resource management in real-world IAB systems by considering operational constraints like signaling delays.

## What I Learned

This project provided significant learning in several areas:
*   **Deep Dive into IAB Networks:** Gained in-depth knowledge of IAB architectures, challenges (half-duplex, interference, multi-hop delays), and their role in next-generation wireless systems.
*   **Distributed Systems Design:** Acquired practical understanding of designing distributed algorithms, managing state consistency, and handling communication delays in resource-constrained environments.
*   **Network Modeling and Abstraction:** Developed skills in modeling complex network behaviors (e.g., DAGs, TDMA, operational modes) for analysis and system design.
*   **Pipelined Architectures:** Understood the benefits and complexities of using pipelined processing to manage sequential dependencies and latencies in control systems.
*   **Problem Formulation and Solution Design:** Honed abilities in identifying specific research problems, defining clear objectives, and systematically designing a solution.
*   **Academic Research and Writing:** Mastered the process of conducting thorough literature surveys, structuring a research thesis, and clearly articulating complex technical concepts.