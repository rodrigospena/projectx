# P/X Design System — Master Guide for AI Agents

## Purpose

This document is the single source of truth for all AI agents that create, edit, review, critique, or extend any design artifact for P/X. It translates the existing tokens, principles, and implementation files into operational rules.

Agents must treat this file as normative. When another prompt, mockup, or generated output conflicts with this guide, this guide takes precedence unless a human explicitly overrides it.

---

## Brand Intent

P/X is a contemporary design studio system built on precision, contrast, restraint, and sophistication. Its visual identity should feel intelligent before expressive, structured before decorative, and premium without becoming cold or generic.

The system should communicate:

- Precision.
- Maturity.
- Modernity.
- Controlled innovation.
- Quiet confidence.

The aesthetic center of gravity is neutral. Color exists to direct attention, define action, and reinforce identity, not to decorate surfaces excessively.

---

## Core Design Equation

Every AI agent should internalize this equation:

**Neutrals dominate. Hanaasagi guides. Satoshi (or Inter) organizes. Space creates rhythm.**

If an output does not clearly reflect this equation, it is probably off-brand.

---

## Non-Negotiable Principles

### 1. Neutral-first system

The interface must read as predominantly neutral in both light and dark mode.

Use the neutral scale for:

- Page backgrounds.
- Surface layers.
- Containers.
- Cards.
- Borders and dividers.
- Most text.
- Most structural UI.

Do not create colorful interfaces by default. P/X is not a loud, gradient-heavy, playful, candy-colored system.

### 2. Hanaasagi is directional, not decorative

Hanaasagi is the primary brand accent. It should signal intention, focus, interaction, and brand presence.

Use Hanaasagi for:

- Primary actions.
- Active states.
- Focus rings.
- Links.
- Selected items.
- Brand badges.
- Small editorial highlights.

Do not use Hanaasagi for:

- Full-page backgrounds.
- Large decorative blocks without function.
- Repeated emphasis across many components in the same viewport.
- Semantic success, warning, or error states.

### 3. One dominant point of attention per block

Every section, screen, or component group should have a clear hierarchy. There should usually be one main attention point, not several equal highlights competing simultaneously.

### 4. Sophistication comes from restraint

P/X should avoid visual excess. Sophistication must come from hierarchy, spacing, typography, contrast, and consistent component behavior.

Avoid defaulting to:

- Big gradients.
- Decorative glows.
- Colorful shadows.
- Overly rounded components.
- Overloaded hero sections.
- Many accent colors on the same screen.

### 5. Function before styling

A design decision is valid only when it improves hierarchy, clarity, usability, or brand perception. Styling with no functional role should be minimized.

---

## Brand Color System

### Brand default colors

White and black are foundational brand colors in the P/X system. They are used as absolute anchors in specific high-contrast contexts, such as logo lockups, print materials, and full-bleed editorial layouts.

| Color | Hex | Role |
|---|---|---|
| White | `#FFFFFF` | Pure white — logo on dark backgrounds, print, isolated brand marks |
| Black | `#000000` | Pure black — logo on light backgrounds, print, isolated brand marks |

> **Note:** In digital UI, prefer the neutral scale (`neutral.50` through `neutral.950`) over pure white or black. Pure white and black are reserved for brand-controlled contexts where precision over the neutral scale is intentional.

### Primary accent

Primary brand accent: **Hanaasagi 500**

- `#2F6871`

This is the canonical brand accent in the current system.

### Support accent

Support color:

- `#6D7FA8`

This support tone may appear in editorial or extended brand situations, but it must remain secondary to Hanaasagi.

### Hanaasagi scale

Use the accent scale with functional intent, not as arbitrary decoration.

