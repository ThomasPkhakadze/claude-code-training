# Exercise 4: Product Landing Page

## Objective

Build a multi-section landing page for a fictional product. This exercise tests your ability to communicate a complex, multi-part design to Claude Code and produce something that looks like a real marketing page.

## What You'll Build

A complete landing page for **ThermoSmart Pro** -- a smart thermostat product. The page should include multiple sections that scroll vertically, like a real product website.

Required sections:

1. **Hero** -- Large headline, subtitle, call-to-action button, background image or gradient
2. **Features** -- 4 feature cards in a grid layout with icons or emoji placeholders
3. **Pricing** -- 3 pricing tiers displayed as cards (Basic, Pro, Enterprise)
4. **Testimonials** -- 3 customer quotes with names and roles
5. **Contact/CTA** -- Final call-to-action section with a form or contact info

## Content Source

Use the `content.md` file in this folder. It contains all the text, features, pricing, and testimonials you need.

## Design Specifications

| Element | Value |
|---------|-------|
| Background | #191919 (dark sections) alternating with #111111 |
| Primary accent | #ffc711 (MARTIVI yellow) |
| Secondary | #3cc5ee (MARTIVI cyan) |
| Font | Montserrat (headings) + Inter (body text) |
| Max content width | 1100px, centered |
| Section padding | Generous -- at least 80px top/bottom |

## Instructions

1. Read `content.md` to see all the text and data for the page
2. Ask Claude Code to build the landing page section by section, or all at once
3. Focus on making each section visually distinct while keeping a cohesive design
4. Iterate until the page looks polished and professional

## Success Criteria

- [ ] Single `index.html` file with all sections
- [ ] Hero section with headline, subtitle, and a visible CTA button
- [ ] 4 feature cards displayed in a grid (2x2 or 4 across)
- [ ] 3 pricing tiers with clear visual hierarchy (Pro tier should stand out)
- [ ] 3 testimonial quotes with attribution
- [ ] Contact or CTA section at the bottom
- [ ] Smooth visual flow from section to section
- [ ] Dark theme maintained throughout
- [ ] Fonts loaded from Google Fonts
- [ ] Page is scrollable and all sections are visible

## Tips

- Landing pages work best when there is clear visual hierarchy -- the hero should be the biggest and boldest section
- Pricing cards usually highlight one tier as "recommended" with a different color or size
- Testimonials look more credible with a photo placeholder (use a colored circle with initials)
- Add smooth scroll behavior with `html { scroll-behavior: smooth; }`
- Navigation links at the top that jump to each section are a nice touch

## Bonus Challenge

- Add a fixed navigation bar at the top that highlights the current section
- Add subtle scroll animations (fade in as sections come into view)
- Make the CTA button pulse or glow
- Add a "Back to Top" button that appears when scrolling down
- Make the page fully responsive for mobile screens
