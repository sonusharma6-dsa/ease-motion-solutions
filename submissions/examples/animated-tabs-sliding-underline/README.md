# Sliding Underline Tabs Component

A pure-CSS animated Tabs component featuring smooth, GPU-accelerated underline sliding transitions when changing active tabs.

## Features
- Zero JS dependency (built on radio input check selectors).
- Fluid sliding active bar powered by CSS transitions and `transform: translateX()`.
- Responsive flex layout with auto-fitting header tabs.
- Clean fading animations for active content panels.

## Usage
Structure your HTML using input radio selectors, paired labels, and a `.em-tab-underline` child inside the navbar:

```html
<div class="em-tabs">
  <!-- Controllers -->
  <input type="radio" id="tab-1" name="tabs" class="em-tab-input" checked />
  <input type="radio" id="tab-2" name="tabs" class="em-tab-input" />
  
  <!-- Navigation Header -->
  <div class="em-tabs-nav">
    <label for="tab-1" class="em-tab-label">Tab 1</label>
    <label for="tab-2" class="em-tab-label">Tab 2</label>
    <div class="em-tab-underline"></div>
  </div>
  
  <!-- Content Panels -->
  <div class="em-tabs-content">
    <div id="panel-1" class="em-tab-panel">Content 1</div>
    <div id="panel-2" class="em-tab-panel">Content 2</div>
  </div>
</div>
```
