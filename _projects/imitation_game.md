---
title: Visual Novel Game System Prototype (PyQt & Python)
permalink: /portfolio/imitation_game/
date: 2023-6-18
excerpt: "Architected a modular, event-driven Python application for a visual novel game, creating the core controller and state management system that integrated separately developed UI and story logic components."
header:
  teaser: /assets/images/imitation_banner.png
sidebar:
  - title: "Role"
    text: "Core System Developer & Architect"
  - title: "Core Technologies"
    text: "Python, PyQt6, Software Architecture"
  - title: "Context"
    text: "Team collaboration with a UI designer and story writer."
  - title: "Duration"
    text: "May 2023 - June 2023"
tags:
  - Python
  - PyQt6
  - System Architecture
  - Game Development
  - Prototyping
  - Software Design Patterns

---

## Project Overview

In a team with a dedicated UI designer and story writer, I was tasked with architecting the core system for an interactive visual novel. The project's success depended on seamlessly integrating the PyQt6 user interface with dynamic story scripts and puzzle-based game mechanics. My role was to design and build the central "nervous system" of the application, enabling all other components to communicate and function as a cohesive whole.

## Source Code

The complete source code is available on GitHub:
*   [lucasjinhong/The_Imitation_Game](https://github.com/lucasjinhong/The_Imitation_Game)

## My Contributions & Key Responsibilities

*   **System Architecture Design:** I designed a modular, controller-mediated architecture to decouple the UI from the game logic. This ensured that the UI designer and story writer could work independently without creating conflicts, connected only by the central controller I built.
*   **Centralized State & Flow Control:** I developed the main orchestration controller and a unified `parameters` dictionary. This served as the single source of truth for the game state, managing the flow of data, processing UI events (like button clicks), and dispatching tasks to the appropriate story or game logic modules.
*   **Module Integration:** I implemented the "connective tissue" that allowed the UI to be data-driven. The controller I wrote would pass state to the UI, which would then render the correct scene, question, or feedback, making the front-end reactive to back-end logic.
*   **Service Layer Abstraction:** To keep the game logic clean, I created a utility facade that provided story modules with easy, abstracted access to shared services like puzzle generators (codecs) and content loaders.

## Technical Approach

The architecture was designed around a **Controller-Mediated pattern** to manage complexity and enforce a clear separation of concerns.

1.  **The Controller (The System Core):** At the heart of the application was a central controller I implemented. It was the sole intermediary between the UI and all back-end logic. No other components communicated directly with each other.

2.  **The State Dictionary (The "Lifeblood"):** All game state—current scene, player score, active puzzle, UI configuration—was encapsulated in a single Python dictionary (`parameters`). This dictionary was passed from the controller to a logic module, which would modify it and return it. The controller would then use the updated dictionary to instruct the UI on what to render next. This created a predictable, traceable, and unidirectional data flow.

3.  **The Components (UI, Story, Puzzles):**
    *   **Presentation Layer (UI):** A component that only knew how to render the state given to it by the controller.
    *   **Logic Layer (Story/Puzzles):** Independent modules responsible for a single level or puzzle. They received the state dictionary, executed their logic, and returned the new state.

This approach ensured that adding a new level was as simple as creating a new logic module that adhered to the established interface, without ever needing to modify the UI or the central controller.

## Key Challenges Addressed

*   **Enabling Parallel Development:** The primary challenge was allowing team members to work on the UI and story logic in parallel. **Solution:** I architected a decoupled system where the UI and logic were completely isolated, communicating only through the central controller. This prevented dependencies and merge conflicts.

*   **Managing Complex, Evolving State:** A game with multiple levels, puzzles, and branching paths has a complex state that is difficult to track. **Solution:** I designed the centralized `parameters` dictionary to serve as a single, authoritative source of truth, which simplified debugging and ensured data consistency across the application.

*   **Integrating Diverse Components:** The project required bringing together UI, narrative scripts, and procedural puzzle generators. **Solution:** I established clear, strict interfaces for how all modules would receive and return data from the central controller, creating a plug-and-play system for new features.

## Impact & Results

*   **Unlocked Team Productivity:** My architecture provided a stable and predictable foundation that unblocked the other team members, allowing them to focus entirely on their areas of expertise (UI and story) and integrate their work seamlessly.
*   **Delivered a Cohesive Prototype:** The final result was a fully functional prototype that successfully demonstrated the core gameplay loop and proved the viability of the architecture.
*   **Created a Modular & Extensible System:** The design allows for new game levels or puzzle types to be added with minimal effort and without touching existing code, making the system highly maintainable.

## What I Learned

*   **The Power of the Mediator Pattern:** This project was a masterclass in the value of a central controller (or Mediator pattern) for managing complexity and decoupling components in event-driven applications.
*   **Designing for the Team:** I learned to design not just for the machine, but for the team. Establishing clear contracts (interfaces) and predictable data flows is critical for effective collaboration.
*   **Pragmatic State Management:** I gained practical experience in designing a simple yet effective state management system for a moderately complex application, balancing flexibility with simplicity.
*   **The Value of Prototyping Architecture:** Building the core system skeleton first allowed us to identify and solve major integration challenges early in the development process.