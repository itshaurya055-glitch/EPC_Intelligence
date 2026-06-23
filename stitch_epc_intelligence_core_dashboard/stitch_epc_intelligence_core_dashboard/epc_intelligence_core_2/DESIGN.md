---
name: EPC Intelligence Core
colors:
  surface: '#f7f9fb'
  surface-dim: '#d8dadc'
  surface-bright: '#f7f9fb'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f2f4f6'
  surface-container: '#eceef0'
  surface-container-high: '#e6e8ea'
  surface-container-highest: '#e0e3e5'
  on-surface: '#191c1e'
  on-surface-variant: '#3c4a46'
  inverse-surface: '#2d3133'
  inverse-on-surface: '#eff1f3'
  outline: '#6b7a76'
  outline-variant: '#bacac5'
  surface-tint: '#006b5f'
  primary: '#006b5f'
  on-primary: '#ffffff'
  primary-container: '#2dd4bf'
  on-primary-container: '#00574d'
  inverse-primary: '#3cddc7'
  secondary: '#565e74'
  on-secondary: '#ffffff'
  secondary-container: '#dae2fd'
  on-secondary-container: '#5c647a'
  tertiary: '#505f76'
  on-tertiary: '#ffffff'
  tertiary-container: '#afbfd9'
  on-tertiary-container: '#3e4e63'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#62fae3'
  primary-fixed-dim: '#3cddc7'
  on-primary-fixed: '#00201c'
  on-primary-fixed-variant: '#005047'
  secondary-fixed: '#dae2fd'
  secondary-fixed-dim: '#bec6e0'
  on-secondary-fixed: '#131b2e'
  on-secondary-fixed-variant: '#3f465c'
  tertiary-fixed: '#d3e4fe'
  tertiary-fixed-dim: '#b7c8e1'
  on-tertiary-fixed: '#0b1c30'
  on-tertiary-fixed-variant: '#38485d'
  background: '#f7f9fb'
  on-background: '#191c1e'
  surface-variant: '#e0e3e5'
typography:
  headline-xl:
    fontFamily: Geist
    fontSize: 40px
    fontWeight: '700'
    lineHeight: 48px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Geist
    fontSize: 32px
    fontWeight: '600'
    lineHeight: 40px
    letterSpacing: -0.01em
  headline-lg-mobile:
    fontFamily: Geist
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Geist
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 28px
  body-lg:
    fontFamily: Geist
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-md:
    fontFamily: Geist
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  label-code:
    fontFamily: JetBrains Mono
    fontSize: 13px
    fontWeight: '500'
    lineHeight: 18px
  label-caps:
    fontFamily: Geist
    fontSize: 12px
    fontWeight: '700'
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
  unit: 4px
  container-max: 1440px
  gutter: 24px
  margin-desktop: 48px
  margin-mobile: 16px
  stack-sm: 8px
  stack-md: 16px
  stack-lg: 32px
---

## Brand & Style

The design system is engineered for technical clarity and high-performance developer workflows. It targets a professional audience in engineering and data science, where precision is paramount. The aesthetic merges **Modern Corporate** reliability with a **Minimalist** ethos, utilizing expansive white space to reduce cognitive load during complex tasks.

The emotional response is one of controlled power—the UI feels like a high-end laboratory instrument: clean, sterile, and hyper-functional. By moving to a light-mode foundation, the system emphasizes transparency and logical organization, using sharp edges and purposeful teal accents to guide the user's attention through dense data structures.

## Colors

The palette is centered on a "Pure White" (#ffffff) foundation to maximize contrast and clarity. The primary accent is a vibrant **Teal**, used sparingly for high-intent actions and status indicators. 

- **Primary:** Teal (#2dd4bf) functions as the brand signal and interactive marker.
- **Surface:** Light Gray (#f8fafc) is used to define container boundaries and differentiate between navigation and content areas.
- **Typography:** High-contrast Slate (#0f172a) ensures readability across all data densities, while Muted Slate (#475569) provides secondary hierarchy for metadata and labels.
- **Accents:** A deep Slate is utilized for structural elements like heavy borders or header text to ground the airy layout.

## Typography

This design system utilizes a dual-font strategy to balance modern aesthetics with technical utility. **Geist** serves as the primary typeface, offering a clean, geometric sans-serif look that feels precise and developer-friendly. For technical data, code snippets, and system status labels, **JetBrains Mono** provides the necessary monospaced clarity.

All headings use tight letter spacing and bold weights to establish a firm hierarchy. Body text is optimized for long-form reading with generous line heights. Small labels and metadata often utilize uppercase styling with increased tracking to maintain legibility at reduced sizes.

## Layout & Spacing

The system employs a **Fluid Grid** model with a maximum content width of 1440px. The spacing rhythm is strictly based on a **4px baseline**, ensuring mathematical harmony between all elements. 

- **Desktop:** 12-column grid with 24px gutters and 48px outer margins.
- **Tablet:** 8-column grid with 16px gutters and 24px outer margins.
- **Mobile:** 4-column grid with 12px gutters and 16px outer margins.

Vertical rhythm is maintained through standardized "Stack" variables, forcing consistent gaps between sections, paragraphs, and components to preserve the minimalist, airy feel.

## Elevation & Depth

To maintain a clean, professional appearance, the design system avoids heavy shadows in favor of **Tonal Layers** and **Low-Contrast Outlines**.

1.  **Level 0 (Base):** Pure White (#ffffff) for the main viewport background.
2.  **Level 1 (Sub-surface):** Light Gray (#f8fafc) for sidebars, headers, and footer areas.
3.  **Level 2 (Float):** Pure White surfaces with a 1px border (#e2e8f0). 
4.  **Interactive:** Elements like active cards or dropdowns use a very soft, diffused ambient shadow (0px 4px 20px rgba(15, 23, 42, 0.05)) to suggest lift without cluttering the interface.

Depth is primarily communicated through subtle shifts in gray value rather than dramatic light effects.

## Shapes

The design system adopts a **Soft** shape language. This subtle rounding (0.25rem / 4px) softens the technical edge of the monospaced typography and geometric grid, making the professional environment feel more approachable while remaining firmly within the "Modern Tooling" aesthetic. Larger components like cards and modal dialogs scale up to 0.75rem (12px) to provide a distinct container identity.

## Components

### Buttons
- **Primary:** Solid Teal (#2dd4bf) with White text. No gradients.
- **Secondary:** Transparent with a 1px Slate (#e2e8f0) border and Slate text.
- **Ghost:** No background or border; Teal text for actions, Slate for navigation.

### Input Fields
- **Default State:** White background, 1px Gray (#e2e8f0) border, Geist Body-md text.
- **Focus State:** 1px Teal (#2dd4bf) border with a 2px soft teal outer glow.

### Cards & Containers
- Cards utilize a white background, a 1px border (#e2e8f0), and a 4px corner radius. In data-heavy views, cards are replaced by "Rows" separated by 1px horizontal lines.

### Chips & Badges
- Used for status and tags. Badges feature a desaturated background (e.g., Teal at 10% opacity) with high-contrast text in the same hue.

### Lists
- Interactive list items use a subtle Gray (#f1f5f9) background on hover. Vertical alignment is strictly enforced via the 4px spacing unit.

### Navigation
- Sidebar navigation utilizes JetBrains Mono for a "terminal-lite" feel. Active states are indicated by a 2px vertical Teal line on the leading edge of the menu item.