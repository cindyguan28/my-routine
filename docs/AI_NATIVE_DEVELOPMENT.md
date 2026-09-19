# AI-Native Development Guide

## Principle
**Small deliverable, large shared context.**

We want:
- small Linear tickets,
- explicit contracts,
- shared product context,
- one independently testable behavior per ticket.

We do **not** want:
- giant feature tickets that let the agent change everything,
- hyper-fragmented micro-tasks with no business meaning,
- duplicated product logic across tickets.

## Required reading before implementation
For Decision Engine work:
1. `docs/PRODUCT_CONTEXT.md`
2. `docs/DECISION_ENGINE.md`
3. The assigned Linear ticket
4. Any blocking issue explicitly referenced by that ticket

## Ticket shape
Every implementation ticket should have:

### Why
Why this behavior exists.

### Scope
Exactly what the ticket implements.

### Non-goals
What the agent must not implement.

### Inputs
The data/contracts it consumes.

### Outputs
The data/contracts it must produce.

### Acceptance cases
Concrete examples or tests.

### Context
Links to shared docs and related/blocking issues.

## Splitting rule
Split a ticket when the pieces:
- can be merged independently,
- have a clear interface,
- can be tested independently,
- or change different parts of the system.

Do not split when:
- each fragment has no independently testable behavior,
- fragments would recreate the same semantic logic separately,
- or they constantly edit the same code path.

## Implementation rule
Split by **testable product behavior**, not arbitrary code components.

Prefer:
> Given a candidate product and cabinet, identify whether it adds meaningful value and which existing product it could replace.

Avoid:
> Create SimilarityService.
> Create ReplacementService.
> Create OverlapHelper.

The agent may choose internal implementation structure as long as the contract and acceptance behavior are met.

## Agent guardrails
- Implement only the assigned ticket.
- Do not opportunistically build downstream features.
- Do not change shared contracts without explicitly updating the shared docs and affected tickets.
- Do not invent product facts.
- Do not add fake numeric precision.
- Add tests for acceptance cases.
- Preserve backwards compatibility with already-merged contracts unless the ticket explicitly changes them.
