# Apple HIG Additional Components

## Combo Boxes (macOS)
- Combines text field with dropdown button
- User can type custom value or select from list
- Fill with meaningful default value
- Label: title-style capitalization + colon

## Digit Entry Views (tvOS)
- Full-screen numeric PIN input
- Secure field masks digits with asterisks
- Clear description of input purpose

## Image Wells (macOS)
- Editable image view supporting copy/paste/drag-drop/delete
- Shows default image when empty

## Virtual Keyboards
- iOS: ~216-350pt height
- Types: ASCII, numeric, decimal, email, URL, phone, web search
- System-provided, can customize input view

## Page Controls
- Flat list page position indicator
- Dots: filled = current page
- Max ~10 dots, centered at bottom
- Three background styles: automatic/prominent/minimal

## Panels (macOS)
- Floating auxiliary control/info panel
- Standard and HUD (dark translucent) styles
- Short noun title
- Shows when app active, hides when inactive

## Windows
- visionOS default: 1280×720pt at 2 meters
- Styles: Default (glass), Volumetric, Plain
- States: Main, Key, Inactive

## Path Controls (macOS)
- Displays selected file/folder path
- Standard (linear) or popup style

## Token Fields (macOS)
- Text auto-converts to actionable tokens
- Tokens: selectable, draggable, context menu
- Comma or Return triggers conversion

## Context Menus
- Long press / Control+click triggered
- Short labels + icons
- Separator groups (≤3)
- Destructive: red text
- Hide unavailable items (don't gray out)

## Dock Menus (macOS)
- Right-click app icon in Dock
- Custom items + window list
- High-frequency operations

## Edit Menus
- Appears after content selection
- Commands: Copy, Cut, Paste, Select, Translate, Look Up
- iOS: compact horizontal → expandable context menu

## Home Screen Quick Actions (iOS)
- Long press app icon, max 4 actions
- Title + SF Symbol + optional subtitle
- Dynamic updates supported
- Don't use emoji, use Quick Action Icon Template

## Menus
- iOS layouts: Small (4 icon rows + list), Medium (3 icons + label row + list), Large (full list)
- Labels: verbs, title-style capitalization, no articles, ellipsis for extra input
- Toggleable (change label/checkmark), disabled items grayed
- Submenus ≤1 level deep

## Ornaments (visionOS)
- Floating controls at window edges
- Width ≤ associated window
- Glass material background
- Borderless buttons
- Used for toolbars, tab bars, video controls

## Pop-up Buttons
- Shows mutually exclusive options in flat list
- Selected item updates button label
- Supports Custom option for additional items

## Pull-down Buttons
- Shows action list related to button purpose
- Destructive: red text + confirmation
- Supports More button (ellipsis icon)

## The Menu Bar (macOS/iPadOS)
- macOS height: 24pt
- Standard order: App→File→Edit→Format→View→Custom→Window→Help
- iPadOS: hidden overlay, swipe down from top

## Activity Rings
- Move=#FF2D55 (red), Exercise=#30D158 (green), Stand=#007AFF (blue)
- Must use black background, circular crop
- Read-only, cannot change colors/opacity/filters

## Gauges
- Display value within a range
- Styles: Standard, Capacity, Accessory
- Supports gradient fills
- macOS: Continuous/Discrete/Tiered

## Rating Indicators (macOS)
- Star symbols for ranking
- Horizontal equal spacing
- No partial symbols
- Read-only display

## App Shortcuts
- Access via Siri/Spotlight/Shortcuts/Action button
- Max 10 per app
- SF Symbols, short memorable phrases
- Support parameter variants

## Complications (watchOS)
- Circular: 50×50pt (45mm)
- Corner: 38×38pt (45mm)
- Inline/Utilitarian: Small 26×26pt
- Rectangular: 193×82pt (45mm)
- Line width ≥2pt
- Closed/Open/Segmented gauge
- Tinted mode (monochrome)

## Controls
- Control Center/Lock Screen/Action button access
- Symbol + title + optional value
- on/off toggle with animated symbol transition
- Supports remote push updates

## Live Activities
- Track real-time progress (delivery, sports, fitness)
- Max 8 hours
- Compact Leading/Trailing: 52.33×36.67pt
- Expanded: 371×84-160pt
- Dynamic Island width: 230pt (Pro) / 250pt (Pro Max)
- Supports alert notifications and interaction

## Notifications
- Requires user permission
- Support custom sounds, action buttons (max 4), SF Symbol icons
- Badge displays unread count
- watchOS: Short Look / Long Look
- Double Tap support (watchOS)

## Snippets
- Siri/App Shortcut result or confirmation display
- Max height: 400pt
- Types: Confirmation (Cancel + Primary) / Result (Done button)

## Status Bars (iOS)
- System-defined, transparent background
- Can temporarily hide for full-screen media
- Use scroll edge effect for readability

## Top Shelf (tvOS)
- Full screen static: 2320×720pt (16:9)
- Poster: 404×608pt (2:3)
- Square: 608×608pt (1:1)
- 16:9: 908×512pt
- Scrolling Inset Banner: 1940×692pt
- Supports video preview autoplay

## Watch Faces (watchOS)
- Main view with customizable complications
- Share watch faces with others
- Graceful degradation for incompatible faces

## Widgets
- iOS Small: 170×170pt, Medium: 364×170pt, Large: 364×382pt
- iPad: Small 160×160pt, Medium 356×160pt, Large 356×356pt, Extra Large 748×356pt
- Accessory: Circular 72×72pt, Rectangular 160×72pt, Inline 234×26pt
- Rendering: Full-color / Accented / Vibrant
- Appearances: Light/Dark/Clear/Tinted
- Standard margins: 16pt, minimum 11pt
- Periodic refresh (not real-time)
- Support Dynamic Type to AX5

## Charts
- Bar/Line/Point marker types
- Fixed/dynamic axis ranges
- Tick marks, grid lines, titles, subtitles, annotations, legends
- Interactive (drag to view values)
- Full accessibility (VoiceOver + Audio Graphs)

## Image Views
- Single image or animation sequence
- Stretchable/scaleable/fit/position
- Transparent/opaque background
- Not interactive by default (use Button for clickable)

## Text Views
- Multi-line formatted text, optionally editable
- Leading aligned, system label colors
- Supports multiple fonts/colors/alignments/Dynamic Type
- iOS: multiple keyboard types

## Web Views
- Load and display HTML/website content in-app
- Support forward/back navigation (must enable)
- Don't build full-featured browser
