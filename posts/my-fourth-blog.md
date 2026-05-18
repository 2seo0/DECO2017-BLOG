---
title: "Week 9: Courts Map Simplification"
date: 2026-05-02
author: Isabelle Lee
summary: "Less is More: Why Removing Court Reviews Sharpened the Badminton Hub's Focus"
tags:
  - DatabaseDesign
  - FunctionalRequirements
  - UXDesign
---

# Less is More: Why Removing Court Reviews Sharpened the Badminton Hub's Focus

In Week 3, my initial sitemap included a complete court review system where players could rate venues, leave comments, and sort courts by ratings. At first, this seemed like an obvious feature because reviews are commonly associated with trust and decision making.

However, after revisiting my user research, I realised the feature was solving the wrong problem.

## The User Research Reality

When discussing court selection with badminton players, the questions they consistently asked were practical and logistical.

- Is there parking available?
- Does the venue have good lighting?
- What is the booking system like?
- How much does it cost?
- What time does the venue close?

Not once did participants mention wanting to browse subjective reviews before deciding on a court.

This shifted my understanding of the feature entirely. Players were not selecting venues based on ratings or reputation. Instead, they were making decisions based on accessibility, convenience, and whether the venue met their practical needs.

## The Review System Trap

Adding reviews would have introduced significant complexity to both the user experience and technical implementation.

### Moderation Requirements

A review system would require moderation workflows to handle spam, inappropriate content, or misleading reviews. It would also raise concerns around venue owners posting fake ratings or manipulating feedback.

### Information Becoming Outdated

Court facilities and management can change over time. Reviews discussing parking availability or venue quality may quickly become inaccurate, reducing the reliability of the information presented.

### Scope Expansion

Once reviews are introduced, additional features naturally follow. Users may expect threaded replies, voting systems, image uploads, reporting tools, or sorting filters. This would significantly expand the project scope beyond the platform's core purpose.

### Development Cost

Implementing a reliable review system would require a substantial amount of development time for a feature that users did not explicitly prioritise during research.

## The Simplified Alternative

Instead of reviews, the court map focuses on factual and actionable information.

Each court displays:
- location and distance from the user
- operating hours
- pricing information
- available facilities such as parking, lighting, cafés, or change rooms
- number of courts available
- direct links to the venue's booking website

This information directly answers the questions users are already asking. More importantly, it is objective rather than opinion based. A venue either has parking or it does not. The interface avoids unnecessary subjectivity and reduces the need for moderation systems.

## Database Implications

This decision also simplified the database structure considerably.

The `courts` table now contains only relational and factual information.

```yaml
courts:
  - court_id
  - name
  - address
  - latitude
  - longitude
  - hourly_rate
  - membership_rate
  - opening_hours
  - court_count
  - ceiling_height
```

Additional facilities such as parking, lighting, or cafés are connected through a related `amenities` table.

Importantly, the application no longer requires:
- `reviews`
- `ratings`
- moderation tables
- voting systems

This keeps the schema lightweight and focused on supporting coordination rather than content moderation.

## Accessibility and UX Benefits

Removing reviews also improves usability and accessibility. Users can quickly tap a court marker, scan practical information, and make a decision without navigating lengthy review sections or conflicting opinions.

This reduces cognitive load and supports faster task completion, particularly for users trying to organise games efficiently.


### Visualizing Scope Reduction: The Task-Focused Court Map

To bridge our refined functional requirements with our backend schema constraints, we developed a simplified map interface. Rather than showing a crowded social dashboard or generic review feeds, the interface focuses entirely on reducing task execution time for organizing real-world games.

![Figure 1: UI wireframe showcasing the court discovery sheet populated with structural facility metadata tags](/assets/diagrams/courtmap.png)

*Figure 1: Our map interface design. Instead of devoting screen layout real estate to user-generated reviews, comment textareas, or subjective star ratings, the interface prioritizes structured, immutable metadata fields (e.g., specific tags mapping to `ceiling_height` or `amenities`) that answer logistical questions instantly.*

## Looking Ahead

This decision reflects a broader design principle that continues throughout the project: remove features that duplicate systems users already have access to elsewhere.

Players can already read public venue reviews through platforms such as Google Maps or official venue websites. The badminton hub does not need to replicate those systems.

Instead, the platform remains focused on its core purpose: helping players coordinate games and participate in the badminton community more efficiently.