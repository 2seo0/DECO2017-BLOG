---
title: "RallyClub: Final Reflection"
date: 2026-06-08
author: Isabelle Lee
summary: "From Planning to Prototype: An Honest Evaluation of RallyClub's Performance, Usability, and What I'd Do Differently"
tags:
  - PrototypeEvaluation
  - Accessibility
  - CriticalReflection
  - FunctionalRequirements
---

# Looking Back — What RallyClub Actually Became

RallyClub started with one specific frustration: finding a badminton game shouldn't require digging through group chats and cold-messaging strangers. Six weeks of planning, building, and testing later, I can finally answer whether we actually solved that. Not just whether the app works, but whether it works for the people it was built for.

## Performance in Practice

The court map had a noticeable loading delay during use, something user testing confirmed when a participant remarked that connecting to the external venue website took longer than expected. Lighthouse audits across the four core pages gave the broader technical picture.

After tutors described the original homepage as generic, I redesigned it on the final day and the score reached 100, evidence that the iteration addressed the right problem. The profile page scoring 78 was the most surprising result given how minimal that page is. Lighthouse flagged unlabelled select elements and contrast failures, which WAVE later confirmed: 4 errors, 3 contrast errors, and an AIM score of 6.4 out of 10. The events page scored 85, with render-blocking requests adding approximately 420ms traced to static image assets loaded directly from the project folder. In production, CDN delivery and image compression would resolve this. Within the prototype timeframe, it was a conscious trade-off in favour of completing core functionality first.

| | |
|:---:|:---:|
| <img src="assets/evidence/homepage-before.png" alt="Homepage before tutor feedback" width="420"> | <img src="assets/evidence/homepage-after.png" alt="Homepage after tutor feedback" width="420"> |

*Figure 1: Homepage before (left) and after (right) the redesign prompted by tutor feedback. The original layout did not surface the platform's core features. Adding the skill-matched game card and FAQ directly to the landing view addressed both the feedback and the Lighthouse score.*


| Page | Lighthouse Score | Primary Issue |
|------|-----------------|---------------|
| Home | 100 | None identified |
| Forum | 92 | Missing alt text, unlabelled select elements, contrast failures |
| Events | 85 | Render-blocking assets adding ~420ms (local image folder) |
| Profile | 78 | Unlabelled select elements, contrast failures |

*Table 1: Lighthouse audit scores across the four core pages of RallyClub.*

## User Experience and Accessibility

Structured testing with two participants who had no prior exposure to the app produced consistent findings and surfaced issues that weren't visible from the inside.

The skill level system was the clearest success. Both participants used the skill filter unprompted and completed the RSVP without assistance. One went straight to intermediate games from the homepage; the other's reaction captured what the forum-first structure was trying to achieve:

> "The subsections are nice for people wanting to find what they want to find." — Participant 2, Task 1

The same participant compared the experience to Reddit and Facebook, a validation I hadn't anticipated but which confirmed the community-first design was landing the way it was intended to.

| Task | P1 Result | P2 Result | Key Finding |
|------|-----------|-----------|-------------|
| 1: Forum exploration | ✓ Complete | ✓ Complete | P2 compared forum to Reddit/Facebook unprompted |
| 2: Find & RSVP to event | ✓ Complete | ✓ Complete | Both used skill filter unprompted |
| 3: Find a court | ✓ Complete | ✓ Complete | P1 noted external link delay; P2 suggested radius filtering |
| 4: Check attendee profiles | Completed | Completed | Both searched for a members page that doesn't exist |
| Overall ease rating | 5/5 | 4/5 | |

*Table 2: User testing task completion summary across two participants (8 June 2026).*

Two usability gaps emerged consistently across both sessions. The first was event card affordance. Both participants expected the entire card to be clickable and attempted to interact with different areas before realising only the title was a link. Participant 1 described it directly:

> "Click doesn't work... oh, I need to click the title." — Participant 1, Task 1

The fix is straightforward, but it is the kind of assumption that only becomes visible when you watch someone encounter it for the first time. The second gap was attendee profile discoverability. Both participants searched for a dedicated members page before eventually locating profiles through the contextual avatar links. Two out of two participants struggling at the same point is a pattern, not an edge case. The context-based profile system works once understood, but the path to understanding it needs to be shorter.

The second session also surfaced smaller friction points: logout button placement felt inconsistent with platform conventions, the site logo wasn't interactive as expected, and forum content felt visually small on desktop. None are critical, but they accumulate and affect how polished the platform feels overall.

