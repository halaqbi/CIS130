# Lab 7 - Responsive Web Design

This folder contains my Lab 6 website with the responsive changes for Lab 7. The original pages, image, colors, and content are preserved.

## Two layout problems

1. The main content had no maximum width. At a 1200px viewport, it stretched to 1136px. I added `width: min(100% - 2rem, 1100px)` and centered it so it stays within the screen and stops growing at 1100px.
2. On a 390px screen, the open dropdown covered the content below the menu because it used absolute positioning. The small-screen submenu now stays visible in the normal page flow, so it does not cover the content.

## Breakpoint and navigation

The home page starts with one column and a 1rem gap. At `min-width: 768px`, the main content and sidebar become two columns with `flex: 2` and `flex: 1`. This keeps the phone layout stacked while allowing two readable columns at the tested tablet and desktop widths.

The menu stacks vertically by default and becomes a horizontal row at 768px. The wider layout keeps the dropdown, including keyboard focus support. The existing hover, focus, and current-page styling is preserved.

## Container query

The Web Learning Resources section contains two cards using the existing resource links. The `.card-panel` is an inline-size container named `cards`. The cards stack by default and switch to a wrapping row when that container is at least 500px wide. This depends on the space inside the section, rather than the viewport width alone.

## Testing

I tested all four pages in Google Chrome at 390px, 768px, and 1200px. Each page has a viewport meta tag. The image scales within the available width, and none of the pages scroll horizontally at these widths. The navigation links and submenu remain usable.

| Viewport | Home page layout | Navigation | Resource cards |
| --- | --- | --- | --- |
| 390px | One column | Vertical, submenu in page flow | Stacked |
| 768px | Two columns | Horizontal with dropdown | Stacked |
| 1200px | Two columns | Horizontal with dropdown | Side by side |
