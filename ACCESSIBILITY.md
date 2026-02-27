# Accessibility Checklist

Follow this checklist while converting the PDF content and testing the generated HTML site.

- Document structure
  - Ensure a single `h1` per page that describes the page's purpose.
  - Use landmarks: `header`, `nav`, `main`, `aside`, `footer`.
  - Logical document order: reading order in DOM must match visual order.

- Images & Media
  - Every informative image has meaningful `alt` text; decorative images use empty `alt=""`.
  - Provide captions for complex images via `figcaption`.
  - Provide transcripts for audio and captions for video.

- Color & Contrast
  - Verify color contrast meets WCAG AA (4.5:1 for normal text).
  - Do not rely on color alone to convey meaning.

- Keyboard & Focus
  - All interactive elements reachable via keyboard (Tab, Enter/Space, Arrow keys where applicable).
  - Visible focus indicator using `:focus-visible`.
  - Skip link present and visible on focus.

- Forms
  - Use explicit `<label for>` associations.
  - Mark required fields and provide helpful error messages.
  - Ensure form validation is accessible (focus moves to the first invalid control).

- ARIA
  - Only use ARIA to fill semantic gaps; prefer native controls.
  - Verify ARIA attributes are correct and do not conflict with role semantics.

- Interactive Widgets
  - Use native elements where possible (`details/summary`, `<button>`, `<input>`).
  - If implementing custom widgets, provide keyboard handling and `aria-*` states.

- Tables
  - Use `<table>` only for tabular data; include `<caption>` and proper header cells.

- Tools & Testing
  - Run automated checks:
    - Lighthouse (Chrome): Accessibility score target >= 90.
    - axe-core CLI: `npx axe .` or integrate with CI.
  - Manual checks:
    - Keyboard-only navigation walkthrough.
    - Screen reader walkthrough (NVDA or VoiceOver).
    - Color contrast checks (Contrast Analyzer).

- Performance & SEO
  - Use `img` `srcset` and `sizes` for responsive images.
  - Use meaningful `title` and `meta description`.

If you'd like, I can extend this checklist into an automated QA script and example axe/lighthouse commands.
