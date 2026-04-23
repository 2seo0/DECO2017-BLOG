---
title: Week 7':' The 'Why' and the 'What' – Defining Functional Requirements
date: 2026-4-17
author: Isabelle Lee
summary: Transitioning from user research to technical reality by defining the core features and rationale for my badminton community app.
tags:
  - FunctionalRequirements
  - UserStories
  - MoSCoW
---
## Bridging the Gap Between "What" and "Why"

This week, the focus shifted from broad user research to the granular reality of product development: defining **Functional Requirements**. In previous weeks, my research into the local badminton community highlighted a recurring frustration—the logistical "messiness" of organising social games. This week, I translated those frustrations into a concrete roadmap for my application.

### The Rationale: The "Why"
Before listing features, I had to ground my decisions in the user experience. My research identified two primary user archetypes: the **Competitive Climber**, who seeks balanced matches to improve their ranking, and the **Social Organiser**, who is burdened by the administrative overhead of booking courts and collecting payments. 

The "Why" behind my project is simple: to reduce the friction of community sports. If the logistics are difficult, the community shrinks. By automating the "boring" parts of badminton—scheduling and cost-splitting—I can allow players to focus on the game itself.

### The Functional Requirements: The "What"
To define the system's behaviour, I utilised **User Stories** to ensure every feature served a direct purpose. For example:
* *As a player, I want to see the skill levels of others in a session so that I can join games that match my ability.*
* *As an organiser, I want a centralised RSVP list so that I can manage court capacity effectively.*

To manage the scope of this project, I applied the **MoSCoW** prioritisation framework. This was a vital exercise in distinguishing between "exciting" ideas and "essential" functionality.

| Priority | Feature | Justification |
| :--- | :--- | :--- |
| **Must Have** | Skill-level filtering & RSVP system | Core to solving the mismatch and overbooking issues found in research. |
| **Should Have** | In-app court cost calculator | A significant "pain point" solver that differentiates this from a generic chat app. |
| **Could Have** | Peer-review/Rating system | Enhances community trust but isn't required for a functional MVP. |
| **Won't Have** | Live video streaming of matches | Technologically out of scope and not a primary user need at this stage. |

---

### Reflection on Feasibility
Moving from the "Why" to the "What" forced me to confront the technical reality of my design. While a "Tournament Bracket Generator" would be a fantastic addition, I realised that perfecting the **Matchmaking Algorithm** (ensuring players of similar levels find each other) is the true priority. 

By narrowing my focus to these specific functional requirements, I now have a clear checklist for my upcoming wireframes. The goal for next week is to ensure the interface makes these complex background tasks—like calculating costs or filtering levels—feel invisible and effortless for the user.