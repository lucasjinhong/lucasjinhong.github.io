---
title: "Topogen - Automated Network Topology Generator"
permalink: /projects/topogen/
date: 2024-12-27
excerpt: "A Python package for automatically generating and setting up network topologies, particularly for Integrated Access and Backhaul (IAB) scenarios, from a graph-based input."
header:
  teaser: /assets/images/topogen_banner.png
sidebar:
  - title: "Role"
    text: "Creator / Lead Developer"
  - title: "Core Technologies"
    text: "Python, Setuptools"
  - title: "Company"
    text: "Personal Project (lucasjinhong)"
  - title: "Duration"
    text: "Ongoing" # Or specify timeframe
tags:
  - Python
  - Network Topology
  - Network Simulation
  - IAB (Integrated Access and Backhaul)
  - Automation
  - Graph Theory
---

## Project Overview

Topogen is a Python package designed to streamline the creation of network topologies. It automates the process of generating interconnected nodes and links based on a user-defined graph structure. This is particularly useful for researchers and developers working on network simulations, performance analysis, or protocol design, especially in contexts like Integrated Access and Backhaul (IAB) networks.

The package takes a simple matrix representation of a network grid as input and constructs a `Topo` object. This object encapsulates:
*   `Node` objects with attributes like type (donor/node), coordinates, parent/child relationships, and connected links.
*   `Link` objects connecting nodes, featuring calculated data rates based on distance and configurable physical layer parameters (defaulting to the Shannon Capacity formula).
*   Information about all possible paths from a designated 'donor' node to all other nodes in the topology.
*   Identification of 'conflict nodes' which might interfere with each other.

Topogen aims to provide a flexible and extensible foundation for building and analyzing various network configurations.

## Source Code

