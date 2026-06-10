# Apple HIG Components Reference

## Buttons
- **Sizes**: xs (28px), sm (34px), md (44px), lg (50px), xl (56px)
- **Styles**: Filled, Tinted, Gray, Plain, Bordered, Destructive
- **Shapes**: Circle (icon), Capsule (text+icon), Rounded rect (text)
- **States**: Normal, Press, Hover, Selected, Unavailable, Disabled
- **Hit region**: 44×44px minimum (60×60px visionOS)

## Text Fields
- **Height**: 44px
- **Corner radius**: 10px
- **Padding**: 16px horizontal
- **Placeholder**: tertiary label color
- **Focus**: 2px blue outline
- **Clear button**: trailing end
- **Secure field**: password input

## Toggles
- **Switch**: 51×31px, green=on, gray=off
- **Checkbox**: 22×22px, 4px radius, checkmark
- **Radio**: 22×22px, circle, filled=selected
- **Mixed state**: checkbox only (dash)

## Sliders
- **Track**: 4px height, 2px radius
- **Thumb**: 28×28px circle, white, shadow
- **Track fill**: accent color
- **Optional min/max icons**
- **Tick marks** (macOS)

## Steppers
- **Two buttons** (-/+), 44×36px each
- **Border**: 1px separator
- **Radius**: 8px
- **Value display** between buttons
- **Shift-click** for ×10 (macOS)

## Segmented Controls
- **Height**: 32px
- **Radius**: 8px
- **Padding**: 2px
- **Segments**: equal width
- **Active**: white bg + shadow
- **Limit**: 5-7 segments

## Pickers
- **Compact**: button + popover
- **Inline**: expanded in place
- **Wheels**: scrolling columns
- **Date modes**: Date, Time, Date & Time, Countdown
- **Minute interval**: divisible by 60

## Color Wells
- **Square shape**
- **Shows current color**
- **Opens color picker** on click
- **Supports drag & drop** (macOS)

## Lists and Tables
- **Text-centric content**
- **Row height**: auto or fixed
- **Headers**: 13px, uppercase, gray
- **Selected**: light blue bg
- **Edit mode** support

## Collections
- **Image-centric content**
- **Grid layout** with auto-fill
- **Aspect ratio**: 1:1 or custom
- **Hover**: scale 1.02

## Split Views
- **Multi-pane layout**
- **Primary**: 300px (min 200, max 400)
- **Secondary**: flex 1
- **Divider**: 4px, resize cursor
- **Three-pane** support

## Navigation Bars
- **Height**: 44px
- **Title**: 17px Bold (center) or 34px Large Title (left)
- **Back button**: < chevron + previous page title
- **Blur background**: backdrop-filter: blur(20px)

## Tab Bars
- **Height**: 83px (49 + 34 safe area)
- **Icon size**: 25×25px
- **Active tint**: accent color
- **Inactive tint**: gray
- **Badge**: red oval with white text

## Sidebars
- **Width**: 280px (min 200, max 320)
- **Sections** with titles
- **Selected**: accent color bg
- **Hide/show** support

## Toolbars
- **Height**: 44px
- **Title**: ≤15 characters
- **Back/Forward** navigation
- **More menu** for overflow

## Search Fields
- **Height**: 36px
- **Radius**: 10px
- **Search icon**: 16px, gray
- **Clear button**: 18px circle
- **Scope bar** for categories
- **Tokens** for search criteria

## Alerts
- **Width**: 270px
- **Title**: 17px, semibold
- **Message**: 13px, secondary color
- **Max 3 buttons**, 1-2 words each
- **Destructive**: system red

## Action Sheets
- **Destructive button** at top, red style
- **Always provide** Cancel button
- **Avoid scrolling**
- **Title**: single line

## Sheets
- **Support detents** (large, medium)
- **Include grabber** for drag
- **Modal or nonmodal**
- **Max height**: 90vh

## Popovers
- **Arrow points** to source control
- **Size to fit** content
- **Don't use** for warnings
- **macOS**: detachable

