---
title: "Week 10: Accessibility & Data Protection Planning"
date: 2026-05-09
author: Isabelle Lee
summary: "Responsibility First: Accessibility and Privacy Considerations in a Community Hub"
tags:
  - Accessibility
  - DataProtection
  - EthicalDesign
---

# Responsibility First: Accessibility and Privacy Considerations in a Community Hub

As development progresses, it becomes easy to focus primarily on features and interaction flows. However, the project brief also requires accessibility compliance and responsible data handling. This week focuses on how accessibility, privacy, and ethical responsibility influence both the design and technical planning of the badminton hub.

## Accessibility Strategy: AA Compliance by Design

The application is being designed with WCAG 2.1 AA accessibility standards in mind from the beginning rather than treating accessibility as a final stage checklist.

Key accessibility requirements include:
- sufficient text contrast ratios
- full keyboard navigation support
- visible focus indicators
- descriptive alt text for images
- semantic HTML structure
- accessible form labels and error handling

These requirements directly shape interface and development decisions throughout the application.

## Specific Implementation Decisions

### Semantic Structure

Forum posts and user profiles use semantic HTML with a clear heading hierarchy. This improves screen reader navigation and helps communicate page structure more effectively for assistive technologies.

Interactive elements use appropriate semantic tags such as `<button>` rather than clickable `<div>` containers.

### Accessible RSVP Forms

The RSVP modal includes labelled form inputs, accessible validation messages, and keyboard navigable controls. Error messages are associated directly with the relevant fields to improve usability for screen reader users.

### Court Map Accessibility

The court map includes both visual and text based representations of information. While users can interact with map markers visually, the same court information is also available through a structured list view below the map.

This ensures users relying on keyboards or assistive technologies can still access the same content and functionality.

### Avoiding Colour Only Communication

Colour is never used as the sole indicator of meaning. Skill level badges and event statuses include both colour and descriptive text labels to support users with colour vision deficiencies.

## Accessibility Evaluation Plan

To evaluate accessibility compliance, the prototype will be tested using:
- WAVE accessibility evaluation tools
- axe DevTools accessibility testing
- keyboard only navigation testing
- colour blindness simulation tools

These evaluations will help identify accessibility issues before final submission and ensure the interface remains usable for a broader range of users.

## Data Protection and Privacy Planning

The platform also requires responsible handling of user data. Although the application is community focused, it still stores personal information and participation history that should be handled transparently.

The application currently collects:
- user profile information
- skill levels and availability
- posts and comments
- RSVP attendance history

This information is collected specifically to support coordination, trust signals, and event management within the platform.

## Privacy Questions Guiding Development

### Data Retention

One key consideration is how long attendance history should remain stored. Retaining participation history supports long term credibility and reliability indicators, but it also increases responsibility around user privacy.

At this stage, the system is leaning towards retaining attendance history indefinitely because reliability becomes more meaningful over time.

### User Control Over Data

Users should be able to delete their accounts and personal data. Current planning prioritises complete removal of user information rather than retaining posts under anonymous placeholders.

This approach aligns more closely with the platform's community focused purpose and avoids retaining unnecessary personal data.

### Data Export Considerations

Another consideration is whether users should be able to export their personal information. This reflects expectations established through GDPR and broader privacy standards.

Although the project primarily targets local badminton communities, investigating export functionality remains part of the evaluation process.

### Cookie Usage

The application only uses encrypted session cookies required for authentication. No tracking cookies or third party analytics systems are planned.

A simple cookie notice will explain:
- what cookies are used
- why they are necessary
- what data is stored within them

## Evaluation Plan for Final Testing

The final evaluation stage will include:
- accessibility audits across core screens
- keyboard only usability testing
- colour blindness testing
- privacy policy documentation
- session logout and cookie clearing tests

## Looking Ahead

Accessibility and privacy are not secondary concerns added after development. They directly shape how the platform is structured, implemented, and evaluated.

A community coordination platform depends heavily on user trust. If the application is inaccessible, difficult to navigate, or careless with user data, it fails both technically and ethically.

Designing responsibly means ensuring the platform remains inclusive, transparent, and practical for the people using it.