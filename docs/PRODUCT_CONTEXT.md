# Product Context

## Product
**My Routine** is a mobile-first skincare memory app.

It remembers:
- what the user owns,
- what they use,
- how their skin reacts,
- and helps them decide what to use or buy next.

## Core promise
- Know what I own
- Know what I use
- Remember how my skin reacts
- Help me decide what to use or buy next

## v0.1 scope
1. My Products
2. Today Routine
3. Skin Diary
4. Product Decision: Should I use / buy this?

## Non-goals for v0.1
- Fashion
- Makeup
- Social/community feed
- Marketplace
- Medical diagnosis
- AI skin scoring
- Product shelf/photo recognition as a launch dependency

## Product principles currently agreed
These are working principles unless a PO-owned issue changes them.

- Personal context over generic recommendations.
- Memory over one-off answers.
- Do not encourage unnecessary product stacking.
- Prefer **Replace > Add** when a user need is already sufficiently covered.
- "Less" is not automatically better; the goal is a sufficient, effective routine.
- Do not use fake precision scores.
- Explain why a recommendation was made.
- Redundancy is about **marginal functional value**, not ingredient overlap alone.
- Safety / irritation risk is a separate dimension from redundancy.
- When information is insufficient, say so instead of guessing.

## Decision hierarchy
A product should not be judged in isolation.

The system should consider:
1. User's long-term skin goals
2. Baseline skin needs / sensitivity
3. Current skin state
4. Existing product cabinet
5. Existing AM/PM routine
6. Historical response where available
7. Candidate product profile

## Open PO-owned decisions
Do not hard-code assumptions that belong to these issues.

- COF-126 — target user for Decision POC
- COF-127 — skincare decision principles
- COF-128 — user need model
- COF-129 — skincare concern & function ontology
- COF-132 — redundancy benchmark cases
- COF-137 — evaluation set

## Rule for coding agents
If a Linear ticket conflicts with this document, the ticket wins only when it explicitly states the product decision changed. Otherwise treat this document as shared product context.
