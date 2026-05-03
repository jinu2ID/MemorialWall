---
name: Memorial Data Narrative
colors:
  surface: '#101416'
  surface-dim: '#101416'
  surface-bright: '#363a3c'
  surface-container-lowest: '#0b0f11'
  surface-container-low: '#181c1e'
  surface-container: '#1c2023'
  surface-container-high: '#262b2d'
  surface-container-highest: '#313538'
  on-surface: '#e0e3e6'
  on-surface-variant: '#dbc2b0'
  inverse-surface: '#e0e3e6'
  inverse-on-surface: '#2d3133'
  outline: '#a38c7c'
  outline-variant: '#554336'
  surface-tint: '#ffb77c'
  primary: '#ffb77c'
  on-primary: '#4d2700'
  primary-container: '#f28e2b'
  on-primary-container: '#5e3000'
  inverse-primary: '#904d00'
  secondary: '#aacaea'
  on-secondary: '#0f334d'
  secondary-container: '#2a4965'
  on-secondary-container: '#99b8d8'
  tertiary: '#acc8f3'
  on-tertiary: '#113154'
  tertiary-container: '#8ca8d1'
  on-tertiary-container: '#1f3d60'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#ffdcc2'
  primary-fixed-dim: '#ffb77c'
  on-primary-fixed: '#2e1500'
  on-primary-fixed-variant: '#6d3900'
  secondary-fixed: '#cde5ff'
  secondary-fixed-dim: '#aacaea'
  on-secondary-fixed: '#001d32'
  on-secondary-fixed-variant: '#2a4965'
  tertiary-fixed: '#d3e4ff'
  tertiary-fixed-dim: '#acc8f3'
  on-tertiary-fixed: '#001c38'
  on-tertiary-fixed-variant: '#2b486c'
  background: '#101416'
  on-background: '#e0e3e6'
  surface-variant: '#313538'
typography:
  headline-xl:
    fontFamily: Newsreader
    fontSize: 48px
    fontWeight: '300'
    lineHeight: '1.1'
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Newsreader
    fontSize: 32px
    fontWeight: '400'
    lineHeight: '1.2'
  headline-md:
    fontFamily: Newsreader
    fontSize: 24px
    fontWeight: '500'
    lineHeight: '1.3'
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: '1.6'
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.6'
  label-caps:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '600'
    lineHeight: '1'
    letterSpacing: 0.1em
  interactive:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '500'
    lineHeight: '1'
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  unit: 4px
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 48px
  xxl: 96px
  gutter: 24px
  margin: 40px
---

## Brand & Style

This design system is built upon the dual pillars of solemnity and data-driven truth. It is designed to facilitate reflection, utilizing a dark, archival aesthetic that mimics the tactile quality of physical memorial walls. The interface serves as a quiet vessel for heavy information, ensuring that the human cost of conflict is presented with dignity and clarity.

The visual style leans into a **Modern Minimalist** approach with a high emphasis on typography and negative space. It avoids decorative flourishes in favor of structural integrity, borrowing from the precision of data journalism to ground emotional subjects in factual accuracy. The atmosphere is quiet, intentional, and enduring.

## Colors

The palette is anchored in deep, obsidian blacks and charcoal grays to create a sense of infinite depth, reminiscent of granite memorial surfaces. 

*   **Primary Accent:** The muted gold (#F28E2B) is used sparingly as a "flicker of light"—it highlights names, active map sectors, and critical data points. 
*   **Secondary/Tertiary:** Muted blues (#6988A6) and deep navies (#04284A) provide subtle tonal shifts for structural elements like dividers and map borders, preventing the dark interface from feeling flat.
*   **Neutral:** The light gray (#E9ECEF) is reserved strictly for legibility in body text, ensuring a soft contrast that reduces eye strain in dark environments.

## Typography

The typographic hierarchy establishes a rhythm between the archival and the utilitarian. 

**Newsreader** is utilized for all headlines and editorial content. Its serif construction conveys historical weight and institutional authority. Large headlines should use lighter weights with tighter letter spacing to maintain a sophisticated, etched appearance.

**Inter** provides the functional backbone for interactive elements, data labels, and navigational components. Its neutral, high-legibility design ensures that complex data—such as unit types and casualty counts—is easily digestible without competing with the emotional resonance of the serif headers.

## Layout & Spacing

The design system employs a **Fixed Grid** model for editorial content and a **Fluid Overlay** model for interactive maps and data visualizations. 

*   **Rhythm:** A strict 4px baseline grid ensures alignment across dense data lists.
*   **Breathing Room:** Large margins (40px+) are used to frame information, creating a "gallery" effect that forces focus onto the content. 
*   **Composition:** Content is often grouped into vertical "steles" or columns, echoing the vertical panels of a memorial wall. Gutters are kept wide to prevent information density from feeling claustrophobic.

## Elevation & Depth

Hierarchy is achieved through **Tonal Layering** rather than traditional shadows. In this dark-themed system, depth is communicated by subtle shifts in background luminosity:

1.  **Floor (0dp):** Pure black (#080808) for the global background.
2.  **Raised Surfaces (1dp):** Dark charcoal (#1A1A1A) for side panels and card containers.
3.  **Active/Hover States (2dp):** Deep navy (#04284A) to denote interactive regions.
4.  **Illumination:** A subtle "outer glow" effect is applied to primary gold elements to simulate light reflecting off a dark surface. 

Shadows, if used, are extremely soft, large-radius blurs with 80% opacity to suggest that elements are floating slightly above the map interface.

## Shapes

The shape language is primarily **Sharp**, favoring 90-degree angles to maintain a sense of structural permanence and architectural rigidity. 

A "Soft" roundedness (0.25rem) is applied only to interactive controls—such as buttons, input fields, and tags—to distinguish them from the purely informational, sharp-edged containers. This subtle rounding provides a "touch-friendly" affordance in an otherwise austere environment.

## Components

### Buttons & Controls
Interactive elements use a "Ghost" style by default. Borders are thin (1px) and use the secondary blue-gray. Upon hover, the border transitions to the primary gold, and the text gains a subtle glow.

### Chips & Tags
Used for filtering data (e.g., Service Branch, Unit Type). These are rectangular with 2px corner radii. Active states utilize a solid gold background with black text to provide maximum contrast.

### Lists & Memorial Walls
Names and data entries are presented in a monochromatic list. On hover, an entry expands slightly, and the text shifts from neutral gray to pure white, accompanied by a gold leading-edge indicator.

### Input Fields
Inputs are bottom-border only, mimicking the lines of a ledger. This reduces visual noise and keeps the focus on the data entered.

### Cards & Tooltips
Tooltips for map locations (e.g., Kandahar) use a semi-transparent dark fill with a 1px gold border. They appear as "HUD" elements, floating over the geographic data without obscuring it entirely.