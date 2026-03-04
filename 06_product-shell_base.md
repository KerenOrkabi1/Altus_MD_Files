# Product Shell - Base

## Purpose

This file defines the reusable host application frame that all new screens should align to.

It is a base layout contract intended to preserve brand consistency, product familiarity, and structural continuity across initiatives.

This file defines the persistent shell only. Initiative-specific screen files should define the content that lives inside the shell, but should not override the shell unless there is an explicit product-level decision to do so.

## Scope

This file applies to the persistent application frame used by the Altus product experience, including:

* the left navigation area
* the top app bar
* the top product area
* the remaining page content canvas

This file does not define initiative-specific content.

## Shell reference assets

When available, uploaded shell reference images should be used as the primary visual reference for shell fidelity.

### Default shell reference

* **Primary reference image:** `altus-initiative-shell_reference.png`

This reference image should be treated as the preferred visual source for:

* left navigation content and grouping
* shell spacing and alignment
* shell styling and visual rhythm
* top app bar structure
* top product/header area structure
* stage/progress strip
* tab row behavior and layout

If a current uploaded shell reference image is available, it should be prioritized over generic assumptions.

### Area-specific shell variants

Some product areas may use different shell content while still following the same overall shell model.

Examples:

* Initiatives area
* Strategy area
* Other product modules with different left navigation items or top header content

When a different area-specific shell reference image is provided:

* use the most relevant reference for that product area
* preserve that area's shell content and layout more literally for that run
* do not force one area's navigation content onto another area if the product context differs

If multiple shell references exist, the current prompt or initiative context should clarify which one to prioritize.

## Layout contract

The application uses a persistent shell with four major regions:

1. Left navigation shell
2. Top app bar
3. Top product area
4. Main content canvas

All new screens must be designed inside this structure.

## Left navigation shell

### Width

* Expanded width: **200px**
* Collapsed width: **44px**

### Behavior

* The left navigation is persistent across screens.
* It is part of the core product shell, not the page content.
* New screens must assume this navigation already exists.
* New screens must not redesign, restyle, or restructure the left navigation unless there is an explicit product-level requirement.

### Design intent

* Preserve the established product navigation pattern.
* Maintain familiarity and orientation for returning users.
* Keep new page layouts visually aligned with the existing navigation rhythm.

### Visual fidelity rule

When a shell reference image is available:

* preserve the left navigation content, labels, grouping, ordering, spacing, and active-state pattern as closely as practical
* avoid replacing the existing navigation with a generic enterprise sidebar
* keep the navigation visually aligned to the actual Altus product area shown in the reference

### Color and contrast intent

* preserve the shell’s light left-navigation treatment
* preserve the established active-state emphasis and highlight pattern
* do not replace the left navigation with a different color model that changes the shell’s overall contrast relationship

## Top app bar

### Height

* Reserved height: **48px**

### Definition

The top app bar is the global application bar at the top of the product shell.

This bar is part of the persistent product frame and may include:

* product branding
* global actions
* product-level utility controls
* global assistant / Copilot access
* user/account access

### Behavior

* This bar is persistent across screens.
* It is part of the core product shell, not initiative-specific page content.
* New screens must not redesign, restyle, or restructure this bar unless a product-level shell redesign is explicitly requested.

### Visual fidelity rule

When a shell reference image is available:

* preserve the dark top app bar treatment
* preserve the overall structure, spacing, and utility-action rhythm
* avoid replacing it with a generic header bar that changes the shell identity

## Top product area

### Height

* Reserved height: **239px**

### Definition

The top product area is the persistent page-level frame below the top app bar and above the main content canvas.

This area provides the page-specific or object-specific product context and should align closely to the established Altus pattern.

This area may include:

* breadcrumb and project title
* project status context
* project metadata / summary row
* command actions (for example save, close, delete)
* stage / progress strip
* tab row / page-level sub-navigation

### Behavior

* This area is part of the host product frame.
* New screens should assume this reserved height already exists.
* New initiative work should align to it, not replace it.
* New screens must not redesign, restyle, collapse, or reinterpret this area unless that change is explicitly requested as part of a product-shell redesign.

