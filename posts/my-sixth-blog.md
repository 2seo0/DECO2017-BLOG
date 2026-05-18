---
title: "Week 11: Integration & Prototype Readiness"
date: 2026-05-16
author: Isabelle Lee
summary: "Bringing It Together: How Forum, Events, Courts, and Profiles Align to Solve the Coordination Problem"
tags:
  - PrototypeEvaluation
  - TechnicalReflection
  - UserExperience
---

# Bringing It Together: How Forum, Events, Courts, and Profiles Align to Solve the Coordination Problem

By Week 11, the prototype is approaching its final submission state. This stage provided an opportunity to evaluate whether the architectural decisions made throughout Weeks 6 to 10 actually translated effectively into the working prototype.

This reflection focuses on how the forum, events, courts, and profile systems integrated together, what worked successfully during testing, and what limitations became apparent during implementation.

## Architecture in Practice

The forum first model proved more effective than expected during early testing.

When users first opened the application, they did not feel pressured into immediately joining games. Instead, they naturally explored forum posts, viewed user profiles through author interactions, and gradually navigated towards the events section.

This behaviour closely matched the interaction flow predicted during Week 7 planning.

The platform successfully encouraged familiarity and trust before asking users to commit to participation.

## Where the Design Held Strongly

### RSVP Flow

The RSVP system was consistently understood by users without additional explanation.

Participants could immediately identify:
- how many people were attending
- the skill levels of attendees
- whether the event matched their own experience level

The simplified RSVP interaction reduced unnecessary steps while still communicating important trust signals.

### Court Map Simplicity

Removing the review system significantly improved usability.

Users were able to quickly scan:
- location
- distance
- parking availability
- pricing
- opening hours

Most users made venue decisions within a short amount of time because the information presented aligned directly with their practical needs.

### Context Based Profiles

Users did not expect a dedicated members browsing system. Instead, profiles felt intuitive when accessed through forum posts or RSVP lists.

Activity history such as games attended and forum participation naturally reinforced credibility without requiring explicit social networking systems.

### Skill Level Validation

The skill filtering system became one of the prototype's strongest features.

During RSVP, the application validated whether a user's skill level aligned with the event requirements. This reduced mismatched games and ensured event listings remained relevant to the selected filters.

This functionality directly addressed one of the core problems identified during early research.

## Friction Discovered During Testing

Although the overall architecture functioned effectively, several usability and maintenance issues emerged during implementation and testing.

### Forum Categorisation

Initially, I assumed users would willingly categorise their posts when creating new forum threads. However, some testers skipped categories entirely.

To address this, I added validation requiring category selection before submission. If more development time were available, I would implement smarter defaults or category suggestions based on post content.

### Court Data Maintenance

The court map relies heavily on accurate logistical information. During testing, one venue's operating information had become outdated due to renovations.

To improve reliability, I added:
- a "last updated" timestamp
- a reporting option for outdated information

In a production environment, the ideal solution would involve syncing court information directly through venue APIs or external data sources.

### Empty States for New Users

New users initially encountered an empty forum feed, which reduced the feeling of community activity.

To improve onboarding, I introduced placeholder content such as:
- community announcements
- badminton tips
- example discussions

While effective, this approach still requires manual curation and would not scale well long term.

## Technical Decisions Under Constraint

Several technical decisions were shaped by the limited scope and timeframe of the prototype.

### SQLite for Rapid Development

SQLite was selected because it allowed the project to remain lightweight and easy to configure during development.

Although a production version would likely require PostgreSQL or another scalable database solution, SQLite was appropriate for a functional prototype focused on validating interaction flows and data relationships.

### Session Based Authentication

The application uses session based authentication through Mojo.js cookies. This was sufficient because the project brief assumes authenticated users within the testing environment.

As a result, features such as:
- registration systems
- email verification
- password recovery

were intentionally excluded from scope.

This trade off prioritised core coordination features over production level account management systems.

## Core User Journeys Validated

The following core interaction flows were successfully demonstrated during testing:

- Forum browsing leading to event discovery and RSVP
- Court lookup through the interactive map
- Profile interactions functioning as trust signals
- Event creation with skill level filtering and attendee coordination

These journeys aligned closely with the original design goals established earlier in the semester.

## Features Prioritised for Future Development

If additional development time were available, the next priorities would include:
- photo uploads for event recaps
- forum search functionality
- notification systems for new events
- optional statistics or leaderboard features

These features were intentionally deprioritised to maintain focus on the platform's primary coordination goals.

## Final Reflection

The final prototype successfully delivers on its core purpose: reducing coordination friction while supporting trust within the badminton community.

Several early design decisions that initially felt restrictive ultimately strengthened the project. Removing member discovery and court reviews kept the platform focused and prevented unnecessary feature expansion.

Most importantly, the forum first structure and skill level validation systems worked together exactly as intended. Rather than functioning as a generic social platform, the application remained centred on helping players organise compatible games efficiently and confidently.

## Looking Ahead

The remaining development period will focus on user acceptance testing, accessibility validation, and interface refinement.

The final evaluation stage will help determine which assumptions proved correct and which interaction patterns require further refinement beyond the prototype stage.