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

Replaced

### Supersedes

None

### Must remain true

* this entry remains part of history only
* future generation must not treat the old five-section structure as the active model
* any use of this structure must be explicitly framed as historical V1

### Notes / validation

Replaced by DL-003 after review of the latest prototype and stable refinement pass.

---

### ID

DL-003

### Date

2026-03-10

### Screen / Scope

Project Overview / Active page structure

### Decision

Replace the earlier five-section V1 structure with a three-layer active model: Executive Summary, optional AI Insight Layer, and unified Diagnostic + Drill-down.

### Reason

The latest prototype review showed the need for a faster scan model, less duplication, clearer AI placement, and stronger structural consistency across tools.

### Impact

* simplifies the scan path
* removes unnecessary section fragmentation
* creates a cleaner generation target for Claude, Lovable, and Figma Make
* improves consistency between factual summary, AI support, and diagnostics

### Status

Accepted

### Supersedes

DL-002

### Must remain true

* the active model uses three primary layers inside the content canvas
* Executive Summary appears first
* AI Insight Layer appears second only when AI is enabled
* Diagnostic + Drill-down appears below as the unified domain layer
* the old Main Health, Supporting Drift, and separate Next Steps structure must not be treated as active unless explicitly requested as historical V1

### Notes / validation

Aligned to the active screen spec V2.

---

### ID

DL-004

### Date

2026-03-10

### Screen / Scope

Project Overview / Executive Summary

### Decision

Absorb the immediate-action answer into the Executive Summary and retire the separate standalone Next Steps section from the active page model.

### Reason

The top of the page must answer in under 30 seconds whether the user is on track, whether anything is critical, and whether action is needed now.

### Impact

* strengthens above-the-fold usefulness
* reduces page fragmentation
* keeps urgent action framing connected to overall status

### Status

Accepted

### Supersedes

DL-002

### Must remain true

* Executive Summary must answer: Am I on track, Anything critical, Do I need to act now
* if action is needed, the summary should present one primary next action and may include one or two secondary follow-ups
* deeper fix destinations belong in the Diagnostic + Drill-down section, not in a standalone Next Steps block

### Notes / validation

This is an active screen rule, not a temporary demo-only treatment.

---

### ID

DL-005

### Date

2026-03-10

### Screen / Scope

Project Overview / AI placement and containment

### Decision

Show AI content only in a dedicated AI Insight Layer directly below the Executive Summary when AI is enabled.

### Reason

The baseline non-AI page must stay clear, trustworthy, and usable on its own. AI should act as an additive interpretation layer rather than blending into baseline facts or card content.

### Impact

* preserves separation between factual project signals and AI interpretation
* reduces duplication and visual noise
* improves stability of cross-tool generation

### Status

Accepted

### Supersedes

DL-002

### Must remain true

* when AI is off, no AI section is shown
* when AI is on, the AI Insight Layer appears directly under the Executive Summary
* no AI content appears inside domain cards
* no AI explanation is embedded into baseline Executive Summary factual content
* the baseline page remains fully usable with AI off

### Notes / validation

This replaces the older V1 placement where AI sat after supporting drift.

---

### ID

DL-006

### Date

2026-03-10

### Screen / Scope

Project Overview / AI interaction

### Decision

The AI Insight Layer is interactive and updates in place based on AI On/Off state and the selected maturity level.

### Reason

Different maturity levels must feel meaningfully different without restructuring the whole page or showing multiple AI states at once.

### Impact

* preserves a stable page frame while allowing interactive AI behavior
* reduces ambiguous generation of AI controls across tools
* keeps baseline sections structurally unchanged when AI state changes

### Status

Accepted

### Supersedes

None

### Must remain true

* the AI level selector is visible only when AI is on
* only one AI maturity state is shown at a time
* changing maturity updates the same AI container in place
* changing AI state or maturity must not convert baseline sections into AI variants
* AI interaction behavior belongs to the screen contract even if control styling remains open

### Notes / validation

Visual control choice can remain flexible; the behavior contract is fixed.

---

### ID

DL-007

### Date

2026-03-10

### Screen / Scope

Project Overview / AI maturity behavior

### Decision

Use one shared AI container across maturity levels, with distinct content behavior by level: Descriptive, Diagnostic, Predictive, and Agentic.

### Reason

Cross-tool generation requires a stable behavior contract so each maturity level does not collapse into the same content shape.

### Impact

* increases differentiation across maturity levels
* reduces repeated or generic AI output
* protects the intended AI maturity model in prototype generation

### Status

Accepted

### Supersedes

None

### Must remain true

* Level 1 focuses on plain-language description of visible status
* Level 2 focuses on likely drivers and causal interpretation
* Level 3 focuses on likely future drift, slippage, or emerging risk
* Level 4 focuses on next best action, intervention options, simulation, or recommended-response framing while keeping the human in control
* AI behavior should differ by purpose, not just by wording tone

### Notes / validation

The same visual container may be reused across levels; the content behavior must change.

---

### ID

DL-008

### Date

2026-03-10

### Screen / Scope

Project Overview / Diagnostic + Drill-down structure

### Decision

Merge Main Health Domains and Supporting Drift Domains into one unified Diagnostic + Drill-down section.

### Reason

The latest review favored a single evidence layer that explains severity, cause, source, and path to fix without repeating the executive summary.

### Impact

* simplifies the middle of the page
* improves scan-to-investigation flow
* reduces artificial separation between control and drift evidence

### Status

Accepted

### Supersedes

DL-002

### Must remain true

