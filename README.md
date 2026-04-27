# Memorial Wall Development Log

This document tracks the evolution of the Afghanistan Veterans Memorial site

### 1. Responsive Grid Layout

- **Goal:** Add a responsive grid section to display memorial data.
- **AI Mistake:**
  1. Hallucinated a non-existent CSS property `grid-column-balance: true`.
  2. Hardcoded `grid-template-columns: repeat(4, 1fr)` which fails on mobile devices by cramming 4 columns into a small viewport.
- **Fix:**
  1. Removed the non-existent `grid-column-balance` property.
  2. Replaced the hardcoded column count with `repeat(auto-fit, minmax(200px, 1fr))`, allowing the grid to wrap naturally on smaller screens without needing explicit media queries for every breakpoint.

### 2. Hover States and Transitions

- **Goal:** Add interactive hover effects and smooth transitions to navigation and cards.
- **AI Mistake:**
  1. Attempted to transition the `display` property to create a "fade" effect (which is not possible with CSS transitions).
  2. Used a hallucinated CSS property `transition-smoothing: ultra;`.
- **Fix:**
  1. Replaced `display: none/block` with `opacity`, `visibility`, and `height` properties, which can be smoothly transitioned by the browser.
  2. Removed the hallucinated `transition-smoothing` property and optimized the `transition` property to target specific attributes rather than using `all`.

### 3. Dark Mode with CSS Variables

- **Goal:** Implement a theme toggle using CSS variables and media queries.
- **AI Mistake:**
  1. Defined CSS variables but continued to use hardcoded hex values in several key selectors (like `nav a` and `.banner`), rendering the variables useless for those elements.
  2. Hallucinated a CSS property `color-theme-strategy: root-relative;`.
  3. **Functional Omission:** Implemented `prefers-color-scheme` but forgot to provide a UI element (toggle button) for the user to manually switch themes.
  4. **Incomplete Variable Adoption:** Left section backgrounds like `#stats` and `.banner` with hardcoded dark hex values while switching text to dark mode (`#333`), resulting in "invisible" text in light mode.
  5. **Nested Element Contrast Failure:** Neglected to apply CSS variables to nested elements within cards (like `h3`, `p`, and `extra-info`). While the card background adapted, the nested text remained light gray/gold, leading to poor contrast against a light background.
- **Fix:**
  1. Replaced hardcoded hex values in `body`, `nav`, `nav a`, `.banner`, and `#stats` with their corresponding CSS variables.
  2. Removed the hallucinated `color-theme-strategy` property.
  3. Added a `transition` to the `body` to ensure theme switching is smooth.
  4. **Functional Fix:** Added a `<button>` to the `nav` and a small script to toggle a `[data-theme="dark"]` attribute.
  5. **Visibility & Contrast Fix:** Refactored all nested card elements to use the `--text-main` or `--accent-color` variables, and updated the hover state to use a variable-based background.

### 4. Custom Toggle Icon (Image-based)

- **Goal:** Use a thematic image (Night Vision Goggles) for the dark mode toggle.
- **AI Mistake:**
  1. **Pathing Error:** Used an absolute local path from the host machine directly in the `src` attribute.
  2. **Unstyled Asset:** Included a large image file without setting dimensions in CSS.
  3. **Layout Break:** Used `display: inline` on `nav li` while giving the child button `display: flex`.
  4. **Accessibility Omission:** Provided no `alt` text for the image-based button.
  5. **Stylistic Omission:** Left a default or manual border on the image-based button, which distracted from the custom NVG icon aesthetic.
- **Fix:**
  1. Copied the asset into the project's `images/` folder and used a relative path.
  2. Added CSS to constrain the image dimensions (`width: 32px`).
  3. **Layout Fix:** Refactored the navigation to use Flexbox (`display: flex`) on the `<ul>`.
  4. Added a descriptive `alt` attribute.
  5. **Aesthetic Fix:** Removed the `border` and `background` from the toggle button to allow the NVG icon to stand alone cleanly.
