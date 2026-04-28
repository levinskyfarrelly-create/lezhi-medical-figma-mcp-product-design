---
name: lezhi-medical-figma-mcp-product-design
description: Design and refine Lezhi high-end medical frontend product UI with Pencil MCP or Figma MCP using bundled design-md and layout-md references. Use when Codex needs to create product screens, backend/admin pages, dashboards, forms, tables, page flows, component states, or visual refinements based on user requirements and the Lezhi medical UI/layout specifications.
---

# Lezhi Medical Figma MCP Product Design

## Overview

Use this skill to convert user requirements into Lezhi high-end medical product designs with a fixed MCP-first workflow. The bundled `design-md` file is the UI specification source, and the bundled `layout-md` file is the layout/style optimization source.

## Required Workflow

Follow these steps in order.

### Step 1: Load Pencil MCP or Figma MCP

Choose the design MCP before designing:

- Use Pencil MCP for prototype-first work, backend/admin product structure, page-flow assembly, `.pen` documents, low/mid-fidelity layout design, and fast requirement-to-prototype tasks.
- Use Figma MCP for polished visual screens, design-system-aligned UI, componentized page design, variables/tokens, higher-fidelity review output, and Figma-native editing.
- If the user explicitly names Pencil or Figma, use that tool.
- If the user does not specify, prefer Pencil for product workflow prototypes and backend/admin page structures, and prefer Figma for visual refinement or high-fidelity screens.

### Step 2: Apply the Design MD UI Specification

Read the bundled design reference before making product UI decisions:

- `./references/design-md.md`

Use it as the source of truth for:

- brand positioning and product tone
- color, typography, spacing, radius, shadow, and token rules
- component style rules for buttons, forms, tables, cards, feedback, navigation, tags, loading, and overlays
- page shells, business modules, interaction states, accessibility, copywriting, and delivery constraints

Do not invent conflicting colors, components, or interaction behavior unless the user explicitly requests a deviation.

Treat the bundled UI specification as the default visual ceiling and floor:

- keep the Lezhi baseline visual language even when the business scenario changes
- do not reinterpret a new scene as a new brand
- do not switch to media-style, consumer-marketing-style, sci-fi cockpit, luxury-black, or entertainment-style UI unless the user explicitly asks to depart from the Lezhi baseline

### Step 3: Apply the Layout MD Style Optimization

Read the bundled layout reference when optimizing page composition, information hierarchy, visual rhythm, module layout, or style polish:

- `./references/layout-md.md`

Use it to improve:

- backend shell structure: top bar, sidebar, content area, breadcrumbs, and action zones
- workbench, list, detail, dashboard, and cockpit page templates
- card rhythm, section density, 70/30 or 7:3/8:4 split layouts, KPI grids, right-side task panels, and fixed operation bars
- visual translation from enterprise SaaS references into restrained high-end medical product language

Treat `layout-md.md` as an optimization layer, not a replacement for `design-md.md`. If the two references conflict, preserve the Lezhi medical UI specification from `design-md.md`.

### Step 4: Design From User Requirements

Translate the user's request into a Pencil or Figma product design.

Always do the following:

1. Identify the product context: page type, business flow, user role, desktop/mobile scope, and output tool.
2. Extract only the relevant rules from `design-md.md` and `layout-md.md`.
3. Map requirements into page shell, modules, components, states, data density, and interaction flow.
4. Build or modify the requested design with Pencil MCP or Figma MCP.
5. Verify that the result follows Lezhi's premium clinical tone and the layout optimization rules.

Translate new business scenarios into the existing Lezhi style system instead of creating a new visual language.

Examples:

- hotel screen, welcome screen, smart display, member service screen:
  still use Lezhi's calm, premium, restrained, low-saturation, card-based language
- dashboard, workbench, detail page, overview page:
  still inherit the same color hierarchy, spacing rhythm, border strength, and information density rules
- commerce or recommendation modules:
  may add emphasis, but cannot turn the whole page into an advertising visual system

### Step 5: Prevent Figma Section Overlap

When the chosen output is Figma, treat overlap prevention as a required part of the workflow, not as optional polish.

Always enforce these rules:

1. Create the page-level wrapper frame first, then append every major section into that wrapper. Do not create multiple top-level content blocks on the page and try to align them later.
2. Build one major section per `use_figma` call. Do not generate a whole multi-section screen in one large script.
3. Make every page wrapper and section wrapper an auto-layout frame. Prefer vertical auto layout for page shells and section stacks.
4. Do not rely on manual `x` / `y` positioning for normal content sections inside a page. Use auto-layout flow, padding, gap, hug, and fill instead.
5. Set child `FILL` sizing only after appending the child to the parent auto-layout frame.
6. Give every section an explicit internal structure before adding business content:
   - section outer frame
   - section header/title area
   - section body container
   - optional action/footer area
7. When placing cards, tables, charts, forms, or right-side panels, create an intermediate row/frame container first. Do not append unrelated content directly onto the page wrapper at mixed hierarchy levels.
8. When a section contains left-right columns, build a horizontal auto-layout row first, then append the two column frames, then set fill/hug rules. Do not fake columns with absolute coordinates.
9. Before adding detailed content, size the shell correctly:
   - desktop page wrapper: fixed width
   - section wrappers: fill horizontally, hug vertically
   - text/content containers: hug vertically unless a fixed region is explicitly required
10. After each section is created, inspect it before building the next one. If a section already clips text, collapses height, or overlaps internally, fix it immediately instead of continuing.

