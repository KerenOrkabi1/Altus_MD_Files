# Masterplan - Project Overview (High Level)

## Overview

This file defines the overall direction, scope, and working intent for the Project Overview experience.

The Project Overview is the high-level landing page for an individual project. It should help a Project Manager (PM) or PMO quickly understand whether the project is under control, where attention is needed, and whether action is required.

This file is the primary source of truth for the overall direction of the experience. Supporting files such as `tasks_project_overview.md`, `rules_base.md`, `design-guidelines_base.md`, and `user-journey_project_overview.md` should align to it.

## Outcome Spec

### Audience and context

* Primary users: Project Manager (PM) and Project Management Office (PMO)
* Usage moment: This is the project landing page users see when they open an individual project
* Primary usage intent: Quickly understand whether the project is under control, where attention is needed, and whether intervention is required

### Job to be done

* Help me stay on top of my project, reduce surprises, and maintain control over delivery.

### Core user intent

The Project Overview should help the PM or PMO determine, at a glance:

* Whether the project is stable or drifting
* Whether intervention is needed now
* Which areas need attention first
* What has changed since the last review
* What action, if any, should be taken next

### Decisions supported

The page should support the following high-level decisions:

1. Do I need to escalate?
2. Do I need to reallocate resources?
3. Do I need to adjust the schedule?
4. Do I need risk mitigation?
5. Do I need stakeholder communication?
6. Do I need budget correction?
7. Do I need scope or change approval?

### Stakeholder communication — V1 scope decision

In V1, stakeholder communication is not given a dedicated visibility block or direct trigger on the Project Overview page.

The need for stakeholder communication is expected to be inferred by the user from the signals already visible across cost, schedule, scope, resources, risks, issues, dependencies, and changes.

This decision is intentional and scoped to V1. It may be revisited in a later iteration if a dedicated stakeholder communication signal is justified.

### Must-have information blocks

The page must include high-level visibility into:

* Cost
* Schedule
* Scope
* Resources

It must also surface key elements that may cause project drift:

* Changes
* Dependencies
* Risks
* Issues

These together form the minimum information backbone for the Project Overview.

### Forecast visibility

The user must be able to understand expected project finish timing from the top-level experience without drilling down.

Forecast visibility is a Tier 1 requirement. It belongs in the Executive Status Summary and must not be deferred to a drill-down view.

### Scope intent

This page is intended to remain high-level. It should prioritize project control and decision support rather than deep operational detail.

### Non-AI baseline behavior

In the non-AI state, the page should help users answer project control questions through structured, visible facts and signals. The experience should rely on clear status indicators, summaries, and direct access to the core project health dimensions:

* Cost
* Schedule
* Scope
* Resources
* Risks
* Issues
* Dependencies
* Changes

The baseline experience should enable users to judge whether action is needed without relying on AI interpretation.

### AI-augmented intent

When AI is enabled, the experience should not replace the baseline decisions. Instead, AI should improve the user's ability to:

* Intervene earlier than planned
* Detect what is likely to slip next
* Identify what is trending off track
* Understand what changed since the last review
* Focus limited attention on the highest-priority concerns
* Receive recommended actions

AI should act as a layer of support on top of the same project control model, not as a separate experience.

### AI maturity levels

The experience should support five states:

* Default / AI Off
  No AI support. The user relies on direct project facts, status signals, and standard project controls.

* Level 1 - Descriptive
  AI summarizes what is already happening. It helps explain the current state in plain language without interpretation beyond what is visible in the data.

* Level 2 - Diagnostic
  AI helps explain why something may be off track by connecting visible conditions across cost, schedule, scope, resources, risks, issues, changes, and dependencies.

* Level 3 - Predictive
  AI highlights likely future drift, likely next slippages, and emerging risks based on patterns and recent signals.

* Level 4 - Agentic
  AI goes beyond insight and recommendation by helping prepare next steps, such as drafting follow-up actions, communications, or proposed interventions, while keeping the human in control.

### Design intent for AI behavior

Across all AI-enabled levels:

* AI should feel supportive, subtle, and trustworthy
* AI should reduce cognitive load, not add noise
* AI should help the user focus, not intimidate them
* Each level must feel meaningfully different in purpose and value

### Early success criteria

This Outcome Spec will be considered successful if it enables:

* A clear separation between non-AI baseline and AI augmentation
* Prototype concepts that can be evaluated against the same decision-support goals
* Easy refinement later without rewriting the whole structure

### Known gaps to refine later

This v1 spec still needs deeper definition for:

* Specific thresholds and signals for each decision
* Detailed do / do not rules per AI level
* Trust and transparency requirements
* Exact page sections and interaction model
* Success and failure criteria at a more measurable level

## Scope and constraints

### In scope

* A high-level Project Overview landing page for an individual project
* Decision support for PM and PMO users
* A clear non-AI baseline experience
* AI maturity layering from descriptive to agentic
* Conceptual structure for information hierarchy and user focus

### Out of scope

* Deep transactional workflows
* Full project editing experiences
* Detailed configuration or admin settings
* Backend logic, integrations, and implementation specifics
* Final production-ready interaction details

### Constraints

* The page must remain high-level and scannable
* AI should enhance judgment, not overpower the user
* The experience should prioritize control, clarity, and focus
* The design should support progressive refinement over time

## File structure

This project uses separate files with clear responsibilities:

* `masterplan.md`
  Defines the overall direction, intent, scope, and core decision-support model.

* `tasks.md`
  Breaks the work into small executable steps in the correct order.

* `rules.md`
  Defines how the AI or generator should behave while creating or refining outputs.

* `design-guidelines.md`
  Captures design principles, UX tone, layout behavior, and visual intent.

* `user-journey.md`
  Describes the user flow from opening the project to taking action.

Each file should stay focused on its role and avoid duplicating the function of the others.

## Current assumptions

* PM and PMO users need fast project control visibility from the landing page
* The Project Overview should be useful even with AI turned off
* AI value should increase progressively across maturity levels
* The same core project control model should support both non-AI and AI-enhanced experiences
* The first version should prioritize clarity over completeness

## Open questions

The following areas still need to be defined in later iterations:

* The precise do / do not behavior for each AI level
* What trust and transparency signals must appear in the UI
* Which actions should be directly available from the overview page
* Whether quality needs a dedicated visibility block in a future version

### Closed in V1

The following questions were open in the initial masterplan and have since been resolved:

* **Page sections and layout structure** — confirmed as five sections in a locked order: Executive Status Summary, Main Health Domains, Supporting Drift Domains, AI Support Layer, Next Steps and Drill-Down Actions
* **Stakeholder communication visibility** — confirmed as inferred from other signals in V1, no dedicated block
* **Forecast visibility** — confirmed as a Tier 1 requirement within the Executive Status Summary
* **Information hierarchy** — confirmed as a four-tier model: Tier 1 Executive Status Summary, Tier 2 Main Health Domains, Tier 3 Supporting Drift Domains, Tier 4 Drill-down only
