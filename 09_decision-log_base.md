# decision-log_base

## Purpose

Capture stable design decisions over time so AI and humans do not unintentionally undo them in later iterations.

Use this file to:

* record what was intentionally decided
* explain why it was decided
* define what must remain true going forward
* reduce design drift across revisions, tools, and team members

This is not a brainstorming file.
It is a record of accepted decisions.

---

## How AI should use this file

* Treat accepted decisions in this file as stable unless a newer entry explicitly replaces them.
* Do not silently reverse or override a logged decision.
* If a requested change conflicts with a logged decision, flag the conflict before applying the change.
* Use this file together with:

  * the masterplan
  * screen spec
  * product shell
  * design guidelines
  * rules
  * change request

Priority rule:

* The newest accepted decision overrides older conflicting decisions.
* If there is no conflict, all accepted decisions remain in force.

---

## Entry format

Use one entry per accepted design decision.

### Required fields

* **ID**: unique identifier
* **Date**
* **Screen / Scope**
* **Decision**
* **Reason**
* **Impact**
* **Status**
* **Supersedes** (if relevant)
* **Must remain true**
* **Notes / validation**

### Status values

* **Accepted**
* **Replaced**
* **Deprecated**
* **Proposed** (only temporary; do not treat as stable until accepted)

---

## Entry template

### ID

DL-001

### Date

YYYY-MM-DD

### Screen / Scope

Example: Project Overview / Right panel

### Decision

Describe the decision that was intentionally made.

### Reason

Why this decision was made.
Reference user need, usability concern, business rule, platform constraint, or brand alignment.

### Impact

What this changes or protects.
Example:

* improves scanability
* preserves interaction consistency
* reduces visual noise
* aligns with existing product shell

### Status

Accepted

### Supersedes

None
or
DL-000

### Must remain true

List the things future revisions must preserve because of this decision.
Example:

* keep the primary KPI in the top-right summary area
* do not move the progress indicator below supporting metrics
* preserve the current section grouping

### Notes / validation

Optional notes, review comments, screenshots, or acceptance observations.

---

## Example entry

### ID

DL-001

### Date

2026-03-02

### Screen / Scope

Project Overview / Overall page structure

### Decision

Keep the existing product shell fixed and design new page content only inside the content canvas.

### Reason

The shell is part of the existing Altus product experience and should remain visually and structurally consistent across pages.

### Impact

* preserves brand consistency
* reduces unnecessary redesign
* keeps generated screens aligned with the host product

### Status

Accepted

### Supersedes

None

### Must remain true

* left navigation remains part of the persistent shell
* top product/header area remains part of the persistent shell
* page generation should focus on the content region inside the shell
* future revisions must not redesign the shell unless explicitly requested

### Notes / validation

Applies to all first-pass generation and later iterations unless replaced by a newer accepted entry.

---

## Accepted entries for Project Overview

### ID

DL-002

### Date

2026-03-03

### Screen / Scope

Project Overview / Page structure

### Decision

The V1 page must follow a fixed five-section order: Executive Status Summary, Main Health Domains, Supporting Drift Domains, AI Support Layer, Next Steps and Drill-Down Actions.

### Reason

This order reflects the intended scan flow from immediate health signal through to action, as defined in the user journey and confirmed during Task 7 review.

### Impact

* locks the section order for all V1 generation and revision
* prevents section reordering during iterative refinement
* ensures the page supports the intended top-to-bottom scan pattern

### Status

Accepted

### Supersedes

None

### Must remain true

* the five sections must appear in this exact order in V1
* no section may be removed or reordered without an explicit approved revision
* future change requests must declare a structural revision mode to alter this order

### Notes / validation

Confirmed during Task 7 review. Captured in screen spec and masterplan.

---

### ID

DL-003

### Date

2026-03-03

### Screen / Scope

Project Overview / Information hierarchy

### Decision

The page uses a four-tier information hierarchy: Tier 1 Executive Status Summary, Tier 2 Main Health Domains, Tier 3 Supporting Drift Domains, Tier 4 Drill-down only.

### Reason

The hierarchy reflects the user's primary scan flow and ensures the most important information is answered above the fold without requiring drill-down navigation.

### Impact

* defines what is primary, secondary, and drill-down only
* prevents operational detail from surfacing inline on the overview page
* supports fast project health assessment at a glance

### Status

Accepted

### Supersedes

None

### Must remain true

* Tier 1 content must be answerable above the fold
* Tier 4 content must not appear inline on the overview page
* the hierarchy must be preserved across all V1 revisions

### Notes / validation

Confirmed during Task 7 review. Captured in screen spec and masterplan.

---

### ID

DL-004

### Date

2026-03-03

### Screen / Scope

Project Overview / Forecast visibility

### Decision

Forecast visibility is a Tier 1 requirement. The user must be able to understand expected project finish timing from the Executive Status Summary without drilling down.

### Reason

The user's immediate need on opening the page includes understanding whether the project is on track to finish as expected. Deferring this to a drill-down view would fail the first 5-second scan requirement.

### Impact

* forecast visibility must be present in the Executive Status Summary
* it must not be deferred to a drill-down view
* all V1 generation must treat this as a required above-the-fold element

### Status

Accepted

### Supersedes

None

### Must remain true

* forecast visibility is always present in the Executive Status Summary
* it is never moved to a secondary or drill-down section without an explicit approved revision

### Notes / validation

