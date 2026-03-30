# Day 3: Debug and Optimize

**NEW SKILL UNLOCKED: Debug, optimize, and iterate at speed**

Estimated time: 4-5 hours

---

**What you will start with:** Your 6-slide client report from Day 2 and a broken dashboard that needs fixing.

**What you will end with:** A fixed dashboard, a fully responsive client report, five rapid client feedback changes, and a git branch with clean commit history.

---

## Part 1 -- Debug Challenge

There is a broken dashboard waiting for you. A "client" has reported multiple issues.

### Setup

First, check if the broken dashboard exists:

```
Does exercises/05_debug/broken_dashboard.html exist? If not, tell me.
```

If it does not exist, ask Claude to create it:

```
Create exercises/05_debug/broken_dashboard.html -- a social media dashboard that has these 6 intentional bugs:

1. One of the Chart.js chart canvases has a typo in its ID, so the chart does not render
2. A stat card shows "NaN" instead of a formatted number (the value is passed as a string with a comma like "45,200" instead of 45200)
3. The CSS grid for stat cards uses "grid-template-columns: repeat(4, 1f)" -- missing the "r" in "1fr"
4. The footer text colors are swapped -- MARTIVI is cyan and DIGITAL is yellow (should be the opposite)
5. One data table row has its columns in the wrong order (Spend and CTR are swapped)
6. A chart's background colors array has only 3 colors for 5 data points, causing some bars to be invisible on the dark background

Make it otherwise look like a complete, professional dashboard with the dark theme (#191919), stat cards, a data table, a bar chart, and a doughnut chart. Use Montserrat font, MARTIVI DIGITAL footer, and realistic social media data. The bugs should be subtle enough that a developer would need to inspect the code to find them.
```

Also create the bug report:

```
Create exercises/05_debug/README.md with a "Client Bug Report" listing these issues as a client would describe them (not technical):

1. "One of the charts is just a blank space"
2. "One of the stat cards shows NaN instead of a number"
3. "The stat cards are stacked vertically instead of in a row"
4. "The footer colors look wrong -- they seem backwards"
5. "In the data table, the Spend and CTR columns seem mixed up in one row"
6. "Some of the bars in the chart are missing or invisible"
```

### The Debug Process

Open the broken dashboard in your browser:

```
open exercises/05_debug/broken_dashboard.html
```

Confirm the bugs are visible. Then use Claude Code to fix them.

**Strategy:** Do not just say "fix all the bugs." Work through them methodically:

```
Read exercises/05_debug/broken_dashboard.html and identify all the bugs listed in exercises/05_debug/README.md. List each bug, its location in the code, and the fix needed. Do not make changes yet.
```

This makes Claude do a Read-and-analyze pass first. Review its findings. Then:

```
Fix bug 1: the chart canvas ID typo.
```

Continue one by one. Watch how Claude uses Read to locate the bug, then Edit to fix the exact line. This is the surgical debug workflow -- no rewriting the entire file.

After all 6 bugs are fixed, save the result:

```
Copy the fixed version to exercises/05_debug/fixed_dashboard.html so we keep the original broken version for reference.
```

**Speed challenge:** Time the entire debug process. You just found and fixed 6 bugs in ___ minutes. How long would that take with manual inspection and find-replace?

---

## Part 2 -- Responsive Optimization

Go back to your Day 2 client report: `exercises/03_dashboard/client_report.html`.

### Responsive Text with clamp()

Fixed font sizes break at different viewport widths. The `clamp()` function sets a minimum, preferred, and maximum size:

```css
/* Instead of this: */
font-size: 2.5rem;

/* Use this: */
font-size: clamp(1.5rem, 3vw, 2.5rem);
/* Minimum: 1.5rem, scales with viewport, maximum: 2.5rem */
```

Ask Claude to make the conversion:

```
Read exercises/03_dashboard/client_report.html and replace ALL fixed font sizes with responsive clamp() values. Use these guidelines:
- Main headings: clamp(1.8rem, 4vw, 3rem)
- Section headings: clamp(1.3rem, 2.5vw, 2rem)
- Stat card values: clamp(1.5rem, 3vw, 2.5rem)
- Stat card labels: clamp(0.75rem, 1.2vw, 0.9rem)
- Body text: clamp(0.85rem, 1.5vw, 1rem)
- Table text: clamp(0.7rem, 1.2vw, 0.9rem)
- Footer text: clamp(0.7rem, 1vw, 0.85rem)
```

### Responsive Grid

The stats-grid should adapt to screen size:

```
Update the stats-grid in client_report.html to be responsive:
- Desktop (default): 4 columns
- Tablet (max-width: 1024px): 2 columns
- Mobile (max-width: 600px): 1 column

Also make chart containers stack vertically on mobile and ensure tables scroll horizontally on small screens.
```

