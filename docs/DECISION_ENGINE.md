# Decision Engine Context

## Goal
Answer a narrow question well:

> Does this candidate product add meaningful value for this user now?

The engine should not decide whether a product is "good" in general.

## Pipeline

Candidate product
→ Normalize product
→ Load user context
→ Calculate need coverage
→ Detect redundancy / replacement
→ Evaluate compatibility / irritation risk
→ Generate structured verdict
→ Persist decision memory

Relevant Linear issues:
- COF-157 Normalize candidate product
- COF-158 Load decision context
- COF-159 Need coverage
- COF-160 Redundancy / replacement
- COF-161 Compatibility / irritation
- COF-162 Structured verdict
- COF-163 Persist decision
- COF-119 Orchestration / integration only

## Boundaries
### Product data layer
Owns facts:
- product identity
- category
- ingredients / actives
- normalized functions
- target concerns
- known / unknown fields
- confidence / provenance

### Rule / decision layer
Owns derived judgments:
- need coverage
- redundancy
- replacement candidate
- compatibility / irritation risk

### AI / language layer
Owns:
- concise explanation
- contextual follow-up wording
- conversational refinement

The language model must not invent missing product facts or silently override rule outputs.

## Provisional contracts

### CandidateProductProfile
- productId?
- brand
- name
- category
- functions[]
- activeFamilies[]
- targetConcerns[]
- knownFields[]
- unknownFields[]
- confidence
- provenance[]

### DecisionContext
- skinGoals[]
- baselineNeeds[]
- currentSkinState[]
- currentProducts[]
- currentRoutine
- recentRelevantDiarySignals[]

### CoverageResult
For each relevant need/function:
- status: uncovered | partial | sufficient | overcovered
- evidence[]

### RedundancyResult
- status: low | partial | high
- overlappingProducts[]
- replacementCandidate?
- reasons[]

### CompatibilityResult
- status: clear | caution | potentially_irritating | need_more_information
- reasons[]

### ProductDecision
- verdict:
  - good_fit
  - useful_but_redundant
  - better_as_replacement
  - not_needed_now
  - caution
  - need_more_information
- reasons[]
- replacementCandidate?
- confidence
- evidenceReferences[]

These contracts are intentionally small. Extend only when a ticket requires it.

## Core decision rule
"User already owns A" does **not** imply "user does not need B".

A candidate is redundant only when:
1. the relevant user need is already sufficiently covered, and
2. the candidate adds little meaningful marginal value, and
3. it does not solve a current gap, format/use-case gap, or replacement need.

Example:
- Existing: HA serum + light gel moisturizer
- Current skin state: dry + flaky
- Candidate: ceramide-rich barrier cream
- Expected: complementary / gap-filling, not redundant

## Compatibility is separate
A product can be:
- non-redundant but irritating,
- redundant but safe,
- useful and safe,
- useful but require routine adjustment.

Do not collapse these dimensions into one score.

## Confidence / unknowns
If concentration, formulation, ingredient list, user state, or routine context is missing:
- reduce confidence,
- surface the missing information,
- prefer `need_more_information` to invented certainty.

## POC success
The engine is good enough for MVP integration when it performs acceptably against the gold-standard evaluation set in COF-137 and failure modes are understood in COF-136.
