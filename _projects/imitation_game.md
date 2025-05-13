---
title: Visual Novel Game System Prototype (PyQt & Python)
permalink: /portfolio/imitation_game/
date: 2023-6-18
excerpt: "Developed the core system architecture for a Python-based visual novel game, integrating PyQt6 UI with dynamic story logic and game mechanics."
header:
  teaser: /assets/images/imitation_banner.png # Optional: Replace with a relevant image
sidebar:
  - title: "Role"
    text: "System Architect / Prototyper"
  - title: "Core Technologies"
    text: "Python, PyQt6, Custom Game Logic Modules"
  - title: "Team Structure"
    text: "Collaborated with a UI designer and a Novel/Story writer."
  - title: "Duration"
    text: "May 2023 - June 2023"
tags:
  - Python
  - PyQt6
  - Game Development
  - System Architecture
  - Prototyping
  - Visual Novel

---

## Project Overview

This project involved the creation of an interactive visual novel game. The game combines a narrative storyline with puzzle-solving elements based on computer science concepts like binary/hexadecimal conversions and logic gates. The goal was to create an engaging experience where players progress through different levels by solving these codec-based challenges.

As the system prototyper, my primary objective was to design and implement the foundational architecture that would seamlessly connect the user interface (developed by one team member) with the game's story logic and core mechanics (developed by another team member).

## Source Code

The complete source code, including all modules and configuration files, is hosted on GitHub:
*   [lucasjinhong/The_Imitation_Game](https://github.com/lucasjinhong/The_Imitation_Game)

## My Contributions & Key Responsibilities

*   **System Architecture Design:** Designed the overall flow of data and control between the UI, story engine, and game mechanic modules.
*   **Centralized State Management:** Developed a `parameters` dictionary system to act as the single source of truth for game state, UI configuration, and inter-module communication.
*   **Main Orchestration Controller (`View.Story.Controller.Controller`):** Implemented the central controller responsible for:
    *   Receiving UI events (button clicks, text input).
    *   Dispatching requests to the appropriate story level or game-specific logic modules.
    *   Managing the sequence of scenes and questions.
    *   Processing user answers and providing feedback.
*   **Integration of UI and Story Logic:** Created the "connective tissue" that allowed the PyQt6 UI (`Main_Widget.py`) to dynamically display story text, present questions, and react to game state changes managed by the backend logic.
*   **Utility Facade (`Controller.Controller.py`):** Designed a utility controller to provide story modules with easy access to:
    *   Codec modules (`Controller.Codec.*`) for generating questions and answers.
    *   Content loading tools (`PrintContent.py`) for fetching narrative text from external files.
*   **Prototyping Core Interaction Loops:** Established the primary interaction cycles:
    *   Scene loading and text display.
    *   Question presentation and answer validation.
    *   Progression to subsequent scenes or levels based on player performance.
*   **Defining Module Interfaces:** Ensured clear interfaces between the UI, the main controller, story modules, and utility services, promoting a separation of concerns.

## Technical Approach

The system was built around a layered architecture:

1.  **Presentation Layer (UI - `Main_Widget.py`):**
    *   Handled user input and display using PyQt6.
    *   Communicated exclusively with the Main Orchestration Controller.
    *   Dynamically updated based on data received from the controller.

2.  **Orchestration Layer (`View.Story.Controller.Controller`):**
    *   Acted as the intermediary between the UI and the story/game logic.
    *   Managed the game flow using the `parameters` state dictionary.
    *   Decided which story module or game mechanic to invoke based on the current state.

3.  **Story & Game Logic Layer (`View.Story.LevelX.py`, `View.Story.Game.Y.py`):**
    *   Contained the narrative script and specific logic for each level or mini-game.
    *   Utilized the Utility Facade to access codecs and story content.
    *   Updated the `parameters` dictionary to reflect game progression and prepare for the next UI state.

4.  **Service/Utility Layer (`Controller.Controller.py`, `Controller.Codec.*`, `PrintContent.py`):**
    *   Provided core functionalities:
        *   Generating and validating puzzle questions (Codecs).
        *   Loading narrative text from `.txt` files.
    *   Decoupled from the UI and higher-level story logic.

The `parameters` dictionary was key to this approach. It carried all necessary information, such as the current level/scene, last question/answer, game configuration (chances, retry flags), and UI button states. This dictionary was passed down through the layers and updated, with the modified version returned to the UI for rendering.

**Key Challenges Addressed:**

*   **Decoupling UI from Game Logic:** Ensuring the UI was not tightly bound to the specifics of each game level or puzzle, allowing for easier maintenance and independent development by team members.
*   **Managing Complex Game State:** Designing a manageable system (the `parameters` dictionary) to track various aspects of the game state across different modules.
*   **Dynamic Content Presentation:** Enabling the UI to dynamically display different story segments, questions, and feedback based on the evolving game state.
*   **Integrating Diverse Components:** Successfully bringing together separately developed UI elements, story scripts, and codec mechanics into a cohesive, functioning system.
*   **Parameter Uniformity** Ensure that the parameters used across all functions are consistent to guarantee the game runs successfully.

## Impact & Results (Generalized)

*   **Functional Prototype:** Delivered a working prototype that demonstrated the core gameplay loop and the successful integration of all major components.
*   **Clear Architecture:** Established a well-defined architecture that facilitated collaboration and allowed team members to work on their respective parts with minimal conflicts.
*   **Modularity:** The system design allowed for easier addition of new levels or game mechanics in the future due to the separation of concerns.
*   **Enabled Team Collaboration:** Provided the foundational structure upon which the other team members could build and integrate their contributions effectively.

## What I Learned

*   **Importance of a Central Controller:** Reinforced the value of a central orchestrator in managing complex interactions between different parts of an application, especially in UI-driven systems.
*   **State Management Strategies:** Gained practical experience in designing and implementing a state management system for a moderately complex application.
*   **Designing for Integration:** Learned the importance of clearly defined interfaces and data structures when building a system that integrates components developed by different people.
*   **Iterative Prototyping:** The process highlighted how building and testing a core prototype early can identify potential integration issues and refine the overall system design.
*   **Balancing Flexibility and Complexity:** Navigated the trade-offs in designing the `parameters` dictionary – aiming for flexibility while trying to manage its inherent complexity.