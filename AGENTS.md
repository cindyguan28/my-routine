# AGENTS.md

This repository is developed AI-natively.

## Core development principle
**Small deliverable, large shared context.**

Before implementing any Decision Engine ticket, read:

1. `docs/PRODUCT_CONTEXT.md`
2. `docs/DECISION_ENGINE.md`
3. `docs/AI_NATIVE_DEVELOPMENT.md`
4. The assigned Linear issue and its explicit blockers

## Scope discipline
- Implement only the assigned Linear ticket.
- Do not opportunistically implement downstream tickets.
- Do not duplicate business logic that belongs to another component.
- Do not change shared contracts silently.
- If a contract must change, update the shared context docs and identify affected tickets.

## Product guardrails
- Personal context over generic recommendations.
- Memory over one-off answers.
- Do not encourage unnecessary skincare stacking.
- Prefer Replace > Add when a need is already sufficiently covered.
- Redundancy is about marginal functional value, not ingredient overlap alone.
- Keep compatibility / irritation separate from redundancy.
- Never invent missing product facts.
- Never invent numeric precision.
- Prefer explicit unknown / need-more-information states to guessing.
- No medical diagnosis.

## Engineering expectations
- One ticket should result in one independently testable behavior.
- Follow the contracts in `docs/DECISION_ENGINE.md`.
- Add tests for acceptance cases.
- Preserve existing contracts unless the ticket explicitly changes them.
- Keep implementation simple; do not over-architect for deferred features.

## Deferred unless explicitly assigned
- Fashion
- Makeup
- Community
- Marketplace
- AI skin scoring
- Product shelf/photo recognition
- Open-ended general skincare chatbot