## Design Decision Rules

Use these defaults unless the user says otherwise:

- Tone: premium, clinical, calm, trustworthy, orderly, service-oriented.
- Base look: white cards, light borders, low-saturation hierarchy, restrained VIP accents, weak shadows.
- Main colors: navy for structure, blue for primary action/key data, teal for medical service emphasis, sand for membership/VIP accents.
- Layout: stable enterprise/admin structure first, decoration second.
- Components: keep table, filter, form, card, drawer, modal, toast, empty, loading, and bottom action bar states consistent.
- Accessibility: keep readable typography, visible focus states, clear field-level errors, and predictable keyboard behavior.

Lock these visual constraints unless the user explicitly overrides them:

- Background:
  prefer white, mist, or very light low-saturation surfaces as the primary background
  decorative gradients or atmospheric layers may exist only as subtle accents, not as the main visual identity
- Cards:
  default to white cards with light borders and restrained shadow
  avoid heavy glassmorphism, heavy blur panels, neon glow, or dark translucent luxury panels as the default system
- Color ratio:
  blue and teal are for emphasis, not for flooding the whole interface
  sand is a restrained accent, not a dominant surface color
- Typography:
  stable hierarchy over display-style headlines
  avoid oversized marketing typography, exaggerated slogans, or hero-banner-first composition
- Decoration:
  information first, ornament second
  avoid large atmospheric blobs, strong cinematic lighting, or entertainment-style motion cues dominating the page

If a request introduces a new scene type, preserve the Lezhi system by translating the scene into:

- structured modules
- white or light cards
- stable information blocks
- restrained highlights
- readable operational hierarchy

Do not let scene novelty justify a full style drift.

## Tool Execution Notes

When using Pencil MCP:

- Start by checking the active editor state and existing `.pen` document.
- Build structure first: shell, navigation, content zones, then modules.
- Use reusable components or existing frames when available.
- Verify the design with screenshot/layout inspection after creating or modifying screens.

When using Figma MCP:

- Load `figma-use` before every `use_figma` write action.
- Load `figma-generate-design` as the workflow reference when building or updating a full screen.
- Search existing design system assets before creating new components.
- Use variables/tokens where possible instead of hardcoded values.
- Prefer incremental section-by-section writes for full screens.
- Before styling a new screen type, restate the Lezhi baseline internally:
  - white/light card system
  - low-saturation layered background
  - restrained blue/teal/sand accents
  - order, trust, clarity over spectacle
- Create the page wrapper frame first and return its node ID before building any section.
- Build one major section per `use_figma` call and return created node IDs after every call.
- Use auto-layout frames for page shell, section shell, row, column, card group, and form group containers.
- Do not place normal content by absolute `x` / `y` coordinates once it is inside a wrapper frame.
- Run section-level screenshot validation after each major section, not only one final full-page screenshot.
- Specifically check for:
  - whether the page still looks like a Lezhi product instead of a new unrelated brand
  - whether the background has become too dark, too glossy, or too decorative
  - whether the card system has drifted away from white card + light border + weak shadow
  - whether accent colors are overpowering the interface
  - cards or sections visually stacked on top of each other
  - text clipping caused by wrong hug/fill rules
  - table, chart, or form areas collapsing to insufficient height
  - right-side sidebars overlapping the main content area
  - components appended to the wrong parent level

## Figma Validation Checklist

Before considering a Figma result complete, validate each of these:

- The page still matches the Lezhi UI tone from `design-md.md`, not a newly invented style direction.
- The page does not rely on dark luxury glass panels, oversized gradients, neon glow, or entertainment-style atmosphere as the dominant UI style.
- White/light cards, light borders, and low-saturation hierarchy are still the main visual system.
- Decorative background treatments stay secondary to content readability.
- The page has exactly one page-level wrapper frame for the designed screen.
- Every major content block is a child of that wrapper or of an intermediate section container.
- No peer sections depend on absolute coordinates for vertical stacking.
- Every major section has explicit padding and gap values.
- Every two-column area uses a dedicated horizontal container.
- No text frame is clipped because of fixed height where hug height should be used.
- No card, chart, table, or form panel overlaps another panel in the section screenshot.
- The full-page screenshot and section screenshots both look structurally correct.

## Common Failure Patterns

If generated Figma screens keep showing overlap, assume one or more of these mistakes happened:

- The skill created multiple top-level frames and positioned them manually instead of using one wrapper frame.
- A whole screen was generated in one script, so the hierarchy and sizing were not validated incrementally.
- The script used `x` / `y` positioning inside content wrappers instead of auto layout.
- `FILL` sizing was applied before `appendChild`, causing sizing/layout bugs.
- The section lacked an intermediate row or column container, so children were appended at the wrong hierarchy level.
- Validation happened only at the full-page level, which hides local overlaps and clipping.

If generated Figma screens keep drifting away from the intended Lezhi style, assume one or more of these mistakes happened:

- The model interpreted a new scene as permission to invent a new brand language.
- Decorative background ideas overrode the baseline white-card system.
- Accent colors were promoted into dominant surfaces.
- The design leaned toward marketing-screen composition instead of structured product composition.
- Scene-specific content was treated as visual direction, instead of being translated into the existing Lezhi style system.

## Reference Files

Load references only as needed:

- `./references/design-md.md`: Lezhi high-end medical UI design specification.
- `./references/layout-md.md`: backend layout/style optimization reference.