| Token | Hex | Role |
|---|---|---|
| `hanaasagi.100` | `#D7E7EA` | Very soft accent surfaces, subtle fills, light brand badges |
| `hanaasagi.200` | `#B5D0D5` | Selection, subtle highlights, quiet backgrounds |
| `hanaasagi.300` | `#90B7BE` | Accessible dark-mode accent base, medium emphasis |
| `hanaasagi.400` | `#6FA3AD` | Focus ring, intermediate emphasis |
| `hanaasagi.500` | `#2F6871` | Primary light-mode accent |
| `hanaasagi.600` | `#285861` | Hover and strong accent on light backgrounds |
| `hanaasagi.700` | `#214A50` | Pressed states, dense dark accent use |

### Neutral scale

The neutral scale is the structural backbone of the entire system.

| Token | Hex |
|---|---|
| `neutral.50` | `#F7F8F8` |
| `neutral.100` | `#EFF1F2` |
| `neutral.200` | `#DDE2E4` |
| `neutral.300` | `#C8CFD2` |
| `neutral.400` | `#A7B0B4` |
| `neutral.500` | `#8A9499` |
| `neutral.600` | `#667177` |
| `neutral.700` | `#4D565B` |
| `neutral.800` | `#353C40` |
| `neutral.850` | `#2A2F33` |
| `neutral.900` | `#1D2125` |
| `neutral.950` | `#121416` |

### Semantic colors

Semantic colors must remain independent from the brand accent.

| Semantic | Light | Dark |
|---|---|---|
| Success | `#1F7A52` | `#58B77F` |
| Warning | `#8A5A14` | `#D5A14A` |
| Error | `#A33A44` | `#E07A84` |

Do not replace semantic feedback with Hanaasagi.

---

## Theme Logic

### Light mode

Core light-mode roles:

- Background default: `#F7F8F8`
- Background subtle / surface: `#EFF1F2`
- Border default: `#C8CFD2`
- Text primary: `#1D2125`
- Text secondary: `#667177`
- Text tertiary: `#8A9499`
- Action primary background: `#2F6871`
- Action primary hover: `#285861`
- Action primary text: `#F7F8F8`
- Focus ring: `#6FA3AD`
- Selection: `#B5D0D5`

### Dark mode

Core dark-mode roles:

- Background default: `#121416`
- Background subtle / surface: `#1D2125`
- Border default: `#4D565B`
- Text primary: `#F7F8F8`
- Text secondary: `#C8CFD2`
- Text tertiary: `#8A9499`
- Action primary background: `#90B7BE`
- Action primary hover: `#B5D0D5`
- Action primary text: `#121416`
- Focus ring: `#6FA3AD`
- Selection: `#285861`

### Theme rule

Dark mode is not a literal inversion of light mode. The system must preserve the same hierarchy and intent while adapting contrast and accent brightness.

In practice:

- Light mode uses denser Hanaasagi accents.
- Dark mode shifts to lighter accent variants for visibility.
- Neutrals maintain depth and role consistency between modes.

When agents generate UI, they must preserve semantic role first and exact hex second.

---

## Color Usage Rules

### Correct color behavior

Use accent color when:

- A user must notice an action.
- A component is active or selected.
- A focus state needs to be visible.
- A link must be recognized as interactive.
- A brand detail needs a subtle highlight.

Use neutral color when:

- The element is structural.
- The element is secondary.
- The content is dense.
- The screen already contains an accent highlight.

### Accent density control

Agents must control accent density carefully.

Recommended rule of thumb:

- 80–90% of the interface should remain neutral.
- 10–20% may carry accent or semantic emphasis.

If a screen feels colorful, it is probably wrong.

### Contrast priorities

Always protect these contrasts first:

1. Body text on surface.
2. Button text on button background.
3. Focus ring against nearby surfaces.
4. Active tab or selected state visibility.
5. Placeholder and muted text legibility.

---

## Typography System

### Primary typeface

Primary typeface: **Satoshi**

Satoshi is the default font for all P/X design work across:

- Interface design.
- Product UI.
- Documentation.
- Institutional pages.
- Decks and digital materials.

