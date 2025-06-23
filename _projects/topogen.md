---

title: "Topogen - Automated Network Topology Generator"
permalink: /projects/topogen/
date: 2024-05-15
excerpt: "A Python package that automates the generation of complex network topologies from simple graph-based inputs, designed for researchers and network engineers in fields like Integrated Access and Backhaul (IAB)."
header:
  teaser: /assets/images/topogen_banner.png
sidebar:
  - title: "Role"
    text: "Creator / Lead Developer"
  - title: "Core Technologies"
    text: "Python, Setuptools, Pytest, PyYAML, Graph Algorithms"
  - title: "Context"
    text: "Personal Project"
  - title: "Duration"
    text: "In Progress"
tags:
  - Python
  - Network Simulation
  - Automation
  - Graph Theory
  - IAB
  - Package Development
---

## Project Overview

Topogen is a Python package designed to automate the complex and time-consuming process of creating network topologies for simulation and analysis. It empowers researchers and network engineers, particularly in emerging fields like Integrated Access and Backhaul (IAB), to rapidly generate and configure network structures from a simple grid-based input.

The package constructs a rich `Topo` object containing nodes, links with physically-aware data rates, all possible communication paths from a source 'donor' node, and other critical network information, providing a robust foundation for advanced analysis and experimentation.

## Source Code

The complete source code, including tests and configuration, is hosted on GitHub:
*   [lucasjinhong/topogen](https://github.com/lucasjinhong/topogen)

## My Contributions & Key Responsibilities

As the creator of Topogen, I was responsible for the entire project lifecycle:

*   **Full Lifecycle Development:** Led the project from conceptualization and architectural design to implementation, packaging, and testing.
*   **Graph Parsing & Node Generation:** Developed algorithms to translate a 2D grid representation into a network of `Node` objects with accurate coordinates and connectivity.
*   **Physics-Aware Link Modeling:** Implemented a data rate calculation engine that models link capacity based on physical distance and configurable channel parameters (e.g., Shannon Capacity), loaded from external YAML files.
*   **Pathfinding and Analysis:** Integrated a Depth-First Search (DFS) algorithm to discover all possible communication paths from a source 'donor' node, a crucial feature for routing analysis.
*   **Python Package Engineering:** Structured the project as an installable Python package using `setuptools` and developed a comprehensive test suite with `pytest` for robust validation.

## Technical Approach

Topogen transforms a high-level grid input into a detailed network object through a systematic process:

1.  **Grid-Based Input:** The user provides a simple 2D Python list representing the network grid, where a `1` denotes a node location. The 'donor' (source) node is identified in the first row.

2.  **Node & Link Generation:** The package traverses the grid to instantiate `Node` objects. It establishes parent-child relationships and creates `Link` objects between them based on proximity rules.

3.  **Data Rate Calculation:** For each link, the physical distance between nodes is calculated. This distance is then fed into a data rate formula (defaulting to the Shannon Capacity) that uses configurable physical layer parameters (bandwidth, Tx power, etc.) from a `channel_config.yaml` file. This produces a realistic, distance-dependent data rate for each link.

4.  **Path and Topology Analysis:** A DFS algorithm systematically finds all unique paths from the 'donor' to every other node. The final `Topo` object encapsulates this complete view of the network's structure and potential routes.

5.  **Rigorous Testing:** A suite of unit tests using `pytest` validates the correctness of core algorithms—including node generation, link creation, data rate calculations, and pathfinding—to ensure reliability and maintainability.

## Key Challenges Addressed

*   **Bridging Abstraction and Reality:** The core challenge was translating a high-level, abstract grid into a detailed, physics-aware network model. Topogen solves this by systematically building `Node` and `Link` objects with calculated, real-world attributes.
*   **Flexible and Realistic Link Modeling:** Instead of using fixed link capacities, I designed a system that calculates data rates based on physical distance and a configurable channel model, making simulations more realistic.
*   **Designing for Extensibility:** The package was architected to be highly customizable. By externalizing physical layer parameters to a YAML file and allowing for custom data rate functions, users can easily adapt Topogen to their specific research needs.

## Impact & Results

*   **Dramatically Reduces Setup Time:** Automates the laborious process of defining network topologies, allowing researchers to focus on analysis rather than manual configuration.
*   **Accelerates Research and Prototyping:** Enables users to quickly generate, test, and iterate on various network structures and physical parameters.
*   **Ensures Reproducibility:** By codifying the topology generation process, Topogen ensures that network experiments are consistent and reproducible, a cornerstone of credible research.
*   **Provides a Foundation for Advanced Analysis:** The detailed `Topo` object serves as a robust input for custom simulation scripts or network analysis tools.

## What I Learned

*   **Applied Object-Oriented Design:** Gained deep experience modeling a complex system (a network) with classes and objects, effectively managing their relationships and behaviors.
*   **Python Package Development Lifecycle:** Mastered the full lifecycle of Python package development, from structuring the project with `setuptools` to writing effective tests with `pytest` and managing configurations with `PyYAML`.
*   **Algorithm Implementation:** Implemented and adapted classic graph traversal algorithms (DFS) for a specific, practical application in network pathfinding.
*   **Designing an Intuitive API:** Focused on creating a clean and usable interface for the package, allowing users to generate complex topologies with a single function call.