The WAVE audit on the forum page was harder to sit with. As shown in Figure 2, it scored 1.7 out of 10 with 60 errors, 60 contrast errors, and 92 alerts. Errors were concentrated on avatar images missing alt text across every post and unlabelled category filter buttons. These issues didn't prevent task completion in either testing session, but they represent a real failure for users relying on assistive technologies. My Week 10 blog planned WAVE, axe DevTools, keyboard-only, and colour blindness testing. In practice, only Lighthouse and WAVE were completed. That gap is something I have to own.

| | |
|:---:|:---:|
| <img src="assets/evidence/wave-forum.png" alt="WAVE audit forum page" width="420"> | <img src="assets/evidence/wave-profile.png" alt="WAVE audit profile page" width="420"> |

*Figure 2: WAVE audit results for the Court Talk forum page (left) and profile page (right). The forum scored 1.7 out of 10 with 60 errors and 60 contrast errors; the profile page scored 6.4 out of 10 with more contained issues consistent with the Lighthouse findings.*

## Critical Reflection and Improvement Planning

The mobile responsiveness gap wasn't a planning oversight. It was a communication failure. One teammate was responsible for mobile responsiveness and several event page functions, and I didn't check in closely enough to know things weren't on track. By the time I realised, I could address the event functionality but not the responsive layout. The lesson wasn't that task allocation was wrong. It was that I needed to stay in contact with what everyone was building, even for tasks that weren't mine. The simulated attendee count came from the same blind spot: a gap that could have been caught and fixed with earlier visibility across the team.

The improvements I'd prioritise are all grounded in what testing revealed. The most important is redesigning the events page so skill level is the visual centrepiece rather than a filter dropdown. It's the platform's core differentiator and currently the last thing a user encounters rather than the first. Second is making the full event card clickable, which both participants expected. After that: logo navigation, logout placement, forum sizing on desktop, and distance-based court filtering, which the second participant suggested and which would make the court map significantly more practical for anyone planning around transport.

| |
|:---:|
| <img src="assets/evidence/events-page.png" alt="Events page" width="840"> |

*Figure 3: The events page in the final prototype. Skill level filtering appears as one option within a dropdown rather than as the primary entry point, underselling the feature the platform was built around.*

## Retrospective Assessment of Functional Requirements

The forum was listed as a Must Have in Week 6, and testing produced real validation. One participant compared it favourably to Reddit unprompted. But by the end it was clear that event-finding and skill-matching was the actual core of what RallyClub does. If I were rewriting the requirements, I'd frame skill-level event coordination as the primary Must Have and position the forum as what supports it, not the other way around.

User profiles were also listed as a Must Have, but the implementation ended up more minimal than planned. That was deliberate. The platform exists to help people meet in person, not build digital identities, and retaining too much user information felt at odds with that purpose. Testing complicated this: the second participant wanted profile pictures and richer attendee cues, which suggests we may have gone slightly too minimal. A middle ground of lightweight profile pictures without a full social graph is probably where the next iteration should land.

The mobile audience was acknowledged throughout but never formally scoped, and that was a requirements gap rather than a reasonable constraint. A second audience with different device needs should have had its own requirements from the beginning, even if those were explicitly deprioritised.

| Original Must Have | Final Outcome | Assessment |
|-------------------|---------------|------------|
| One-tap RSVP system | ✓ Delivered | Worked intuitively, both testers completed without help |
| Skill level filtering and display | ✓ Delivered, but buried in dropdown | Core feature undersold by its placement |
| Forum for Q&A and discussion | ✓ Delivered | Validated by testing; may have been over-prioritised vs. events |
| Location-aware court map | ✓ Delivered | Well-received; radius filtering identified as missing |
| User profiles with activity history | Delivered at reduced scope | Deliberate privacy decision; testing suggests slightly too minimal |

*Table 3: Original Must Have requirements from Week 6 compared against the final prototype.*

---

In Week 6, I asked what problem this app actually solves. Having built and evaluated it, I'd give the same answer, coordination friction, but I understand it more specifically now. The problem isn't just logistics. It's the social anxiety of not knowing who you're playing with or whether you'll fit in. Skill level matching, contextual profiles, and beginner-friendly event visibility are all doing the same underlying work: making it feel safe to show up. That's what both testing sessions confirmed, and it's what I'd keep at the centre of every future development decision.

*AI tools (Claude) were used to support drafting and editing of this post. All reflections, evidence, and design decisions are my own.*