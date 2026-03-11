# Change Request — Project Overview CR-001

## Purpose
This file is the active revision contract for a specific refinement pass of the Project Overview screen.

It should be used together with:

* `01_masterplan_project_overview.md`
* `02_user-journey_project_overview.md`
* `03_design-guidelines_base.md`
* `04_rules_base.md`
* `06_product-shell_base.md`
* `07_screen-spec_project_overview.md`
* `08_change-request_base_UPDATED.md`
* `09_decision-log_base.md`
* `10_fluent-ui_base.md`

This file does not replace the core files.
It defines the permitted change scope for this specific revision pass.

---

## Request identity

* **Request name:** Apply approved diagnostic card contract to current Project Overview implementation
* **Request ID:** CR-001
* **Related screen:** Project Overview
* **Current source being revised:** Current generated Project Overview prototype / preview
* **Version being changed:** Current post-structure-refinement version

---

## Source-of-truth files

The following files remain the governing source of truth for this revision:

* `01_masterplan_project_overview.md`
* `03_design-guidelines_base.md`
* `04_rules_base.md`
* `06_product-shell_base.md`
* `07_screen-spec_project_overview.md`
* `09_decision-log_base.md`
* `10_fluent-ui_base.md`

This change request must be interpreted as a bounded refinement layer on top of those files, not a replacement for them.

---

## Revision mode

**Refine**

This request does not introduce a new page model.
It applies the already approved card and content rules to the current implementation while preserving the active three-layer Project Overview structure.

---

## Problem being solved

The core rules for the Project Overview screen are now updated, but the current generated implementation may not yet fully reflect them.

This refinement is needed to ensure that:

* diagnostic cards follow the approved collapsed and expanded structure
* card content stays factual and data-based
* AI-generated interpretation remains contained to the AI Insight Layer
* the screen preserves the active three-layer page model
* responsiveness and alignment issues are corrected without introducing structural drift

---

## Desired outcome

The revised screen should:

* preserve the active page structure:
  1. Executive Summary
  2. AI Insight Layer (only when AI is on)
  3. Diagnostic + Drill-down
* apply the approved diagnostic card pattern consistently across all domains
* keep card content factual and clearly separated from AI reasoning
* preserve shell alignment and overall page calmness
* improve responsiveness and layout alignment where needed
* remain high-level, decision-support oriented, and easy to scan

---

## Scope of change

This request applies only to:

* the Diagnostic + Drill-down card structure and content behavior
* card expansion behavior
* factual-only card-content enforcement
* AI off/on containment behavior where needed for compliance
* responsive layout corrections for Executive Summary and diagnostic-card layout
* minor alignment and spacing adjustments needed to support the approved rules

---

## Locked items to preserve

The following must remain unchanged unless explicitly required for compliance with the approved core rules:

* the host product shell
* the active three-layer Project Overview structure
* Executive Summary as the top factual layer
* AI Insight Layer directly below Executive Summary only when AI is enabled
* Diagnostic + Drill-down as the unified domain section
* the first diagnostic row containing Schedule, Scope, Cost, and Resources
* conditional visibility behavior for remaining drift domains
* the two-sided Executive Summary pattern
* AI maturity switching behavior
* the rule that AI content remains outside domain cards

---

## Explicitly forbidden changes

Do not:

* redesign the host product shell
* introduce a new page model
* reintroduce the older five-section V1 structure
* add AI-generated commentary inside domain cards
* move the AI Insight Layer elsewhere in the page
* turn diagnostic cards into a detailed workspace
* add speculative or advisory language into factual card content
* remove the visible Needs updating section from collapsed cards
* expose all secondary domains by default unless already justified by the current rules
* make broad visual redesign changes unrelated to this refinement

---

## Allowed changes

The following changes are allowed in this revision:

* update diagnostic cards so collapsed state shows:
  * title
  * current-state RAG
  * trend
  * exactly 3 factual key bullets
  * visible Needs updating
* update expanded cards so they:
  * retain all collapsed content
  * add exactly 2 factual supporting bullets between the first 3 bullets and Needs updating
  * add 1–3 drill-down links
* revise card content so all bullets and Needs updating remain factual and derived from available project data
* remove any AI-like interpretation from diagnostic cards
* correct AI-off behavior so no placeholder AI content is shown when AI is off
* adjust responsive layout so:
  * Executive Summary stacks cleanly when needed
  * forecast content moves below the decision-oriented summary when stacked
  * diagnostic cards reflow cleanly to fewer columns
  * card headers stay aligned without overlap
  * important summary content wraps before losing meaning
* make minor spacing, alignment, and container adjustments required to apply the approved rules cleanly

---

## Acceptance criteria

This change request is successful if the revised screen meets all of the following:

* the screen still follows the active three-layer Project Overview structure
* diagnostic cards follow the approved collapsed and expanded contract
* collapsed cards visibly show Needs updating
* expanded cards add exactly 2 factual supporting bullets before Needs updating
* diagnostic-card content remains factual and non-AI
* AI-generated reasoning appears only in the AI Insight Layer
* no placeholder AI section or AI placeholder text is shown when AI is off
* the first diagnostic row remains Schedule, Scope, Cost, and Resources
* additional domains use the same card contract underneath
* the page remains useful without expanding cards
* the screen remains readable and aligned at narrower widths
* the shell remains intact and visually dominant over page-level customization
* the page remains calm, high-signal, and suitable for fast executive scan

---

## Notes / rationale

This request applies already-approved core rules to the current implementation.

It should be treated as a bounded implementation refinement, not as a new concept exploration.

The stable diagnostic card pattern and factual-only trust rule already exist in the core files and should not be reinvented in this pass.
This request exists to make the current implementation comply with those approved rules.

---

## Promotion decision after review

After review, record one of the following outcomes:

* no promotion needed
* accepted and already aligned to current core files
* partially accepted with follow-up CR required
* rejected

Expected current outcome:
* accepted and already aligned to current core files, if the implementation successfully applies the approved rules without introducing drift
