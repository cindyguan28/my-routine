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

## Product decision verdicts

- Good fit
- Useful but redundant
- Not needed
- Potentially irritating
- Need more information

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

### AI Decision
- COF-118 Product check input flow
- COF-119 Contextual skincare decision engine

## Explicitly deferred

- Fashion
- Makeup
- Community
- Marketplace
- Medical diagnosis
- AI skin scoring
- Product shelf/photo recognition as a hard dependency
- Complex treatment / clinic workflows
