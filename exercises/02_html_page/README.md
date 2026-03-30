# Exercise 2: Styled Profile Page

## Objective

Build a professional-looking profile page with multiple sections and styled components. This exercise introduces CSS layout concepts like cards, grids, and typography.

## What You'll Build

A single `index.html` file that looks like a personal portfolio card, featuring:

- Dark theme background (#191919)
- Montserrat font from Google Fonts
- A profile header section with name and title
- 3 stat cards in a row (e.g., "5 Years Experience", "30+ Projects", "12 Happy Clients")
- A short bio section
- Clean spacing and modern styling throughout

## Instructions

1. Open Claude Code in this folder
2. Describe the page you want, referencing the requirements above
3. Review the output in your browser
4. Iterate -- ask for changes until it looks professional

## Design Specifications

| Element | Value |
|---------|-------|
| Background | #191919 |
| Text color | #ffffff |
| Accent color | #ffc711 (yellow) |
| Font | Montserrat (Google Fonts) |
| Card background | #2a2a2a |
| Card border radius | 12px |
| Max content width | 900px, centered |

## Success Criteria

- [ ] File `index.html` exists in this folder
- [ ] Page uses dark theme (#191919 background)
- [ ] Montserrat font is loaded from Google Fonts
- [ ] Name and title/role are displayed prominently
- [ ] Exactly 3 stat cards are shown in a horizontal row
- [ ] Cards have a slightly lighter background than the page
- [ ] A bio/about section is present with at least 2 sentences
- [ ] Page is responsive (looks okay when you resize the browser window)
- [ ] No horizontal scrollbar appears

## Tips

- If the cards stack vertically instead of sitting side by side, ask Claude Code to use CSS Flexbox or Grid
- If the font doesn't look different from default, check that the Google Fonts link tag is in the `<head>`
- Try resizing your browser window to see if the layout adapts
- You can ask: "Make the stat numbers bigger and yellow" to emphasize them

## Bonus Challenge

- Add hover effects on the stat cards (subtle scale or color change)
- Add a skills section with tag-style badges
- Add a subtle gradient or pattern to the header area
- Make the stat numbers count up with a CSS animation
