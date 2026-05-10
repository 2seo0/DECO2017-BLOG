---
title: Week 8':' Architecture of a Community - Reasoning through Flow and Friction
date: 2026-04-25
author: Isabelle Lee
summary: This post documents the transition from research to execution by justifying the sitemap and wireframe designs for the Badminton Community Hub.
tags:
  - Interaction Design
  - Functional Requirements
  - Wireframes
---
## Interpreting the Brief: The Hybrid Community Hub
Following my initial research into the badminton community, I have moved beyond the abstract **"game finder"** concept to a concrete design documented through a Sitemap and Wireframes. To align with the Bla+Bla Corp mission of creating bespoke, user-centric experiences, I have used these artifacts to balance two distinct user needs: physical match coordination and digital social interaction. This blog post focuses on how I reasoned through these design decisions to ensure the application solves real-world logistical friction.

* The Sitemap: Justifying a Dual-Focus Homepage
My sitemap reveals a key design decision: elevating the Forum to a primary navigation element alongside Matchmaking.


* The Rationale: Current community engagement is often restricted to the physical court, which requires significant time, energy, and financial investment.


* The Decision: By placing the forum on the homepage, I am creating a space for indirect conversation. This lowers the barrier to entry for a diverse, multi-generational community who want to discuss strategy or gear without the pressure of an immediate meetup.


* Trade-off: I have de-prioritized "Gear Marketplaces" as a "Could-Have" feature to ensure the core social-functional hybrid remains technically feasible within the project timeline.

## The Wireframe: Solving the "Organizer Bottleneck"
A major pain point identified in my research was the inefficiency of joining socials, which currently requires manually contacting an organizer via fragmented group chats to verify skill levels. To solve this, my wireframes introduce an automated Skill-Based RSVP system.

I have made a concrete technical decision (LO2) to implement a mandatory skill-categorization field during user registration. Rather than a vague 1–10 scale, I have defined three descriptive tiers to ensure data integrity and user trust:  

* Beginner: Learning basic mechanics and maintaining long rallies. 

* Intermediate: Confident in clears, lifts, drops, and basic doubles rotation.

* Advanced+: Full mastery of all shots, strategy, and high-intensity play.

### Technical Alignment and Feasibility
This decision moves the "friction" from the organizer to the initial user onboarding. While this adds complexity to the backend—requiring the system to validate a user's skill_level against the event_requirement before allowing an RSVP—it directly supports the goal of high-quality community interaction. This intentional alignment between user needs (efficient joining) and technical architecture (relational data validation) replaces a manual social hurdle with a streamlined digital solution.
