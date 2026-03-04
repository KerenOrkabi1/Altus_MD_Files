# Screen Spec - Project Overview (V1 Contract)

## Purpose

This file defines the first-version screen contract for the Project Overview experience.

This is the screen-level specification used to generate the first controlled version of the page. It defines what must be true when version 1 is created, even if some detail remains intentionally open for refinement.

This file should work with:

* `masterplan_project_overview.md`
* `user-journey_project_overview.md`
* `design-guidelines_base.md`
* `rules_base.md`
* `product-shell_base.md`

## Screen identity

* Screen name: **Project Overview**
* Screen type: **High-level landing page for an individual project**
* Primary users: **Project Manager (PM)** and **PMO**
* Primary usage moment: **Open an individual project and quickly assess control, stability, and need for intervention**

## Core screen job

This screen must help the user quickly determine:

* Am I on track?
* Is anything critical?
* Do I need to act now?
* Where should I focus first?

The page should feel calm, high-signal, and decision-support oriented.

## Host layout dependency

This screen must be generated inside the host product frame defined in `product-shell_base.md`.

That means:

* the left navigation shell already exists
* the top product area already exists
* this file defines the page content inside the remaining content canvas

The shell is not part of the editable page body for this screen.

## V1 design principle

Version 1 should optimize for:

* fast scanability
* stable information hierarchy
* confidence in project control
* clear drill-down paths
* subtle AI augmentation without overpowering the baseline experience

Version 1 should not attempt to solve every detailed workflow on this page.

## Required outcome

The first generated version must:

* remain high-level
* support fast project health assessment
* surface attention areas clearly
* preserve a clear separation between baseline project facts and AI support
* provide enough visibility to decide whether further investigation or action is needed

## Required information backbone

The screen must visibly cover the minimum backbone defined by the project direction:

### Main health domains

* Cost
* Schedule
* Scope
* Resources

### Supporting drift domains

* Risks
* Issues
* Dependencies
* Changes

These items must be represented in the first version, either as direct sections, summary cards, grouped modules, or clearly reachable drill-down entry points.

## Primary hierarchy

The screen uses a four-tier information hierarchy:

* **Tier 1 — Executive Status Summary**
  Overall project health signal and forecast visibility. Must be answerable above the fold without scrolling.

* **Tier 2 — Main Health Domains**
  Cost, Schedule, Scope, Resources. The primary decision-support view.

* **Tier 3 — Supporting Drift Domains**
  Risks, Issues, Dependencies, Changes. Explains where instability may be building.

* **Tier 4 — Drill-down only**
  Operational detail is not surfaced inline on the overview page. It is accessible only through drill-down navigation.

This hierarchy must be preserved across all V1 revisions unless explicitly replaced by a newer accepted decision.

## Above-the-fold expectation

The area above the fold must allow the user to answer the first three questions without scrolling:

* Am I on track?
* Is anything critical?
* Do I need to act now?

This area must include:

* the overall project health signal
* forecast visibility — the user must be able to understand expected project finish timing from the top-level experience without drilling down
* any immediately critical flags

Forecast visibility is a Tier 1 requirement. It must be present in the Executive Status Summary, not deferred to a drill-down view.

## Required screen sections for V1

The first version should include the following page sections inside the content canvas.

### 1. Executive status summary

A top summary area that helps the user understand the current overall state.

This section should:

* summarize the project status at a glance
* signal whether the project appears stable or drifting
* help the user quickly judge if intervention may be needed
* include forecast visibility so the user can understand expected project finish timing from the top-level experience

This may include a concise summary pattern, a status band, or a compact health overview, but it must stay calm and not dominate the full page.

### 2. Main health section

A primary section for the core control domains:

* Cost
* Schedule
* Scope
* Resources

This section should:

* provide the first detailed project control view
* make it easy to scan across the four core dimensions
* support direct comparison of where the project is healthy versus at risk

### 3. Supporting drift section

A secondary but still prominent section covering:

* Risks
* Issues
* Dependencies
* Changes

This section should:

* help explain where project drift may be building
* make attention areas visible without forcing deep investigation immediately
* support fast movement to the right detailed area when needed

### 4. AI support section

A dedicated area for AI assistance when AI is enabled.