### Design intent

* Preserve the existing branded product framing.
* Keep page-level context visible and predictable.
* Support continuity with the current product look and feel.
* Maintain recognisable Altus page framing before the content canvas begins.

### Visual fidelity rule

When a shell reference image is available:

* preserve the project header/banner structure as closely as practical
* preserve the breadcrumb/title/metadata layout pattern
* preserve the stage/progress strip structure
* preserve the tab row structure and placement
* keep spacing, alignment, and visual rhythm close to the reference
* avoid replacing the top product area with a generic app header or generic command bar layout

### Color and contrast intent

* preserve the shell’s existing contrast relationships between the dark top app bar, the lighter product area, and the content region
* do not introduce a new color model that makes the top shell feel unrelated to the Altus product frame
* approximate the current product shell colors if exact tokens are not provided, while preserving the same overall visual hierarchy

## Main content canvas

### Definition

The main content canvas is the only region that initiative-specific screen design should actively define by default.

### Available space

The content canvas begins:

* to the right of the left navigation shell
* below the top app bar
* below the top product area

The usable content width depends on whether the left navigation is expanded or collapsed.

### Working rule

By default, AI-generated page design should focus on this content canvas only.

Unless explicitly instructed otherwise:

* do not redesign the left navigation shell
* do not redesign the top app bar
* do not redesign the top product area
* do not move shell-level controls into the page body
* do not treat shell-level content as part of the editable screen layout

## Content alignment rules

New page content inside the content canvas should:

* align to the existing product spacing rhythm
* use clear gutters and consistent margins
* follow the existing card, panel, and tab conventions already used in the product
* preserve a calm, structured, enterprise-style layout
* prioritize scanability and hierarchy over decorative layout choices

## Visual system alignment

When generating new screens inside this shell:

* align to the current Altus product look and feel
* use **Fluent UI 9** as the default component foundation
* prefer matching existing approved product patterns before introducing new visual patterns
* keep the design visually compatible with the surrounding shell so the page feels native to the product

## Shell preservation rules

Unless explicitly requested otherwise, AI must treat the following as locked constraints:

* left navigation width values
* the existence of the left navigation shell
* the reserved top app bar height
* the existence of the top app bar
* the reserved top product area height
* the existence of the top product area
* the separation between shell and page content

AI must not:

* redesign the shell as part of a page-generation task
* replace shell-level navigation with a new page-specific navigation model
* merge shell content into the main page body
* create a page layout that ignores the reserved shell dimensions

## Shell fidelity expectation

When generating prototype screens:

* treat the shell as an existing product frame, not a new design problem
* preserve the shell as literally as practical when a shell reference image is available
* keep the shell content, spacing, layout structure, and styling close to the uploaded reference
* prefer approximation of the actual Altus shell over invention of a cleaner but generic alternative

Acceptable prototype limitations:

* exact icons may be approximated if the exact icon library is unavailable
* exact colors may be approximate if brand tokens are not explicitly provided
* shell components may be simplified structurally, but should remain recognizably aligned to the real product

These approximations should not change the fundamental shell pattern.

## Page-generation instruction

When generating a new page inside this product:

* use the product shell defined here as the fixed frame
* use the most relevant uploaded shell reference image when available
* place new content only inside the remaining content canvas unless instructed otherwise
* ensure the page feels like an extension of the existing product, not a separate application
* preserve the surrounding product shell so the resulting design maintains brand consistency and familiarity

## Prompt-level override note

This file defines the default shell behavior.

A prompt may still clarify:

* which shell reference image to use
* which product area the screen belongs to
* whether a specific shell variant should be prioritized for that run

Prompt clarification should refine shell selection, not override the shell preservation rules in this file.

## Extension rule

Initiative-specific files may extend this base file by adding:

* page-specific header behavior inside the content canvas
* page-specific section layouts
* page-specific interaction zones

They should not contradict the shell constraints in this file without an explicit product-level decision.
