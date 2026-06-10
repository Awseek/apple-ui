# Apple HIG Scraping Strategy

## How to Scapple Apple HIG

Apple HIG is a JavaScript-rendered SPA — `curl` doesn't work. Use browser automation.

### Method 1: Browser Console Extraction
```javascript
// Navigate to a page, then extract main content
document.querySelector('main')?.innerText
```

### Method 2: Nav Tree Expansion
```javascript
// Expand all sections in the navigation tree
const buttons = document.querySelectorAll('[aria-label="Documentation Navigator"] button');
buttons.forEach(btn => {
  if (btn.getAttribute('aria-expanded') === 'false') {
    btn.click();
  }
});

// Wait, then collect all links
setTimeout(() => {
  const nav = document.querySelector('[aria-label="Documentation Navigator"]');
  const links = nav.querySelectorAll('a');
  links.forEach(link => {
    const href = link.getAttribute('href');
    const text = link.textContent.trim();
    // Process...
  });
}, 2000);
```

### Limitations
- Nav tree doesn't fully expand via JS — only shows current section's children
- Some pages redirect (e.g., `/table-views` → `/lists-and-tables`)
- Content is dynamically loaded — must wait for render

### Parallel Scraping
Use `delegate_task` with 3 parallel workers for faster scraping:
- Worker 1: Foundations (18 pages)
- Worker 2: Components (50+ pages)
- Worker 3: Patterns (25 pages)

Each worker takes ~4 minutes. Serial scraping takes ~20 minutes.

## Page Structure

### Foundations (18 pages)
accessibility, app-icons, branding, color, dark-mode, icons, images, immersive-experiences, inclusion, layout, materials, motion, privacy, right-to-left, sf-symbols, spatial-layout, typography, writing

### Components (8 categories, 64 pages)
- Content: charts, image-views, text-views, web-views
- Layout: boxes, collections, column-views, disclosure-controls, labels, lists-and-tables, lockups, outline-views, split-views, tab-views
- Menus: activity-views, buttons, context-menus, dock-menus, edit-menus, home-screen-quick-actions, menus, ornaments, pop-up-buttons, pull-down-buttons, the-menu-bar, toolbars
- Navigation: path-controls, search-fields, sidebars, tab-bars, token-fields
- Presentation: action-sheets, alerts, page-controls, panels, popovers, scroll-views, sheets, windows
- Selection: color-wells, combo-boxes, digit-entry-views, image-wells, pickers, segmented-controls, sliders, steppers, text-fields, toggles, virtual-keyboards
- Status: activity-rings, gauges, progress-indicators, rating-indicators
- System: app-shortcuts, complications, controls, live-activities, notifications, snippets, status-bars, top-shelf, watch-faces, widgets

### Patterns (25 pages)
charting-data, collaboration-and-sharing, drag-and-drop, entering-data, feedback, file-management, going-full-screen, launching, live-viewing-apps, loading, managing-accounts, managing-notifications, modality, multitasking, offering-help, onboarding, playing-audio, playing-haptics, playing-video, printing, ratings-and-reviews, searching, settings, undo-and-redo, workouts

### Inputs (13 pages, hardware-specific, not web-relevant)
action-button, apple-pencil-and-scribble, camera-control, digital-crown, eyes, focus-and-selection, game-controls, gestures, gyroscope-and-accelerometer, keyboards, nearby-interactions, pointing-devices, remotes
