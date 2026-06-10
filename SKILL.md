---
name: apple-ui
description: "Apple Human Interface Guidelines — complete design system for web: principles, colors, typography, layout, components, patterns, dark mode, accessibility, materials, motion, writing."
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  source: https://developer.apple.com/design/human-interface-guidelines
  last_updated: "2026-06-11"
  platform: web
  tags: [design, apple, ui, typography, color, layout, components, dark-mode, materials, motion]
---

# Apple UI Design System

Apple's Human Interface Guidelines adapted for web development. Complete design tokens, component specs, and patterns — all in CSS/HTML.

## Quick Reference

- `references/foundations.md` — Color, typography, layout, materials, motion, dark mode specs
- `references/components.md` — All UI components with CSS implementations
- `references/patterns.md` — 25 design patterns (loading, onboarding, searching, etc.)
- `references/additional-components.md` — 35 additional components (charts, widgets, notifications, etc.)
- `references/scraping-guide.md` — How to scrape Apple HIG (JS-rendered SPA), page inventory, parallel strategy

## Coverage Summary

| Category | Pages | Status |
|----------|-------|--------|
| Foundations | 18/18 | ✅ Complete |
| Components | 50+ | ✅ Complete |
| Patterns | 25/25 | ✅ Complete |
| Inputs (hardware) | 13 | ⏭️ Skipped (not web-relevant) |
| Technologies | N/A | ⏭️ Skipped (platform-specific) |

## Design Principles

1. **Clarity** — Text legible at every size, icons precise, adornments subtle
2. **Deference** — UI supports content, doesn't compete with it
3. **Depth** — Visual layers and realistic motion convey hierarchy

## Quick Start

```css
/* Import Apple design tokens */
:root {
  /* Colors */
  --apple-blue: #007AFF;
  --apple-green: #34C759;
  --apple-red: #FF3B30;
  --apple-orange: #FF9500;
  --apple-yellow: #FFCC00;
  --apple-pink: #FF2D55;
  --apple-purple: #AF52DE;
  --apple-indigo: #5856D6;
  --apple-teal: #5AC8FA;
  
  /* Backgrounds */
  --bg-primary: #FFFFFF;
  --bg-secondary: #F2F2F7;
  --bg-elevated: #FFFFFF;
  
  /* Labels */
  --label-primary: #000000;
  --label-secondary: rgba(60, 60, 67, 0.6);
  --label-tertiary: rgba(60, 60, 67, 0.3);
  
  /* Spacing (4px base) */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  
  /* Radius */
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-full: 9999px;
  
  /* Shadows */
  --shadow-sm: 0 1px 3px rgba(0,0,0,0.08);
  --shadow-md: 0 4px 12px rgba(0,0,0,0.12);
  --shadow-lg: 0 8px 24px rgba(0,0,0,0.16);
  
  /* Typography */
  --font-sans: -apple-system, BlinkMacSystemFont, 'SF Pro Text', 'Segoe UI', Roboto, sans-serif;
  --font-mono: 'SF Mono', ui-monospace, 'Cascadia Code', Menlo, monospace;
}

/* Dark mode */
@media (prefers-color-scheme: dark) {
  :root {
    --bg-primary: #000000;
    --bg-secondary: #1C1C1E;
    --bg-elevated: #1C1C1E;
    --label-primary: #FFFFFF;
    --label-secondary: rgba(235, 235, 245, 0.6);
    --label-tertiary: rgba(235, 235, 245, 0.3);
  }
}
```

## Component Quick Reference

### Buttons
```css
.btn { height: 44px; padding: 0 20px; border-radius: 10px; font-size: 17px; font-weight: 600; }
.btn-filled { background: var(--apple-blue); color: white; }
.btn-tinted { background: rgba(0,122,255,0.1); color: var(--apple-blue); }
.btn-plain { background: transparent; color: var(--apple-blue); font-weight: 400; }
```

### Cards
```css
.card { background: var(--bg-elevated); border-radius: 12px; box-shadow: var(--shadow-sm); }
.card:hover { transform: translateY(-2px); box-shadow: var(--shadow-md); }
```

### Lists
```css
.list-item { display: flex; align-items: center; gap: 12px; padding: 12px 16px; min-height: 44px; }
.list-item:hover { background: var(--fill-quaternary); }
```

### Navigation
```css
.navbar { height: 44px; padding: 0 16px; background: var(--bg-primary); backdrop-filter: blur(20px); }
.tabbar { height: 83px; background: var(--bg-primary); border-top: 0.5px solid var(--separator); }
```

### Forms
```css
.input { height: 44px; padding: 0 16px; background: var(--bg-tertiary); border-radius: 10px; }
.toggle { width: 51px; height: 31px; background: var(--fill-primary); border-radius: 15.5px; }
.toggle.active { background: var(--apple-green); }
```

### Modals
```css
.sheet { position: fixed; bottom: 0; max-height: 90vh; background: var(--bg-elevated); border-radius: 12px 12px 0 0; }
.alert { width: 270px; background: var(--bg-elevated); border-radius: 14px; }
```

## Key Numbers

- **Touch target**: 44×44px minimum (60×60px for visionOS)
- **Contrast ratio**: 4.5:1 minimum, 7:1 recommended
- **Font sizes**: Body 17px, minimum 16px
- **Spacing**: 4px base grid
- **Animation**: 200ms fast, 300ms standard, 500ms slow
- **Corner radius**: 8px small, 12px medium, 16px large

## Pitfalls

- **Don't use emoji as icons** — Use Lucide or SF Symbols alternatives
- **Don't hardcode colors** — Use CSS variables for light/dark support
- **Don't skip dark mode** — Always provide both themes
- **Don't use thin font weights** — Prefer Regular/Bold, avoid Ultralight/Thin/Light
- **Don't ignore touch targets** — 44×44px minimum for all interactive elements
- **Don't nest scroll views** — Avoid same-direction scroll nesting
- **Don't use native controls** — Style all inputs with `appearance: none`
- **Don't claim completeness without verification** — Apple HIG has 70+ pages across Foundations, Components, Patterns, Inputs, Technologies. The nav tree is JS-rendered and won't fully expand via browser_console. Always cross-check against the official site structure before claiming full coverage. When user asks "are you sure?", they're usually right that something's missing.
- **Skill structure matters** — When creating or updating skills, follow the standard format: frontmatter (name, description, version, author, license, metadata), Quick Reference index, Coverage Summary, concise main file with details in references/. A 1800-line SKILL.md is too long — move detailed specs to references/.

## Resources

### Official
- [Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines)
- [Apple Design Resources](https://developer.apple.com/design/resources)
- [SF Symbols](https://developer.apple.com/sf-symbols)

### Web Tools
- [Lucide Icons](https://lucide.dev) — SF Symbols alternative for web
- [Tailwind CSS](https://tailwindcss.com) — Utility-first CSS
- [Radix UI](https://www.radix-ui.com) — Accessible components

### Inspiration
- [Apple.com](https://www.apple.com)
- [Linear](https://linear.app)
- [Stripe](https://stripe.com)
