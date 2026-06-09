# Ease Theme Tokens (SS) — CSS Custom Properties for Theme Customization

> Addresses [Issue #3286](https://github.com/SAPTARSHI-coder/EaseMotion-css/issues/3286) — Feature Request: Add CSS custom properties (variables) for easy theme customization.

## 1. What does this do?

Provides a self-contained, framework-agnostic set of CSS custom properties (theme tokens) that let users re-theme **colors, animation durations, easings, spacing, and sizing** of any EaseMotion-powered page by overriding a single variable — with no edits to core stylesheets.

## 2. How is it used?

```html
<!-- 1) Link the stylesheet -->
<link rel="stylesheet" href="style.css">

<!-- 2) Use the themed components anywhere in your HTML -->
<div class="theme-card">Card uses --ease-theme-surface + radius tokens</div>
<button class="theme-btn">Uses --ease-theme-primary on hover</button>
<span class="theme-badge">Pulsing badge with theme easing</span>
<span class="theme-float">Floating element</span>

<div class="theme-alert theme-alert--success">Saved successfully</div>
<div class="theme-alert theme-alert--danger">Something went wrong</div>
<div class="theme-alert theme-alert--warning">Check your input</div>
<div class="theme-alert theme-alert--info">New version available</div>

<!-- 3) Switch the entire theme with one attribute -->
<html data-theme="ocean"> ... </html>
<html data-theme="sunset"> ... </html>
<html data-theme="forest"> ... </html>
<html data-theme="rose"> ... </html>

<!-- 4) Override any token at :root, on a parent, or inline -->
<style>
  :root {
    --ease-theme-primary: #0ea5e9;     /* rebrand globally */
    --ease-theme-duration-base: 600ms; /* slow every animation */
  }
</style>
```

## 3. Why is it useful?

EaseMotion CSS's philosophy is to be **lightweight, beginner-friendly, and modular**. Issue #3286 asked for a way to customize theme, colors, and animation parameters without modifying the core stylesheet — and that's exactly what theme tokens provide:

- **Zero JS dependency** — pure CSS custom properties cascading through every component.
- **One place to rebrand** — override `--ease-theme-primary` (and friends) at `:root` and the entire UI updates instantly.
- **Three knobs, one override** — colors, durations, easings, spacing, and radius are all swappable independently.
- **Framework-friendly** — works *alongside* EaseMotion's existing `--ease-*` core tokens, not against them. Contributors can use `--ease-theme-*` for any new component and integrate cleanly later.
- **Accessibility-first** — auto dark/light mode via `prefers-color-scheme` and motion safety via `prefers-reduced-motion` (drops all durations to `0ms`).
- **No core edits** — fully self-contained, follows the submission-first pipeline.

### Token Surface (summary)

| Group | Examples |
|-------|----------|
| Brand colors | `--ease-theme-primary`, `--ease-theme-primary-soft`, `--ease-theme-secondary`, `--ease-theme-accent` |
| Semantic colors | `--ease-theme-success`, `--ease-theme-danger`, `--ease-theme-warning`, `--ease-theme-info` |
| Surfaces | `--ease-theme-bg`, `--ease-theme-surface`, `--ease-theme-surface-raised`, `--ease-theme-text`, `--ease-theme-text-muted`, `--ease-theme-border` |
| Durations | `--ease-theme-duration-instant`, `--ease-theme-duration-fast`, `--ease-theme-duration-base`, `--ease-theme-duration-slow`, `--ease-theme-duration-slower` |
| Easings | `--ease-theme-ease-linear`, `--ease-theme-ease-in`, `--ease-theme-ease-out`, `--ease-theme-ease-in-out`, `--ease-theme-ease-bounce`, `--ease-theme-ease-elastic` |
| Spacing | `--ease-theme-space-1` … `--ease-theme-space-8` |
| Radius | `--ease-theme-radius-sm`, `--ease-theme-radius-md`, `--ease-theme-radius-lg`, `--ease-theme-radius-xl`, `--ease-theme-radius-pill` |

### Built-in theme variants

Switch palette with a single attribute:

- `data-theme="ocean"` — sky/cyan
- `data-theme="sunset"` — orange/red/pink
- `data-theme="forest"` — green/lime/yellow
- `data-theme="rose"` — rose/fuchsia/purple
- `data-theme="default"` — remove the attribute

Switch motion feel:

- `data-motion="snappy"` — half the durations (faster, snappier)
- `data-motion="cinematic"` — double the durations (slower, more dramatic)
- `data-motion="default"` — remove the attribute

### Demo

Open `demo.html` in any modern browser. The demo includes a live theme switcher, motion switcher, themed components (card, button, badge, floating element, alert), a complete token reference table, override examples, and reduced-motion + dark-mode behavior baked in.