Confirmed during Task 7 review. Captured in screen spec and masterplan.

---

### ID

DL-005

### Date

2026-03-03

### Screen / Scope

Project Overview / AI Support Layer

### Decision

The AI Support Layer must sit after the Supporting Drift Domains section in the page order and must remain visually and functionally subordinate to core project facts at all AI maturity levels. The page must remain fully usable with AI Off.

### Reason

AI should enhance the user's judgment without replacing or overpowering the baseline project control experience. The core facts must always be the primary signal.

### Impact

* AI layer placement is locked after Supporting Drift Domains
* AI content must not dominate the visual hierarchy at any maturity level
* the page must be complete and usable without any AI-generated content

### Status

Accepted

### Supersedes

None

### Must remain true

* AI Support Layer always appears after Supporting Drift Domains
* AI never becomes the sole path to understanding project health
* the page remains fully usable with AI Off

### Notes / validation

Confirmed during Task 7 review. Captured in screen spec.

---

### ID

DL-006

### Date

2026-03-03

### Screen / Scope

Project Overview / AI maturity levels

### Decision

The page supports five AI states: AI Off, Level 1 Descriptive, Level 2 Diagnostic, Level 3 Predictive, Level 4 Agentic. Each level must feel meaningfully different in purpose and value.

### Reason

The AI maturity model is the core progression framework for this experience. Each level must add distinct value so users understand what they gain as AI support increases.

### Impact

* all five states must be supported in the screen model
* each level has a distinct purpose: what, why, prediction, recommended action
* no two levels should feel equivalent in what they offer the user

### Status

Accepted

### Supersedes

None

### Must remain true

* all five AI states remain supported
* the level definitions must not be merged or collapsed without an explicit approved revision

### Notes / validation

Confirmed during Task 7 review. Captured in screen spec and masterplan.

---

### ID

DL-007

### Date

2026-03-03

### Screen / Scope

Project Overview / Next Steps and Drill-Down Actions (Zone E)

### Decision

Within the Next Steps and Drill-Down Actions section, attention-flagged domains must appear first. Entry points for domains with no active flags remain present but should be visually de-emphasised.

### Reason

Presenting all drill-down paths at equal visual weight forces the user to scan the full list before identifying where action is needed. Prioritising flagged domains reduces cognitive load and supports faster decision-making.

### Impact

* Zone E must not present all entry points at equal visual weight
* flagged domains always appear before unflagged ones in this section
* unflagged entry points remain accessible but are not given equal prominence

### Status

Accepted

### Supersedes

None

### Must remain true

* attention-flagged domains appear first in Zone E at all times
* unflagged domains remain present and reachable but visually subordinate
* this ordering rule applies to V1 and carries forward unless explicitly revised

### Notes / validation

Confirmed during Task 7 review. Captured in screen spec.

---

### ID

DL-008

### Date

2026-03-03

### Screen / Scope

Project Overview / Stakeholder communication — V1 scope

### Decision

In V1, stakeholder communication is not given a dedicated visibility block or direct trigger on the Project Overview page. The need for stakeholder communication is inferred by the user from signals visible across cost, schedule, scope, resources, risks, issues, dependencies, and changes.

### Reason

A dedicated stakeholder communication block was not justified for V1 given the available signals. The existing information backbone is sufficient for the user to infer when communication is needed.

### Impact

* no dedicated stakeholder communication card, section, or trigger in V1
* the decision to communicate with stakeholders remains with the user based on visible signals
* this may be revisited in a later iteration if a dedicated signal is justified

### Status

Accepted

### Supersedes

None

### Must remain true

* V1 must not introduce a dedicated stakeholder communication block without an explicit approved revision
* the inference model remains in place for V1

### Notes / validation

Confirmed during Task 7 review. Captured in masterplan.

---

### ID

DL-009

### Date

2026-03-03

### Screen / Scope

Project Overview / Shell and content canvas boundary

### Decision

All Project Overview page content must be designed inside the content canvas only. The left navigation shell and top product area are locked shell elements and must not be redesigned, restyled, or restructured as part of this screen.

### Reason

The shell is part of the existing Altus product experience and must remain visually and structurally consistent across pages. The Project Overview is an extension of the existing product, not a standalone application.

### Impact

* page generation and revision work is scoped to the content canvas only
* the left navigation and top product area are treated as fixed constraints
* no initiative-specific work may move shell-level controls into the page body

### Status

Accepted

### Supersedes

None

### Must remain true

* the left navigation shell remains outside the editable page area
* the top product area remains outside the editable page area
* all V1 generation and future revisions must respect this boundary
* this constraint applies unless explicitly overridden by a product-level shell redesign decision

### Notes / validation

Confirmed as an applied decision for the Project Overview screen. Consistent with the shell preservation rules in `06_product-shell_base.md`.

---

## Working rules for the team

* Only log decisions that are actually accepted.
* Do not log every idea or suggestion.
* When a major design change is approved, add a new entry rather than rewriting history.
* If a new decision replaces an old one, mark the old one as **Replaced** and reference the new ID.
* Review this log before major revisions to avoid undoing stable choices.

---

## Recommended usage in workflow

1. Generate or revise a screen.
2. Review what was intentionally decided.
3. Add accepted decisions to this log.
4. Use this log as an input for future iterations.
5. Check new change requests against this log before editing.

This file becomes the persistent memory for design intent outside the chat thread.
