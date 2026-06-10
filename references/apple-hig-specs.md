# Apple HIG Complete Specifications

> Extracted from developer.apple.com/design/human-interface-guidelines/
> Last updated: June 2026

## Foundations Index

### Color
- System colors auto-adapt to light/dark/increased contrast
- Minimum contrast: 4.5:1, recommended 7:1 for small text
- 10 accent colors: blue, green, indigo, orange, pink, purple, red, teal, yellow, mint, cyan
- Background hierarchy: primary → secondary → tertiary → grouped → elevated
- Label hierarchy: primary → secondary → tertiary → quaternary
- Separator: opaque (#C6C6C8) and non-opaque (rgba with 29% opacity)
- Fill hierarchy: primary (20%) → secondary (16%) → tertiary (12%) → quaternary (8%)

### Typography
- Font: SF Pro (system), SF Mono (code), New York (serif)
- Minimum sizes: iOS 11pt, macOS 10pt, web 16px body
- 11 text styles: Large Title → Caption 2
- Dynamic Type support with accessibility sizes
- Weights: Ultralight to Black; prefer Regular/Bold, avoid Thin/Light

### Layout
- 4px base grid
- Safe areas: top 44pt, bottom 34pt (iPhone with home indicator)
- Size Classes: Regular/Compact for width/height
- Breakpoints: 375/390/428/768/1024/1366/1920/2560px

### Materials
- Liquid Glass: Regular (blur) and Clear (translucent)
- 4 thickness levels: ultraThin, thin, regular, thick
- Vibrancy: label, secondaryLabel, tertiaryLabel, quaternaryLabel
- Fills: fill, secondaryFill, tertiaryFill

### Motion
- Target: 30-60 fps
- Durations: instant (100ms), fast (200ms), normal (300ms), slow (500ms)
- Easing: standard, decelerate, accelerate, spring, sharp
- Avoid ~0.2Hz oscillation (visionOS)

### Dark Mode
- Not simple color inversion
- Base (dimmer) vs Elevated (brighter) backgrounds
- Use semantic colors that auto-adapt
- Test with Increase Contrast + Reduce Transparency

### Accessibility
- Touch targets: 44×44pt minimum (60×60pt visionOS)
- Focus states: 2px solid blue outline
- Reduced motion: respect prefers-reduced-motion
- High contrast: prefer-contrast media query
- Screen reader: sr-only class for hidden text

### Writing
- Clear, friendly, helpful, concise tone
- Use verbs for button labels
- Sentence case, not Title Case
- Explain what happened + how to fix in errors

---

## Additional Foundations (detailed in apple-hig-missing.md)

The following foundations have brief coverage above but detailed implementation guidance in `references/apple-hig-missing.md`:
- Accessibility — Detailed ARIA patterns, screen reader support
- App Icons — Sizes, masks, guidelines per platform
- Branding — Logo usage, color palette
- Immersive Experiences — visionOS spatial computing
- Inclusion — Diversity, representation in imagery
- Privacy — Data handling, permission flows
- Right to Left — RTL layout support
- SF Symbols — Icon library usage, alternatives
- Spatial Layout — visionOS 3D layout patterns