This section should:

* sit on top of the same project control model, not replace it
* remain visually subordinate to the main project state
* adapt based on AI maturity level
* distinguish AI-added insight clearly enough for user trust

### 5. Next-step and drill-down actions

A clear set of entry points that helps the user move from insight to action.

This section should support actions such as:

* open the relevant detailed area
* investigate a flagged issue
* follow up with an owner
* escalate when needed
* move into deeper project management views

### Zone E ordering rule

Within the Next Steps and Drill-Down Actions section, attention-flagged domains must appear first.

Entry points for domains with no active flags remain present but should be visually de-emphasised.

This ensures the user's eye is drawn toward the actions that matter most, rather than presenting all drill-down paths at equal weight.

## Section ordering rule

The V1 page must follow this section order:

1. Executive Status Summary
2. Main Health Domains
3. Supporting Drift Domains
4. AI Support Layer
5. Next Steps and Drill-Down Actions

This order is locked for V1. It reflects the intended scan flow from immediate health signal through to action. It must not be changed without an explicit approved revision.

## Interaction requirements

The screen must support the following interaction behavior:

* fast scan without mandatory interaction
* clear clickable or navigable drill-down paths into detailed areas
* stable section boundaries so users can predict where information lives
* optional AI-assisted interpretation when available
* progression from awareness to action without requiring the AI layer

## AI behavior in the screen

The page must support the following AI maturity states:

* **AI Off**
  No AI-generated content is shown on the page. The user relies entirely on direct project facts and status signals.

* **Level 1 — Descriptive**
  AI summarizes the current project state in plain language. It describes what is visible without interpretation beyond the data.

* **Level 2 — Diagnostic**
  AI explains why something may be off track by connecting signals across cost, schedule, scope, resources, risks, issues, dependencies, and changes.

* **Level 3 — Predictive**
  AI highlights likely future drift, likely next slippages, and emerging risks based on patterns and recent signals.

* **Level 4 — Agentic**
  AI suggests the next best action and may help prepare follow-up steps, communications, or interventions, while keeping the human in control.

### AI layer rules for this screen

* The AI Support Layer sits after the Supporting Drift Domains section in the page order.
* AI must remain visually and functionally subordinate to core project facts at all maturity levels.
* The page must remain fully usable with AI Off. AI should enhance judgment, not replace the baseline experience.
* AI must not become the sole path to understanding project health at any level.

## Layout expectations

The layout should:

* fit naturally inside the existing product shell
* use an enterprise-style information hierarchy
* support quick left-to-right and top-to-bottom scanning
* use cards, panels, sections, or similar structured containers where helpful
* avoid dense walls of text
* preserve a calm, controlled visual rhythm

## Locked constraints for V1

Unless explicitly changed by a later approved revision, AI must preserve these constraints in the initial generated version:

* the page remains a high-level overview, not a detailed workspace
* the main health domains remain primary
* the supporting drift domains remain visible and easy to access
* the AI layer remains secondary to core project facts
* the design must align to the host product shell and existing product patterns
* the page must include a clear path from signal to drill-down action

## What AI must not do

When generating the first version, AI must not:

* redesign the product shell
* omit one of the core required information domains without an explicit reason
* replace direct factual visibility with AI-only summaries
* create a visually noisy or overly promotional AI experience
* introduce an entirely new page model that feels disconnected from the existing product
* turn the page into a deep operational screen with excessive detail

## Intentional open items for later refinement

The following may still be refined after the first controlled version is created:

* exact card pattern and grouping model
* exact visual treatment of the executive summary
* exact CTA pattern for next-step actions
* detailed content density within each section
* exact non-AI treatment of the AI support area (for example, hidden vs minimal enable treatment)
* exact visual pattern for Level 3 predictive signals within cards

These can evolve later, but the core structure and hierarchy in this file should remain stable unless explicitly changed.

## Success criteria for V1 review

The first version is successful if a reviewer can confirm that:

* the screen feels native to the existing product
* the first 5-second questions are answerable quickly
* the main health domains are easy to scan
* the drift domains are visible and useful
* AI support is helpful but not visually dominant
* the page supports judgment first and drill-down second
* the page feels structured, calm, and trustworthy
