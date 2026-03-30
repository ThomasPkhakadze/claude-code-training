# Day 5: Presentations

**NEW SKILL UNLOCKED: You can build multi-slide presentations**

Estimated time: 3-4 hours

---

**What you will start with:** A single-page dashboard with stat cards and charts.

**What you will end with:** A multi-slide scrollable presentation with a title slide, data slides, charts, and a summary -- the kind of report you would present to a client in a meeting.

---

## What Are HTML Presentations?

You know PowerPoint and Google Slides. They create presentations with discrete slides that you click through. HTML presentations work differently: each "slide" is a section of a web page that takes up the full screen. You scroll down to move to the next slide.

Why use HTML instead of PowerPoint?

- **No software needed.** The client opens a link in their browser.
- **Always up to date.** You can update the content and the link stays the same.
- **Interactive charts.** Hover over data, click on elements -- things PowerPoint cannot do.
- **Consistent branding.** Define your colors and fonts once, and they apply everywhere.

This is how the agency delivers monthly performance reports. Today you will learn the format.

---

## The Pattern: Full-Height Slides

Each slide is a `<div>` (a container) with a minimum height of `100vh` -- which means "100% of the viewport height." In plain terms: each section takes up at least one full screen. When the viewer scrolls, the next slide comes into view.

You do not need to memorize this. Just know that when you tell Claude "make each section a full-screen slide," this is the technique it will use.

---

## CSS Variables: Define Once, Use Everywhere

Imagine you are building a presentation and you use the color `#ffc711` (yellow) in 20 different places. Then the client says "can you make it a bit more orange?" You would have to find and change all 20 places.

CSS variables solve this. You define the color once at the top of your file:

```
--accent-yellow: #ffc711;
```

And then every element that uses yellow refers to this variable. Change it once, and it updates everywhere. Think of it like "Find and Replace" built into the design system.

When you ask Claude to use CSS variables, it will set up this system for you. The benefit is that if you ever need to change the brand colors, you only change one line.

---

## Exercise: Build a 4-Slide Presentation

Start Claude Code:

```bash
cd claude-code-training
claude
```

Then give Claude this prompt:

```
Create exercises/04_landing_page/presentation.html -- a scrollable presentation
for "Cafe Batumi - Monthly Performance Review, March 2026."

DESIGN SYSTEM (use CSS variables):
- --bg-dark: #191919
- --bg-card: #262626
- --accent-yellow: #ffc711
- --accent-cyan: #3cc5ee
- --text-white: #ffffff
- --text-gray: #aaaaaa
- Font: Montserrat from Google Fonts
- Use Chart.js from CDN for any charts

Each slide is a full-viewport-height section (min-height: 100vh).
Add a slide number in the bottom-right corner of each slide ("1 / 4", "2 / 4", etc.).

SLIDE 1 -- TITLE
- Center-aligned
- Large heading: "Cafe Batumi"
- Subheading: "Monthly Performance Review"
- Below that: "March 2026"
- MARTIVI DIGITAL branding at the bottom: "MARTIVI" in yellow + "DIGITAL" in cyan
- Clean, minimal, impressive first impression

SLIDE 2 -- OVERVIEW
- Section title: "Performance Overview"
- 4 stat cards in a row:
  - Reach: 45,200
  - Impressions: 89,300
  - Engagements: 3,400
  - Spend: $250
- Below the cards: a short paragraph summarizing the month:
  "March showed strong growth across all channels. Reach increased by 18%
  compared to February, driven primarily by the Spring Menu Launch campaign.
  Engagement rate remained healthy at 3.8%."
- MARTIVI DIGITAL footer

SLIDE 3 -- CHARTS
- Section title: "Campaign Performance"
- Two charts side by side:
  LEFT: Horizontal bar chart "Top Ads by Reach" with the 5 ads data (yellow bars)
  RIGHT: Doughnut chart "Spend by Platform" -- Meta $180, Google $70 (yellow and cyan)
- MARTIVI DIGITAL footer

SLIDE 4 -- SUMMARY
- Section title: "Key Takeaways"
- 3 takeaway cards stacked or in a row:
  Card 1: "Spring Menu Launch drove 27% of total reach"
  Card 2: "Google Ads CTR outperformed Meta by 1.3 percentage points"
  Card 3: "Recommendation: Increase weekend campaign budget for Q2"
- Each card has an icon or number (1, 2, 3), a title area, and the text
- Cards have #262626 background with yellow top border
- MARTIVI DIGITAL footer

Make it look polished and professional.
```

Approve the file. Open it:

```bash
open exercises/04_landing_page/presentation.html
```

Scroll through all 4 slides. Each one should fill the screen and tell part of the story.

---

## Iterate: Polish the Presentation

Try these refinements:

**Smooth scrolling:**
```
Add smooth scrolling behavior so that when you scroll,
the page glides between slides instead of jumping.
```

**Slide transitions:**
```
Add a subtle fade-in animation to each slide's content
so that elements appear as you scroll to them.
```

**Better typography:**
```
Make the title slide heading really large and bold.
Use lighter font weight for the subtitle.
Add more vertical spacing between elements.
```

**Visual consistency:**
```
Make sure all four slides have the same amount of padding
on the sides, and that the footer is in exactly the same
position on every slide.
```

These small refinements are the difference between "functional" and "professional." Clients notice polish even if they cannot articulate what makes something look good.

---

## Compare: Dashboard vs Presentation

You now have two different ways to show the same data:

- **Dashboard** (Day 3-4): Everything on one page, dense with information, designed for someone who wants to dig into the numbers
- **Presentation** (Today): Information split across slides, designed for storytelling, guiding the viewer through a narrative

Both have their place. Dashboards are for ongoing monitoring. Presentations are for monthly reviews and meetings. Knowing how to build both makes you versatile.

---

## Commit Your Work

```
Commit my work with the message: "day-5: multi-slide cafe batumi presentation with charts"
```

Then push:

```
Push my changes to GitHub
```

---

## What You Accomplished Today

- Learned what HTML presentations are and why they are used
- Understood the full-height slide pattern
- Used CSS variables to create a consistent design system
- Built a 4-slide presentation with title, stats, charts, and summary
- Added slide numbers for navigation
- Applied MARTIVI DIGITAL branding throughout
- Practiced polishing a presentation with animations and typography

**Deliverable:** `exercises/04_landing_page/presentation.html`

**Tomorrow:** You will step back from building and focus on a crucial skill -- how to write prompts that get great results on the first try.

**Go to [Day 6: Prompt Engineering](DAY_6_PROMPT_ENGINEERING.md)**
