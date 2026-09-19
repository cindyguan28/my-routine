# MVP v0.1

## Goal

Validate whether users repeatedly use a skincare memory app to manage products, follow routines, record skin state, and make product decisions.

## Core loop

1. User creates a lightweight skin profile.
2. User adds current skincare products.
3. User creates AM / PM routines.
4. User checks today's routine and optionally logs skin state.
5. User checks a new or existing product with **Should I use this?** or **Should I buy this?**.
6. The app uses accumulated personal context to improve future decisions.

## Screens

- Today
- My Products
- Skin Diary
- Check Product
- Profile / Settings

## MVP entities

- UserSkinProfile
- Product
- Routine
- RoutineStep
- SkinDiaryEntry
- ProductDecision

## Decision Engine

The Decision Engine is intentionally split into independently deliverable behaviors.

High-level flow:
1. Normalize candidate product
2. Load user context
3. Calculate need coverage
4. Detect redundancy / replacement
5. Evaluate compatibility / irritation risk
6. Generate structured verdict
7. Persist decision memory
8. Orchestrate the end-to-end pipeline

See [Decision Engine Context](DECISION_ENGINE.md).

## Build order

### Foundation
- COF-110 Mobile app foundation and navigation
- COF-111 Skin profile and onboarding
- COF-112 Core skincare data model

### My Products
- COF-113 Add and edit skincare products
- COF-114 My Products cabinet view

### Daily Use
- COF-115 AM and PM routines
- COF-116 Today routine screen
- COF-117 Lightweight Skin Diary check-in

### Product Decision
- COF-118 Product check input flow
- COF-157–163 Decision components
- COF-119 Decision pipeline orchestration
- COF-164–167 AI decision / compare UX
- COF-136 POC validation

## Explicitly deferred

- Fashion
- Makeup
- Community
- Marketplace
- Medical diagnosis
- AI skin scoring
- Product shelf/photo recognition as a hard dependency
- Complex treatment / clinic workflows
