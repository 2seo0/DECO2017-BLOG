---
title: "Week 7: Forum First Architecture"
date: 2026-04-17
author: Isabelle Lee
summary: "Why Forums Come First: Reframing the Badminton Hub as Content Driven, Not Event Driven"
tags:
  - InteractionDesign
  - FunctionalRequirements
  - Wireframes
---

# Why Forums Come First: Reframing the Badminton Hub as Content Driven, Not Event Driven

When I first sketched my sitemap, the Events tab was the hero of the homepage. Games Today, Upcoming Events, and Filter by Skill were all positioned as the primary features. However, I quickly realised that this structure could overwhelm new users.

## The Pressure Problem

Imagine opening the app for the first time and immediately seeing "Games happening today. RSVP now!" alongside a list of unfamiliar players. For experienced members this may feel exciting, but for new users it introduces pressure straight away.

This reflected an issue I identified during research. Players want to join games, but the main friction is not technical. It is social. New players often do not know anyone in the community, feel uncertain about their skill level, and want reassurance that the environment feels welcoming before committing to an event.

## Enter the Forum First Model

By placing forum content on the homepage instead of prioritising events, the first user experience changes entirely.

1. The user lands on the homepage and scrolls through community posts
2. They read gear tips, training advice, event recaps, and community discussions
3. Familiarity and trust begin to build through relatable interactions
4. Event related posts naturally spark curiosity about upcoming games
5. The user navigates to the Events tab and RSVPs with more confidence

This creates what I describe as an **engagement flywheel**. Forum activity encourages event participation, events create shared experiences, and those experiences generate new forum content.

## The Architecture Decision

This shift had direct implications for the sitemap and navigation structure.

- **Home** displays a subtle event carousel alongside recent forum posts as the primary content
- **Forum** becomes a primary navigation tab rather than being hidden under a broader Community section
- **Events** remains an essential feature but is discovered more organically
- **Courts** and **Profile** function as supporting tabs accessed when needed

The key insight behind this structure is that *trust precedes action*. Allowing users to engage with asynchronous content at their own pace reduces the pressure of immediately joining a game with strangers.

## Technical and UX Implications

This architectural shift also influences several technical and interaction design decisions.

### Post Categories

The forum requires structured post categories such as Gear, Training, Event Highlights, and Community Talk. This prevents the forum from becoming a second event listing system and encourages users to share experiences, opinions, and advice rather than only logistics.

### Context Based Profiles

Profiles remain visible only within context, such as when selecting an author's name or tapping an attendee avatar. This reinforces the platform's purpose as a coordination hub rather than a social networking platform. Profiles answer practical questions such as whether advice feels credible or what skill level other attendees may have.

### Event Visibility Without Pressure

The homepage still includes an event carousel, but it functions as a passive invitation rather than an aggressive call to action. The interface suggests opportunities without forcing immediate commitment.

## The Trade Off

This model intentionally delays the primary call to action. From a business perspective, some may argue that the homepage should maximise immediate event clicks and RSVPs.

However, my research suggests that users who feel informed and comfortable are more likely to RSVP confidently and attend consistently. Prioritising trust and familiarity may lead to fewer impulsive sign ups, but it supports higher quality participation and stronger long term engagement.

## Looking Ahead

With the forum first structure now established, the next challenge is developing wireframes that validate this interaction flow. The interface needs to demonstrate that browsing forum content naturally encourages event discovery rather than distracting users from it.