The complete source code for Topogen, including all modules and configuration files, is hosted on GitHub:
*   [lucasjinhong/topogen](https://github.com/lucasjinhong/topogen)

## My Contributions & Key Responsibilities

As the creator and primary developer of Topogen, my responsibilities encompassed the entire development lifecycle:

*   **Conceptualization and Design:** Defining the core abstractions (`Node`, `Link`, `Topo`) and the overall architecture of the package.
*   **Algorithm Development:**
    *   Implementing the logic to parse the input graph and instantiate `Node` objects with appropriate coordinates and connectivity (`generate_nodes_from_graph`).
    *   Developing the mechanism for establishing links between nodes based on proximity (`max_dist_to_connect_nodes`) and hierarchical relationships.
    *   Creating the data rate calculation module, incorporating physical distance (`size_of_grid_len`) and a configurable channel model (e.g., Shannon Capacity from `config.py`).
    *   Implementing pathfinding algorithms (DFS) to discover all routes from the donor node (`find_paths_from_donor_to_all_nodes`).
    *   Designing the logic for identifying conflict nodes.
*   **Configuration Management:** Implementing the system to load physical layer parameters (bandwidth, Tx power, noise, etc.) from an external `channel_config.yaml` file, allowing for easy customization.
*   **Utility Functions:** Developing helper functions for tasks like distance calculations, graph manipulation, and YAML data parsing.
*   **Error Handling:** Integrating robust error checking to guide users and ensure valid inputs.
*   **Packaging and Distribution:** Setting up the project using `setuptools` for easy installation and use as a Python package.
*   **Testing:** (Implied by the `tests` directory) Developing unit tests to ensure the correctness and reliability of different modules and functionalities.

## Technical Approach

The core of Topogen revolves around transforming a high-level grid representation into a detailed network topology object.

1.  **Input:** The process starts with a 2D Python list (`graph`) where `1`s denote potential node locations and `0`s are empty spaces. A key constraint is that the first row must contain exactly one `1`, designated as the 'donor' node.

2.  **Node Generation (`generate_nodes_from_graph`):**
    *   A 'donor' `Node` is created first.
    *   A breadth-first-like traversal (using a queue) explores the graph from the donor.
    *   For each `1` encountered in the grid, a new `Node` object is created if it's within `max_dist_to_connect_nodes` of an existing node being processed. Coordinates are assigned based on its grid position.
    *   Parent-child relationships are established based on the connection logic and `tree_type` (DAG or TREE).

3.  **Link Generation (`generate_links`):**
    *   Once nodes and their parent-child relationships are set, `Link` objects are created between each parent and its children.
    *   The physical distance between connected nodes is calculated using their coordinates and `size_of_grid_len` (scaling factor for grid units to meters).
    *   This distance is then fed into a data rate formula (default: Shannon Capacity from `config.py`, using parameters from `channel_config.yaml`, or a user-provided custom function) to determine the `data_rate_bps` for the link.

4.  **Pathfinding (`find_paths_from_donor_to_all_nodes`):**
    *   A Depth-First Search (DFS) algorithm is employed, starting from the 'donor' node, to find all unique paths to every other node in the topology.

5.  **Additional Setup:**
    *   Conflict nodes are identified based on shared parents or children.
    *   The initial graph matrix is updated to replace `1`s with actual node names for easier inspection.

6.  **Modularity:** The codebase is structured into:
    *   `model/`: Contains core classes like `Node`, `Link`, and `Topo`.
    *   `utils/`: Helper functions for common tasks (error handling, math, graph operations).
    *   `config/`: Manages physical layer parameters and default formulas.

**Key Challenges Addressed:**

*   **Abstract to Concrete Mapping:** Translating the simple grid input into a rich set of interconnected objects with meaningful attributes.
*   **Realistic Link Characterization:** Implementing a data rate model that considers physical distance and configurable channel parameters, rather than assuming fixed capacities.
*   **Connectivity Logic:** Ensuring nodes connect based on proximity rules while respecting the desired `tree_type` (DAG/TREE).
*   **Flexibility and Extensibility:** Designing the system to allow users to inject custom data rate formulas and easily modify channel parameters via `channel_config.yaml`.
*   **Package Usability:** Structuring the project with `setuptools` for straightforward installation and integration into other Python projects.

## Impact & Results (Generalized)

Topogen provides significant value by:

*   **Automating Tedious Setup:** Drastically reduces the manual effort required to define and configure network topologies for simulations or analytical studies.
*   **Enabling Rapid Prototyping:** Allows users to quickly generate and iterate on different network structures and parameter settings.
*   **Facilitating Reproducible Research:** By codifying the topology generation process, it ensures that network setups can be consistently reproduced.
*   **Providing a Foundation for Advanced Analysis:** The generated `Topo` object, with its detailed node, link, and path information, serves as a robust input for various network analysis tools or custom simulation scripts.
*   **Improving Understanding of Network Dynamics:** By allowing easy manipulation of parameters like node density, connectivity range, and physical channel properties, users can better explore their impact on network behavior.

## What I Learned

Developing Topogen has been a valuable learning experience, reinforcing and expanding my skills in several areas:

*   **Object-Oriented Design:** Deepened understanding of how to model complex systems (like a network) using classes and objects, managing their relationships and behaviors.
*   **Algorithm Implementation:** Gained practical experience in implementing graph traversal algorithms (DFS for pathfinding) and custom logic for node and link creation.
*   **Python Package Development:** Mastered the use of `setuptools` for creating installable Python packages, including managing dependencies and entry points (though not explicitly shown, it's a standard part of `setup.py`).
*   **Configuration Management:** Learned the importance of separating configuration (like channel parameters) from code for flexibility and ease of modification, utilizing YAML for this purpose.
*   **API Design:** Considered how users would interact with the `generate_topology_from_graph` function and the resulting `Topo` object, aiming for an intuitive and useful interface.
*   **Modular Programming:** Practiced breaking down a complex problem into smaller, manageable modules (`model`, `utils`, `config`) for better organization and maintainability.
*   **Mathematical Modeling in Code:** Translating physical concepts like the Shannon Capacity formula and distance calculations into functional Python code.
*   **The Importance of Testing:** (Even if not explicitly detailed here) The presence of a `tests` directory underscores the iterative process of writing code and verifying its correctness.