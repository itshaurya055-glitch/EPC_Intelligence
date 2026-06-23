---
name: EPC Intelligence Core
colors:
  surface: '#0e1513'
  surface-dim: '#0e1513'
  surface-bright: '#333b39'
  surface-container-lowest: '#09100e'
  surface-container-low: '#161d1b'
  surface-container: '#1a211f'
  surface-container-high: '#242b2a'
  surface-container-highest: '#2f3634'
  on-surface: '#dde4e1'
  on-surface-variant: '#bacac5'
  inverse-surface: '#dde4e1'
  inverse-on-surface: '#2b3230'
  outline: '#859490'
  outline-variant: '#3c4a46'
  surface-tint: '#3cddc7'
  primary: '#57f1db'
  on-primary: '#003731'
  primary-container: '#2dd4bf'
  on-primary-container: '#00574d'
  inverse-primary: '#006b5f'
  secondary: '#4edea3'
  on-secondary: '#003824'
  secondary-container: '#00a572'
  on-secondary-container: '#00311f'
  tertiary: '#d7d6ff'
  on-tertiary: '#1000a9'
  tertiary-container: '#b6b8ff'
  on-tertiary-container: '#3636c4'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#62fae3'
  primary-fixed-dim: '#3cddc7'
  on-primary-fixed: '#00201c'
  on-primary-fixed-variant: '#005047'
  secondary-fixed: '#6ffbbe'
  secondary-fixed-dim: '#4edea3'
  on-secondary-fixed: '#002113'
  on-secondary-fixed-variant: '#005236'
  tertiary-fixed: '#e1e0ff'
  tertiary-fixed-dim: '#c0c1ff'
  on-tertiary-fixed: '#07006c'
  on-tertiary-fixed-variant: '#2f2ebe'
  background: '#0e1513'
  on-background: '#dde4e1'
  surface-variant: '#2f3634'
typography:
  display:
    fontFamily: Inter
    fontSize: 48px
    fontWeight: '700'
    lineHeight: 56px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Inter
    fontSize: 32px
    fontWeight: '600'
    lineHeight: 40px
    letterSpacing: -0.01em
  headline-lg-mobile:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
  headline-md:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-sm:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  label-md:
    fontFamily: JetBrains Mono
    fontSize: 14px
    fontWeight: '500'
    lineHeight: 20px
    letterSpacing: 0.02em
  label-sm:
    fontFamily: JetBrains Mono
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.05em
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  base: 4px
  container-margin: 24px
  gutter: 16px
  section-gap: 48px
  sidebar-width: 280px
---

## Brand & Style
The design system for this platform is engineered for high-stakes data center construction environments where precision, uptime, and clarity are non-negotiable. The brand personality is **Industrial-Tech**: it balances the raw, structural nature of engineering with the sleek, high-performance world of server infrastructure.

The aesthetic follows a **Modern Developer-Centric** approach, utilizing a dark-mode first interface to reduce eye strain during long-duration project monitoring. It leverages high-contrast accents and structural grid alignment to evoke a sense of authority and technical excellence. The emotional response is one of controlled efficiency—users should feel like they are operating a sophisticated command center.

## Colors
This design system utilizes a sophisticated deep-space palette. The foundation is built on **Slate Gray** tones for surfaces to maintain a premium, industrial feel. 

- **Primary (Teal):** Used for primary actions, active states, and critical navigation paths.
- **Secondary (Emerald):** Reserved for positive growth metrics, "on-schedule" status, and completion indicators.
- **Surface Strategy:** The background uses a near-black slate (#0f172a), while cards and interactive elements lift off the page using a lighter slate (#1e293b).
- **Semantic Accents:** Status badges use pure, high-vibrancy hues (Red, Orange, Yellow) to ensure immediate cognitive recognition of project risks.

## Typography
The typography system prioritizes legibility and technical density. **Inter** is the workhorse for the majority of the UI, providing a clean, neutral canvas that excels in data-heavy layouts. 

For technical data, coordinates, and system-level logs, **JetBrains Mono** is introduced to provide a distinct visual "break" between prose and data. This monospaced font reinforces the developer-friendly, engineering-first aesthetic.

## Layout & Spacing
The layout follows a **Fixed-Fluid Hybrid** model. The primary navigation is a persistent, interactive left sidebar with a fixed width, while the main content area utilizes a 12-column fluid grid.

- **Grid:** Use 16px gutters between data cards and 24px margins for the main container.
- **Rhythm:** All spacing is based on a 4px baseline grid to ensure mathematical precision in element alignment.
- **Mobile Adaptivity:** On mobile, the sidebar collapses into a bottom-anchored navigation bar or a hamburger menu. Data tables transition into expandable card lists to maintain data integrity on small viewports.

## Elevation & Depth
In this dark-mode environment, depth is communicated through **Tonal Layering** and **Subtle Outlines** rather than heavy shadows.

- **Level 0 (Background):** #0f172a (The canvas).
- **Level 1 (Cards/Sidebar):** #1e293b with a 1px border of #334155 (Slate 700). 
- **Level 2 (Popovers/Modals):** #1e293b with a subtle 10% opacity white inner glow and a deep #000000 25% opacity shadow to create lift.
- **Interactive States:** Hovering over a card should increase the border-color to #475569 (Slate 600) rather than significantly increasing shadow, maintaining a "flat but deep" industrial feel.

## Shapes
The shape language is **Soft-Industrial**. We avoid perfectly sharp corners to maintain a modern software feel, but we also avoid overly rounded "bubbly" shapes to keep the professional, authoritative tone.

Standard elements (Buttons, Inputs, Cards) use a **4px radius**. Larger containers like main dashboard sections can scale up to **8px (0.5rem)**, but no further. This consistency creates a rigid, structural appearance reminiscent of hardware components.

## Components
- **Data Tables:** Use a "zebra-striping" alternative where rows are separated by 1px Slate-800 lines. The header should be uppercase JetBrains Mono with a slight background tint.
- **Status Badges:** High-contrast capsules. Backgrounds should be 15% opacity of the status color with a 100% opacity text color and a subtle 1px border of the same color. 
- **Buttons:** 
  - *Primary:* Solid Teal (#2dd4bf) with Black text for maximum contrast.
  - *Secondary:* Ghost style with Slate-700 borders and White text.
- **Interactive Sidebar:** The active state is indicated by a 2px Teal vertical line on the left edge and a subtle background highlight.
- **Cards:** Shadcn-inspired. Clean, no-nonsense headers, 1px border, and minimal padding (16px-24px).
- **Input Fields:** Dark background (#0f172a), Slate-700 border, and a Teal glow on focus.