## Scroll Views
- **No visual appearance**
- **Elastic scrolling**
- **Page-by-page** support
- **Scroll indicators**: semi-transparent

## Progress Indicators
- **Linear**: 4px height, 2px radius
- **Circular**: SVG with stroke-dashoffset
- **Spinner**: 20px, border-top animation
- **Activity indicator**: spinning dots

## Context Menus
- **Long press** / Control+click triggered
- **Short labels** + icons
- **Separator groups** (≤3)
- **Destructive**: red text
- **Hide unavailable** items

## Menus
- **iOS layouts**: Small (4 icon rows + list), Medium (3 icons + label row + list), Large (full list)
- **Labels**: verbs, title-style capitalization, no articles, ellipsis for extra input
- **Toggleable** (change label/checkmark), disabled items grayed
- **Submenus** ≤1 level deep

## Avatars
- **Sizes**: xs (24px), sm (32px), md (44px), lg (56px), xl (72px)
- **Circle shape**
- **Initials**: 18px, semibold
- **Group**: overlapping with border

## Badges
- **Min width**: 20px, height: 20px
- **Colors**: red (default), blue (primary), green (success), orange (warning)
- **Dot badge**: 8px circle
- **Padding**: 0 6px

## Chips / Tags
- **Height**: 28px
- **Radius**: 14px (pill)
- **Background**: fill-secondary
- **Active**: accent color bg
- **Close button**: 16px circle

## Skeleton Loading
- **Shimmer animation**: 1.5s infinite
- **Background**: linear-gradient with fill colors
- **Match content** layout
- **Border radius**: 8px

## Toast / Notification
- **Position**: fixed, top 56px
- **Border left**: 4px colored accent
- **Animation**: slide down
- **Duration**: 3-5 seconds
- **Types**: success, error, warning, info

## Page Controls
- **Dots**: 8px circle
- **Active**: filled
- **Inactive**: outline or transparent
- **Max ~10 dots**
- **Centered** at bottom

## Gauges
- **Display value** within a range
- **Styles**: Standard, Capacity, Accessory
- **Supports gradient** fills
- **macOS**: Continuous/Discrete/Tiered

## Rating Indicators
- **Star symbols** for ranking
- **Horizontal equal** spacing
- **No partial symbols**
- **Read-only** display

## Activity Rings
- **Move**: #FF2D55 (red)
- **Exercise**: #30D158 (green)
- **Stand**: #007AFF (blue)
- **Must use** black background
- **Read-only**, cannot change colors

## Widgets
- **iOS Small**: 170×170pt, Medium: 364×170pt, Large: 364×382pt
- **iPad**: Small 160×160pt, Medium 356×160pt, Large 356×356pt, Extra Large 748×356pt
- **Accessory**: Circular 72×72pt, Rectangular 160×72pt, Inline 234×26pt
- **Rendering**: Full-color / Accented / Vibrant
- **Standard margins**: 16pt, minimum 11pt

## Live Activities
- **Track real-time** progress (delivery, sports, fitness)
- **Max 8 hours**
- **Compact**: 52.33×36.67pt
- **Expanded**: 371×84-160pt
- **Dynamic Island**: 230pt (Pro) / 250pt (Pro Max)

## Notifications
- **Requires** user permission
- **Support custom** sounds, action buttons (max 4)
- **Badge displays** unread count
- **watchOS**: Short Look / Long Look

## Charts
- **Bar/Line/Point** marker types
- **Fixed/dynamic** axis ranges
- **Tick marks**, grid lines, titles, annotations, legends
- **Interactive** (drag to view values)
- **Full accessibility** (VoiceOver + Audio Graphs)

## Image Views
- **Single image** or animation sequence
- **Stretchable/scaleable**/fit/position
- **Transparent/opaque** background
- **Not interactive** by default

## Text Views
- **Multi-line** formatted text, optionally editable
- **Leading aligned**, system label colors
- **Supports multiple** fonts/colors/alignments/Dynamic Type
- **iOS**: multiple keyboard types

## Web Views
- **Load and display** HTML/website content in-app
- **Support forward/back** navigation (must enable)
- **Don't build** full-featured browser