### Verify

Resize your browser window and check that everything scales smoothly. No text should overflow or become unreadably small.

---

## Part 3 -- Client Feedback Simulation

This is where Claude Code becomes a superpower. In a real workflow, clients send feedback and you need to implement changes fast. Here are 5 client feedback items. Time each one individually.

### Feedback 1: Chart Colors

> "The bar chart colors are too similar -- make them more distinct"

```
In exercises/03_dashboard/client_report.html, update all bar chart color palettes to use more visually distinct colors. Use: #ffc711 (yellow), #3cc5ee (cyan), #ff6b6b (coral), #51cf66 (green), #845ef7 (purple). Make sure every chart uses this palette.
```

Target: under 3 minutes.

### Feedback 2: Comparison Column

> "Add a comparison column to the data table showing last month's values"

```
In the Meta top ads data table in client_report.html, add a "Prev. Month" column after each numeric column showing values approximately 8-12% lower than current values. Style the comparison values in a muted color (#888).
```

Target: under 3 minutes.

### Feedback 3: Title Slide Visual Impact

> "The title slide needs more visual impact -- add a gradient background"

```
Update the title slide in client_report.html to use a diagonal gradient background from #191919 to #262626 with a subtle accent. Add a decorative element -- maybe a thin gradient line or geometric accent using the brand colors #ffc711 and #3cc5ee.
```

Target: under 3 minutes.

### Feedback 4: Client Brand Color

> "Can you add the client's brand colors as an accent? Coffee Brown: #6F4E37"

```
Add a new CSS variable --accent-client: #6F4E37 to client_report.html. Use it as a subtle accent on the title slide (maybe a border or background element) and as an alternate stat card border color. Keep the MARTIVI branding colors for the footer and charts.
```

Target: under 3 minutes.

### Feedback 5: Mobile Footer

> "The footer text is too small on mobile"

```
Update the footer in client_report.html to use clamp() for its font size with a mobile-friendly minimum. Also increase the footer padding on mobile so it does not feel cramped. Add a media query if needed.
```

Target: under 3 minutes.

### Speed Challenge Results

Write down your times:
- Feedback 1: ___ minutes
- Feedback 2: ___ minutes
- Feedback 3: ___ minutes
- Feedback 4: ___ minutes
- Feedback 5: ___ minutes
- **Total: ___ minutes**

You just handled 5 rounds of client feedback in ___ minutes. In a typical workflow without Claude Code, each of these is a 15-30 minute task. That is 1.5-2.5 hours compressed into minutes.

---

## Part 4 -- Git Workflow

Now practice a clean git workflow. This is how you would handle these changes on a real project.

### Create a Branch

```
Create a git branch called "improvements" and switch to it.
```

### Commit Each Change Separately

The point is incremental commits, not one big dump. Ask Claude to help:

```
Stage and commit my changes in logical groups:
1. The debug fixes (exercises/05_debug/) -- message: "day-3: fix 6 bugs in broken dashboard"
2. The responsive optimization -- message: "day-3: add responsive clamp() and grid breakpoints"
3. The client feedback changes -- message: "day-3: implement 5 client feedback items"
```

### Push the Branch

```
Push the improvements branch to GitHub.
```

### Optional: Create a PR

If you want to practice the full workflow:

```
Create a GitHub pull request from improvements to main with a summary of all changes.
```

---

## Verification Checklist

Before you finish Day 3, confirm:

- [ ] `exercises/05_debug/fixed_dashboard.html` exists with all 6 bugs fixed
- [ ] `exercises/03_dashboard/client_report.html` uses clamp() for all font sizes
- [ ] Stats grid is responsive: 4 cols -> 2 cols -> 1 col
- [ ] All 5 client feedback items are implemented
- [ ] Charts use distinct color palette
- [ ] Data table has comparison column
- [ ] Title slide has gradient background
- [ ] Client accent color #6F4E37 is used as a CSS variable
- [ ] Footer is readable on mobile
- [ ] At least 3 separate commits on the improvements branch

---

## What You Accomplished Today

- Debugged a broken dashboard using Claude's Read -> analyze -> Edit workflow
- Made an entire report responsive with clamp() and grid breakpoints
- Handled 5 rounds of client feedback at high speed
- Practiced clean git workflow with branching and incremental commits
- Experienced the Read -> Edit surgical approach (versus rewriting entire files)

**Tomorrow:** You will learn advanced Claude Code features -- MCP servers, hooks, permission modes -- and take the final test.

**Go to [Day 4: Advanced Mastery](DAY_4_ADVANCED.md)**
