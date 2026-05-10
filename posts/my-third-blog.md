---
title: "Week 9: Data Requirements and Technical Architecture"
date: 2026-05-02
author: Isabelle Lee
summary: Bridging the gap between user needs and system implementation through a robust relational database design for the Badminton Hub.
tags:
  - Technical Reasoning
  - Database Design
  - 
---
## Aligning Requirements with Implementation

This week, my focus shifted from high-level interface design to the underlying technical architecture of the Badminton Community Hub. Translating my functional requirements into a formal Entity Relationship Diagram (ERD) and SQL schema forced me to make critical decisions regarding data integrity, scalability, and system performance.

### 1. The Decision: Relational Integrity over Flat Data
In my initial brainstorming, I considered a "flat" data model where venue details were simply text strings stored within a match record. However, my final implementation utilizes a highly relational structure with a dedicated `courts` table and junction tables for `amenities` and `access`.

**Reasoning:**
Badminton players rely heavily on specific venue metadata, such as lighting quality or ceiling height. By implementing a relational structure, I ensure **Data Integrity**. If users were allowed to type locations manually, the data would become inconsistent (e.g., "Syd Uni" vs "Sydney University"). Using a central `courts` table allows for reliable filtering—a core functional requirement—enabling users to accurately search for courts with specific features like "Disability Access" or "Pro Lighting."

### 2. Implementation: Managing Many-to-Many Relationships
A significant technical challenge was managing how players interact with events. I implemented an `event_attendance` junction table to handle the many-to-many relationship between users and matches.

```sql
-- Event attendance (many-to-many junction)
CREATE TABLE IF NOT EXISTS event_attendance (
    user_id INTEGER NOT NULL,
    event_id INTEGER NOT NULL,
    status TEXT DEFAULT 'confirmed',
    rsvp_date DATETIME DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (user_id, event_id),
    FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE,
    FOREIGN KEY (event_id) REFERENCES events(event_id) ON DELETE CASCADE
);