* the active page uses one unified diagnostic domain section
* the section must help answer: what is driving the issue, how serious is it, where is it coming from, where do I fix it, what must be updated
* deeper operational detail is still reached by navigation rather than fully exposed inline

### Notes / validation

The section keeps both control and drift visibility but in one structured layer.

---

### ID

DL-009

### Date

2026-03-10

### Screen / Scope

Project Overview / Diagnostic domain visibility

### Decision

Always show the four core control domains first, and conditionally show remaining drift domains only when they are problematic or newly recovered, with a Show all domains reveal option.

### Reason

This preserves a stable backbone while reducing noise and allowing the page to focus on what currently matters.

### Impact

* keeps essential control coverage visible at all times
* reduces clutter from healthy secondary domains
* supports both problem and recovery storytelling

### Status

Accepted

### Supersedes

None

### Must remain true

* Cost, Schedule, Scope, and Resources are always visible in the diagnostic layer
* Risks, Issues, Dependencies, and Changes are conditionally shown when problematic or newly green since the last review
* the interface may provide a Show all domains option to reveal the full set
* healthy secondary domains should not dominate the default view

### Notes / validation

Supports the demo need to show both healthy and at-risk scenarios without changing the page model.

---

### ID

DL-010

### Date

2026-03-10

### Screen / Scope

Project Overview / Diagnostic card contract

### Decision

Use a compact card contract in the Diagnostic + Drill-down section: title, RAG status dot, trend cue, top three signals, and expand/collapse affordance.

### Reason

The cards must support fast scan first, then progressive reveal, while staying consistent across domains and tools.

### Impact

* improves scanability
* standardizes domain-card generation
* supports progressive disclosure without overloading the overview

### Status

Accepted

### Supersedes

None

### Must remain true

* each diagnostic card shows a title
* each title includes a small RAG color status cue for current domain state
* each card includes a trend cue beside the title
* each card shows the top three most relevant signals in collapsed state
* cards should support a consistent expand/collapse pattern

### Notes / validation

Trend states may include worsening, unchanged, improving, and recovered.

---

### ID

DL-011

### Date

2026-03-10

### Screen / Scope

Project Overview / Diagnostic card interactivity

### Decision

Diagnostic cards are collapsed by default and can be expanded to reveal a limited set of supporting details and deep links.

### Reason

The overview must remain high-level by default while still allowing targeted investigation and navigation to fix areas.

### Impact

* protects overview simplicity
* supports interactive drill-down behavior
* avoids turning the page into a dense workspace

### Status

Accepted

### Supersedes

None

### Must remain true

* cards are collapsed by default
* expanded state reveals approximately two to four extra diagnostic details
* expanded state may show one to three drill-down destinations where the user can investigate or fix the issue
* expanded state may indicate what needs updating at a high level
* expansion must not expose full operational detail inline

### Notes / validation

Possible destinations may include multiple targets such as schedule view and milestone view.

---

### ID

DL-012

### Date

2026-03-10

### Screen / Scope

Project Overview / Information separation

### Decision

Enforce a hard separation between Executive Summary, AI Insight Layer, and Diagnostic + Drill-down so the same content is not redundantly repeated across layers.

### Reason

Prototype review showed a need to reduce duplication and make each layer answer a different type of question.

### Impact

* improves clarity of purpose by section
* reduces repetitive content
* makes cross-tool generation easier to validate

### Status

Accepted

### Supersedes

None

### Must remain true

* Executive Summary focuses on overall state, criticality, and immediate-action signal
* AI Insight Layer focuses on AI-specific interpretation according to the active maturity level
* Diagnostic + Drill-down focuses on evidence, severity, source, cause, and path to fix
* the same KPI or fact should not be repeated across layers unless needed for comprehension

### Notes / validation

This is a stable UX rule and should be enforced during generation and review.

---

### ID

DL-013

### Date

2026-03-10

### Screen / Scope

Project Overview / Executive Summary layout

### Decision

Use a two-sided Executive Summary layout: decision-oriented summary on the left and compact forecast context on the right.

### Reason

The top layer needs to support a very fast scan. Separating immediate decision answers from forecast context makes it easier for the user to understand status first and supporting outlook second.

### Impact

* improves first-glance clarity
* creates a more stable summary layout across tools
* prevents forecast details from diluting the immediate decision signal

### Status

Accepted

### Supersedes

None

### Must remain true

* the left side answers: Am I on track, Anything critical, Do I need to act now
* the right side contains compact forecast-level context such as forecast finish, forecast cost, or equivalent forward-looking summary measures
* the left side leads the scan and action decision
* the right side supports the summary without turning into a diagnostic section

### Notes / validation

Aligned to the active screen spec V3.

---

### ID

DL-014

### Date

2026-03-10

### Screen / Scope

Project Overview / Diagnostic layout

### Decision

Anchor the Diagnostic + Drill-down section with a first row of the four core domains, then place remaining domains underneath using the same card styling and interaction pattern.

### Reason

The user needs a stable domain backbone for scanning. Fixing the first row to Schedule, Scope, Cost, and Resources improves consistency while allowing additional domains to appear beneath without changing the model.

### Impact

* strengthens layout consistency across tools
* preserves the core-control scan pattern
* keeps additional domains visually aligned with the same card contract

### Status

Accepted

### Supersedes

None

### Must remain true

* the first diagnostic row contains Schedule, Scope, Cost, and Resources
* additional domains such as Risks, Issues, Dependencies, and Changes appear underneath when shown
* additional domains use the same styling, card contract, and expand/collapse behavior as the core row
* secondary domains do not replace or reorder the core row by default

### Notes / validation

Aligned to the active screen spec V3.
