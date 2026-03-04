# User Journey — Project Overview (High Level)

## Overview
This file describes the intended user flow for a PM or PMO using the Project Overview landing page for an individual project.

The purpose of the journey is to help the user quickly assess project health, identify whether intervention is needed, and take the right next action with confidence.

## Entry points
The user may open the Project Overview page when:
- performing a routine project check
- investigating a suspected issue
- preparing for a meeting
- generating a report or status view for stakeholders

The page is the primary entry point for understanding project health.

## Immediate user need
Within the first few seconds, the user should be able to answer:
- Am I on track?
- Is anything critical?
- Do I need to act now?

This first impression should be fast, clear, and confidence-building.

## Primary scan flow
The intended scan order is:

1. Main project health across:
   - Cost
   - Scope
   - Schedule
   - Resources

2. Supporting drift domains, with roughly equal importance:
   - Risks and issues
   - Dependencies
   - Changes

The main health view should provide the first overall signal. The supporting domains should help explain where the project may be drifting and what needs attention.

## Core questions during the session
During a typical visit, the user is trying to understand:
- Am I on track?
- Is anything critical?
- Do I need to act now?
- Where should I focus first?
- What changed since the last review?
- What needs follow-up?

## Decision point
The decision point happens after the user has reviewed:
- the main project health
- the supporting drift domains

At this stage, the user decides whether:
- the project is stable
- a specific area needs attention
- immediate intervention is required

## If action is needed
If the page indicates that action is needed, the user should be able to move toward the appropriate next step, such as:
- open the relevant item to address the issue
- escalate the issue
- add notes
- nudge or follow up with the owner

The next action depends on the type of issue identified.

## If no action is needed
If no immediate action is required, the page should still provide:
- a clear view of the main project health
- confidence that the project is under control
- a concise summary of current status

The experience should help confirm stability, not just highlight problems.

## AI role in the journey
AI should support the journey according to the active AI maturity level.

### AI maturity support across the journey
- **Level 1 — Descriptive:**  
  Provides the **what**.  
  AI summarizes the current project state in plain language and highlights the most important visible signals.

- **Level 2 — Diagnostic:**  
  Provides the **why**.  
  AI helps explain why something may be off track by connecting signals across cost, scope, schedule, resources, risks, issues, dependencies, and changes.

- **Level 3 — Predictive:**  
  Provides the **prediction**.  
  AI highlights what is likely to drift next, what may slip, and where emerging risk is building based on recent signals and patterns.

- **Level 4 — Agentic:**  
  Provides the **what to do next**.  
  AI recommends the next best action, such as where to focus attention, what to follow up, or what intervention should be considered next.

AI should support judgment and prioritization without replacing the core project control view.

## Drill-down behavior
This page should provide enough diagnostic visibility to help the user understand the issue at a high level.

When deeper investigation is needed, the page should allow the user to drill down by navigating to the relevant area.

The Project Overview should act as the decision-support entry point, not the final destination for all detailed work.

## End-of-session outcome
By the end of the session, the user should leave with:
- confidence in the current project state
- a clear next action, if needed
- awareness of any risk that requires follow-up
- fewer surprises

The page should help the user feel informed, focused, and in control.