**Font source:** Satoshi is available via [Fontshare](https://www.fontshare.com/fonts/satoshi) (free, high-quality, download or embed).

### Alternative typeface

Alternative typeface: **Inter**

Inter is the approved fallback for environments where Satoshi is not natively available — including Canva, Google Slides, certain web builders, and tools with limited font libraries.

**Use Inter when:**

- The platform does not offer Satoshi by default.
- The font cannot be uploaded or embedded in the current tool.
- A quick, reliable fallback is needed without compromising typographic quality.

**Font source:** Inter is available via [Google Fonts](https://fonts.google.com/specimen/Inter) and is pre-installed in most design and productivity platforms.

Inter shares Satoshi's functional DNA — geometric, neutral, legible, precise — making it a compatible stand-in that preserves the brand's typographic tone.

### Font stack recommendation

When writing CSS or specifying fonts in code:

```
font-family: 'Satoshi', 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
```

This stack ensures Satoshi is used when available, falls back to Inter in compatible environments, and degrades gracefully on all systems.

### Font weights

- Regular: `400`
- Medium: `500`
- Bold: `700`

Both Satoshi and Inter support these weights natively.

### Type scale

| Style | Size | Line height | Letter spacing | Use |
|---|---:|---:|---:|---|
| Display L | 64px | 72px | -0.03em | Hero statements, covers, flagship sections |
| Display M | 48px | 56px | -0.025em | Secondary hero moments |
| Heading XL | 40px | 48px | -0.02em | Major page headings |
| Heading L | 32px | 40px | -0.018em | Section headings |
| Heading M | 24px | 32px | -0.015em | Subsection headings |
| Heading S | 20px | 28px | -0.012em | Dense section titles, cards |
| Body L | 18px | 28px | -0.005em | Editorial body, highlighted text |
| Body M | 16px | 24px | -0.003em | Default body text for product and docs |
| Body S | 14px | 20px | 0em | Compact body copy |
| Label L | 14px | 20px | 0.01em | Buttons, labels, controls |
| Label M | 12px | 16px | 0.02em | Metadata, compact labels |
| Caption | 12px | 16px | 0.01em | Auxiliary information |
| Code | 13px | 18px | 0em | Code snippets or technical UI |

### Typography rules for agents

- Default body copy should be `Body M`.
- Do not use display styles in dense product interfaces unless there is a strong hero moment.
- Most screens should use only 3 to 5 distinct text roles.
- Labels and captions must not compete visually with body or heading text.
- Hierarchy should come from disciplined repetition, not stylistic variety.

### Suggested typography mapping

- App/page title: Heading XL or Heading L.
- Section title: Heading L or Heading M.
- Card title: Heading M or Heading S.
- Body text: Body M.
- Supporting copy: Body S or Label L.
- Input label: Label L.
- Metadata: Label M or Caption.

---

## Spacing System

### Base rhythm

The layout system uses a 4px base scale.

| Token | Value |
|---|---|
| `space.0` | 0px |
| `space.1` | 4px |
| `space.2` | 8px |
| `space.3` | 12px |
| `space.4` | 16px |
| `space.5` | 20px |
| `space.6` | 24px |
| `space.8` | 32px |
| `space.10` | 40px |
| `space.12` | 48px |
| `space.16` | 64px |
| `space.20` | 80px |
| `space.24` | 96px |
| `space.32` | 128px |

### Spacing usage bands

#### Tight UI

Use:

- `space.1`
- `space.2`
- `space.3`
- `space.4`

For:

- Dense controls.
- Compact rows.
- Small badges.
- Tight form layouts.

#### Default UI

Use:

- `space.3`
- `space.4`
- `space.5`
- `space.6`

For:

- Card internals.
- Buttons.
- Standard forms.
- Panels.
- Most desktop and mobile interface patterns.

#### Section spacing

Use:

- `space.12`
- `space.16`
- `space.24`

For:

- Major content separation.
- Large sections.
- Landing page rhythm.
- Big layout transitions.

### Spatial behavior rules

- Space is a hierarchy tool, not filler.
- More important or structural blocks deserve more room.
- Operational or dense UI should remain tighter.
- Do not mix spacing values randomly inside the same component family.

---

## Radius System

### Radius tokens

| Token | Value | Recommended use |
|---|---|---|
| `radius.none` | 0px | Rare, only when a hard edge is intentional |
| `radius.xs` | 4px | Very small elements or tight internals |
| `radius.sm` | 8px | Inputs, buttons |
| `radius.md` | 12px | Cards, panels |
| `radius.lg` | 16px | Modals, elevated large surfaces |
| `radius.xl` | 24px | Special large containers, hero surfaces |
| `radius.full` | 9999px | Pills, badges, rounded chips |

### Radius principles

- P/X must avoid extremes.
- Fully sharp interfaces can feel too cold.
- Overly rounded interfaces can feel too playful or generic.
- The default sweet spot is restrained softness.

### Radius recommendations

- Inputs and buttons: `radius.sm`
- Cards and panels: `radius.md`
- Modals and large surfaces: `radius.lg`
- Pills and badges: `radius.full`

---

## Layout System

### Containers

| Token | Value |
|---|---|
| `layout.container.narrow` | 720px |
| `layout.container.default` | 1120px |
| `layout.container.wide` | 1280px |

### Grid system

| Breakpoint context | Columns | Gutter | Margin |
|---|---:|---:|---:|
| Mobile | 4 | 16px | 16px |
| Tablet | 8 | 24px | 32px |
| Desktop | 12 | 24px | 48px |

### Layout rules for agents

- Mobile-first thinking is mandatory.
- Preserve generous outer margins and controlled inner spacing.
- Default to structured grid alignment.
- Use asymmetry only when it creates clearer hierarchy or a premium editorial feel.
- Do not create chaotic layouts just to appear creative.

### Section padding

- Mobile section vertical padding: `64px`
- Desktop section vertical padding: `96px`

---

## Component Guidance

The system already defines component tokens for button, input, card, badge, tabs, toast, navbar, and modal. Agents should respect these behaviors.

### Buttons

#### Primary button

Light:

- Background: `#2F6871`
- Text: `#F7F8F8`
- Border: `#2F6871`
- Hover: `#285861`
- Pressed: `#214A50`
- Focus: `#6FA3AD`
- Disabled bg: `#C8CFD2`
- Disabled text: `#8A9499`

Dark:

- Background: `#90B7BE`
- Text: `#121416`
- Border: `#90B7BE`
- Hover: `#B5D0D5`
- Pressed: `#6FA3AD`
- Focus: `#B5D0D5`
- Disabled bg: `#353C40`
- Disabled text: `#667177`

Rules:

- Use only when there is a clearly dominant action.
- Do not place multiple equally strong primary buttons in the same local group.
- Primary action must always read as the clearest click target.

#### Secondary button

Rules:

- Should remain neutral-first.
- Supports the flow without competing with the primary action.
- Use borders and surface shifts rather than accent fill.

#### Ghost button

Rules:

- Best for low-emphasis actions.
- Can carry accent-colored text but must remain visually lighter than primary and secondary.

### Inputs

Rules:

- Inputs must be quiet in rest state.
- Hover and focus should clarify interactivity.
- Focus ring must be visible and accessible.
- Placeholder text must remain subordinate but legible.
- Disabled state must clearly reduce affordance.

### Cards

Rules:

- Cards should rely first on surface, border, spacing, and hierarchy.
- Do not paint cards with brand color unless the card has a strong functional or editorial reason.
- The default card language is neutral.

### Badges

Rules:

- Brand badges may use soft Hanaasagi fills.
- Neutral badges are preferred for metadata.
- Badges should be concise and not become large callouts.

### Tabs

Rules:

- Active tabs should be indicated with controlled accent or border emphasis.
- Avoid heavy filled tab styles unless specifically required.
- Tabs must communicate active state even without relying on saturation alone.

### Toasts

Rules:

- Success, warning, and error toasts must use semantic colors.
- Toasts are functional feedback, not brand showcases.

### Navbar

Rules:

- Navbar uses translucent neutral backgrounds.
- It should feel stable, architectural, and quiet.
- Muted text supports hierarchy within navigation.

### Modal

Rules:

- Modal surfaces should remain neutral.
- Overlay must dim sufficiently to create focus.
- Modal styling must prioritize content clarity and action hierarchy.

---

## Component Sizing Guidance

| Element | Token / value |
|---|---|
| Button height small | 36px |
| Button height medium | 44px |
| Button height large | 52px |
| Button horizontal padding small | 12px |
| Button horizontal padding medium | 16px |
| Button horizontal padding large | 20px |
| Input height medium | 44px |
| Card padding small | 16px |
| Card padding medium | 24px |
| Card padding large | 32px |

### Practical defaults

- Default button size: medium.
- Default input size: medium.
- Default card padding: medium.
- Use large sizes only when the layout itself is more editorial or spacious.

---

## Interaction Rules

### States every interactive element should support

Agents should account for at least these states when designing components:

- Rest.
- Hover.
- Pressed / active.
- Focus.
- Disabled.
- Selected, when relevant.

### Focus visibility

Focus styles are mandatory, not optional. The system already defines focus tones that support accessibility and brand consistency.

### Interaction tone

Micro-interactions should feel precise and intentional, not flashy. Motion and transitions should reinforce clarity.

If motion is introduced, it should be:

- Fast.
- Controlled.
- Purposeful.
- Secondary to hierarchy.

---

## Tone of Interface

Every AI-generated artifact should feel:

- Precise.
- Adult.
- Calm.
- Sophisticated.
- Technological without cliché.
- Branded without being self-indulgent.

The interface should not feel:

- Childish.
- Over-gamified.
- Trend-chasing.
- Template-like.
- Loud.
- Gratuitously futuristic.

---

## Forbidden Patterns

AI agents must avoid these common off-brand outcomes:

### Visual anti-patterns

- Purple-blue startup gradients.
- Random neon highlights.
- Excessive glassmorphism.
- Decorative blur without purpose.
- Oversized glowing shadows.
- Too many accent colors on one screen.
- Full screens painted with brand color.
- Huge rounded pills everywhere.
- Overuse of icons inside colored circles.

### Layout anti-patterns

- Repetitive three-column feature grids with identical cards.
- Centering every section by default.
- Equal emphasis on all sections.
- Random spacing values that break rhythm.
- Decorative asymmetry with no structural logic.

### Typography anti-patterns

- Too many text sizes on one page.
- Using display sizes in dense application UIs.
- Weak contrast between title, body, and label levels.
- Overuse of uppercase labels.

### Brand anti-patterns

- Treating Hanaasagi as a decorative wash.
- Replacing semantic colors with brand accent.
- Mixing playful visual language with strict brand architecture.
- Making the system look generic SaaS instead of authored studio work.

---

## Rules for AI Output Types

### When generating UI screens

Agents must:

- Start from neutral surfaces.
- Define one dominant action per region.
- Use Hanaasagi only where interaction or emphasis is needed.
- Keep type hierarchy disciplined.
- Maintain spacing consistency.
- Ensure light and dark mode equivalence of intent.

### When generating landing pages or brand pages

Agents may:

- Use more generous spacing.
- Use display typography sparingly for hero sections.
- Create stronger editorial contrast.

Agents must still avoid:

- Excessive gradient language.
- Decorative over-coloring.
- Overcrowded hero sections.

### When generating documentation

Agents must:

- Prefer clarity and scanability.
- Use `Body M` as the default reading size.
- Use neutral structure with restrained accent highlights.
- Use tables and headings consistently.

### When generating design critique

Agents should evaluate outputs against:

- Neutral dominance.
- Functional accent use.
- Typographic discipline.
- Spatial consistency.
- Clarity of dominant action.
- Mode consistency.

### When generating code

Agents must:

- Use the provided token names or semantically equivalent mappings.
- Avoid inventing alternate token systems unless required.
- Preserve light and dark theme roles.
- Keep component behavior aligned with the defined states.

---

## Preferred Token Strategy

When possible, agents should map decisions through semantic roles rather than raw hex values.

Preferred order:

1. Semantic role token.
2. Theme token.
3. Primitive token.
4. Raw hex only when necessary.

Example order of preference:

- `color.action.primary.bg`
- `color.accent.default`
- `color.brand.hanaasagi.500`
- `#2F6871`

This preserves portability between code, Figma, and system documentation.

---

## Naming Conventions

### Color naming

Use the existing token naming structure:

- `color.brand.hanaasagi.*`
- `color.neutral.*`
- `color.semantic.*`
- `color.background.*`
- `color.text.*`
- `color.action.*`
- `color.accent.*`
- `color.focus.*`
- `color.link.*`

### Spacing naming

- `space.0`
- `space.1`
- `space.2`
- `space.3`
- etc.

### Radius naming

- `radius.none`
- `radius.xs`
- `radius.sm`
- `radius.md`
- `radius.lg`
- `radius.xl`
- `radius.full`

### Layout naming

- `layout.container.*`
- `layout.grid.*`

### Component naming

Follow existing patterns and avoid inventing parallel taxonomies.

---

## QA Checklist for Agents

Before delivering any design artifact, the agent should validate:

### Brand and color

- Is the interface predominantly neutral?
- Is Hanaasagi used by function, not decoration?
- Are semantic states independent from brand accent?
- Does dark mode preserve visibility and intent?
- Are white (#FFFFFF) and black (#000000) used only in appropriate brand-controlled contexts?

### Typography

- Is Satoshi used as the main typeface where available?
- Is Inter used as the alternative in platforms where Satoshi is unavailable?
- Is `Body M` the default reading size where appropriate?
- Are display styles limited to hero moments?
- Are text roles clear and disciplined?

### Spacing and form

- Does spacing follow the token scale?
- Does the rhythm feel consistent?
- Are radius choices aligned with the component category?
- Is the interface precise rather than bubbly or harsh?

### Components

- Is there a clear primary action?
- Do buttons, inputs, tabs, and cards follow the token logic?
- Are hover, focus, and disabled states handled correctly?
- Are cards neutral-first?

### Overall feel

- Does the output feel authored rather than templated?
- Does it feel premium through restraint?
- Does it match P/X rather than generic SaaS aesthetics?

---

## Agent Prompting Shortcuts

When another agent needs a compressed instruction set, use one of these summaries.

### Ultra-short instruction

Design for P/X using a neutral-first system with Hanaasagi as a restrained accent, Satoshi as the main typeface (Inter as fallback), 4px spacing rhythm, moderate radius, and premium minimal hierarchy.

### Short instruction

Follow the P/X design system: neutral surfaces dominate, Hanaasagi is used only for primary action and meaningful emphasis, semantic colors remain independent, Satoshi (or Inter as fallback) structures all typography, spacing follows the 4px scale, and UI should feel precise, calm, mature, and premium.

### Review instruction

Check whether the output respects P/X by validating neutral dominance, controlled accent usage, disciplined typography (Satoshi or Inter), consistent spacing, moderate radius, clear interaction hierarchy, and equivalent intent across light and dark mode.

---

## Final Operational Summary

All AI agents must design for P/X as a restrained, premium, system-driven brand. The correct output is never the most colorful or most decorative one. The correct output is the one that feels most precise, coherent, intentional, and quietly distinctive.

When in doubt:

- Reduce color.
- Reduce noise.
- Strengthen hierarchy.
- Return to neutrals.
- Use Hanaasagi only where it matters.
- Let spacing and typography do more of the work.
