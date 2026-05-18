---
title: "Week 6: Interpreting the Brief & Defining Requirements"
date: 2026-04-10
author: Isabelle Lee
summary: "Beyond the Feature List: Why My Badminton Hub Prioritises Coordination Over Networking"
tags:
  - FunctionalRequirements
  - UserStories
  - MoSCoW
---

# Beyond the Feature List: Why My Badminton Hub Prioritises Coordination Over Networking

In the first week of this project, I faced a critical question: *what problem does my badminton app actually solve?*

My research into the local badminton community revealed a frustration that cuts across skill levels and age groups: organising games is unnecessarily difficult. Players currently rely on fragmented group chats, outdated Facebook posts, and manual text exchanges to coordinate matches. A secondary issue also emerged. Players often do not know the skill levels of others joining a session, resulting in mismatched games and frustrating experiences.

## The Temptation: Building a Social Network

One possible direction was to create a "Badminton Instagram" style platform centred around discovering people, browsing profiles, and networking with other players. The brief even suggested member discovery as a potential feature.

However, my research revealed something important: most players are not looking to make friends with random people online. Instead, they simply want to organise enjoyable games with players of compatible skill levels.

This insight fundamentally shifted my design direction. Rather than building a social network with profiles as the central feature, I decided to design an **event coordination platform supported by trust signals**.

### Social Network vs. Coordination Hub
![Bespoke Badminton Hub vs Generic Social Network Platform Architecture Concept](/assets/diagrams/comparison-diagram.png)


## The MoSCoW Reality Check

Applying the MoSCoW framework forced me to make deliberate decisions about scope and priorities.

### Must Have
- One tap RSVP system to reduce organisational friction
- Skill level filtering and display to minimise mismatched games
- Forum for Q&A and discussion to support organic community building
- Location aware court map to reduce search friction
- User profiles showing activity history to provide credibility and context

### Should Have
- Photo uploads for event recaps
- Notifications for RSVP updates or cancellations
- Search functionality within the forum

### Won't Have
- Dedicated member browsing tab
- Court review system
- Leaderboards or rankings
- Gear marketplace

## A Key Technical Decision: Removing Member Discovery

This became the project's biggest pivot.

Profiles still exist within the system, but they only appear contextually. For example, users can click an author's name in the forum or tap an attendee avatar in an RSVP list. However, there is no standalone "Members" tab.

This decision came from the belief that profiles are most valuable when tied to trust and participation rather than passive browsing. A player wants to know who they are playing with or whether someone's advice is credible, not endlessly scroll through user profiles.

Removing member discovery also significantly reduced technical complexity. Without follower, friend, or social graph systems, the database structure became simpler and required less state management within the application. This made the overall scope more achievable within the semester timeframe. While this decision may reduce opportunities for broader social networking, it keeps the platform focused on efficient match coordination rather than passive engagement.
More importantly, this decision reinforced the forum first structure that later shaped the project. Community interaction became the entry point rather than profile discovery.

## Looking Ahead

These constraints are not limitations. They provide clarity.

By rejecting the generic social network model and evaluating every feature against a single question, *does this reduce coordination friction?*, I now have a much more coherent product direction and roadmap.

The next stage of the project will involve translating these requirements into a sitemap, user flows, and database relationships that support fast and intuitive event coordination.