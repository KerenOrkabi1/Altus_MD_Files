# Change Request - Base (Non-Destructive Revision Contract)

## Purpose
This file defines the standard format for requesting design changes after a first version already exists.

It is intended to reduce design drift during iteration by making each requested change explicit, bounded, and reviewable.

This file should be used whenever AI is asked to revise an existing screen, prototype, or page concept.

## Role in the file set
This file works after an initial version has been created.

It should be used with:
- the relevant masterplan file
- the relevant user journey file
- the relevant design guidelines file
- the relevant rules file
- the relevant product shell file
- the relevant screen spec file
- the current screen version being changed

This file does not replace the screen spec.

The screen spec defines what the screen must be.

This file defines what is being changed now, under what limits, and how the revision should be judged.

## Core principle
All revisions should be treated as non-destructive by default.

That means the AI should assume the current design remains valid unless this file explicitly authorizes a structural change.

If a requested change is unclear, AI should preserve the current structure rather than invent a new one.

## Default revision policy
Unless this file explicitly says otherwise, AI must:
- preserve the current screen purpose
- preserve the current section structure
- preserve existing required components
- preserve existing labels and naming
- preserve existing interaction flow
- preserve the product shell
- limit the revision to the requested scope only

AI must not make broader changes outside the requested scope.

## Revision modes
Every change request should declare one revision mode.

### 1. Preserve mode
Use when the goal is to improve clarity, readability, hierarchy, spacing, grouping, or emphasis without changing structure.

In this mode, AI must not:
- remove components
- add major new sections
- change user flow
- rename core labels
- restructure the page

### 2. Refine mode
Use when the goal is to improve the experience with moderate design adjustment while keeping the same screen model.

In this mode, AI may:
- improve grouping
- refine section layout
- improve emphasis and ordering inside an existing section
- adjust component treatment

In this mode, AI must still not:
- remove required information domains
- change the screen purpose
- redesign the product shell
- replace the current page model with a different one

### 3. Structural mode
Use only when a larger approved redesign is intentionally required.

In this mode, broader change may be allowed, but only if explicitly written in the request.

Structural mode should be used rarely and intentionally.

## Standard change request fields
Each change request should include the following sections.

### 1. Request identity
Include:
- request name
- related screen
- version being changed
- date or sequence number if useful

### 2. Revision mode
Declare one of:
- Preserve
- Refine
- Structural

### 3. Problem being solved
State the issue clearly and specifically.

Examples:
- The right panel is hard to scan.
- The executive summary feels visually too heavy.
- AI content is too prominent compared with baseline project information.

The problem should describe what is wrong now, not prescribe the full solution.

### 4. Desired outcome
State what success should feel like after the change.

Examples:
- The user can scan the right panel faster.
- The summary feels calmer and easier to trust.
- AI insight feels supportive rather than dominant.

### 5. Scope of change
Define exactly where the AI is allowed to work.

Examples:
- right panel only
- executive summary only
- AI support section only
- spacing and hierarchy only within the main health cards

The narrower the scope, the lower the risk of drift.

### 6. Locked items to preserve
List what must stay unchanged during this revision.

Typical locked items may include:
- section order
- required cards
- labels
- action buttons
- tabs
- interaction paths
- shell dimensions
- overall page model

### 7. Explicitly forbidden changes
List what the AI must not do during this revision.

Examples:
- do not remove existing sections
- do not merge cards
- do not rename labels
- do not move actions to a new location
- do not restyle the entire page
- do not change the left navigation or top product area

### 8. Allowed changes
List the kinds of changes the AI is allowed to make.

Examples:
- adjust spacing
- improve visual grouping
- strengthen heading hierarchy
- reduce visual noise
- simplify card emphasis
- improve CTA clarity inside the defined area

### 9. Acceptance criteria
Define how the revision will be judged.

Acceptance criteria should be observable.

Examples:
- The revised area is easier to scan in under 5 seconds.
- All original components remain present.
- The hierarchy is clearer without introducing new sections.
- The screen still feels native to the product.

### 10. Notes or rationale
Use this section for short supporting context only if needed.

This may include:
- why the change matters
- what triggered the revision
- what user feedback or review concern led to the request

## Change request template
Use the following structure when creating an actual request.

### Request identity
- Request name:
- Related screen:
- Version being changed:

### Revision mode
- Preserve / Refine / Structural

### Problem being solved
-

### Desired outcome
-

### Scope of change
-

### Locked items to preserve
-

### Explicitly forbidden changes
-

### Allowed changes
-

### Acceptance criteria
-

### Notes or rationale
-

## Guidance for writing strong change requests
A strong request should:
- focus on one problem at a time
- keep scope tight
- preserve more than it changes
- define what success looks like
- make non-destructive intent explicit

A weak request usually sounds like:
- improve this screen
- make it better
- redesign the layout
- fix the UX

These broad instructions increase drift because they force the AI to reinterpret too much at once.

## Recommended review rule
After any revision, review the result against the request before accepting it.

Check:
- Was the requested problem actually improved?
- Did the AI stay inside the defined scope?
- Were all locked items preserved?
- Did the AI introduce any unapproved drift?
- Does the revised screen still align with the screen spec and product shell?

If the answer to any of these is no, the revision should be corrected before moving on.

## Escalation rule
If multiple Preserve or Refine requests fail to solve the issue, do not keep issuing broader vague prompts.

Instead:
- stop the iteration
- identify whether the real issue is structural
- update the screen spec if needed
- then create a deliberate Structural mode request

This prevents repeated prompt churn and avoids accidental redesign.

## Final instruction to AI
When working from a change request:
- read the request as the active revision contract
- preserve the current design unless a change is explicitly authorized
- treat locked items as fixed constraints
- apply only the requested level of change
- prefer a smaller safe edit over a larger risky reinterpretation
