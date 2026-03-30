# Final Test: Build a Client Report

**THE FINAL CHALLENGE: Build a Client Report**

Estimated time: 2-3 hours

---

## The Scenario

Giorgi has assigned you a real task. A new client, **Cafe Batumi**, needs their March 2026 social media performance report. You have the data, the brand guidelines, and the agency standards. Your job is to build the report from scratch.

This is the kind of deliverable the agency sends to clients every month. It needs to look professional, contain accurate data, and follow the agency brand.

---

## What You Have Been Given

Before you start building, read through these three files. They contain everything you need.

### 1. Client Brief

File: `exercises/06_final_project/brief_beginner.md`

This describes what the client expects and what the report should cover. Read it carefully.

If this file does not exist yet, ask Claude to create it with the following content:

```
Create exercises/06_final_project/brief_beginner.md with this content:

# Cafe Batumi -- March 2026 Monthly Report Brief

## Client
Cafe Batumi -- a popular cafe and restaurant in Batumi, Georgia.

## Report Period
March 2026

## What the Client Wants
A monthly social media performance report covering:
- Overall performance metrics (reach, impressions, engagements, spend)
- Meta (Facebook/Instagram) ad performance breakdown
- Google Ads performance breakdown
- Monthly trend showing 6 months of progression
- Summary with key takeaways and recommendations

## Delivery Format
Single HTML file with multiple slides (full-screen scrollable sections).
Must be viewable in any browser without additional software.

## Notes
- Client appreciates visual data (charts over tables)
- Client wants to see month-over-month growth
- Keep language professional but accessible
```

### 2. Data

File: `exercises/06_final_project/data_beginner.json`

This contains all the numbers for the report. Every stat card, every chart, every table should pull from this data.

If this file does not exist yet, ask Claude to create it:

```
Create exercises/06_final_project/data_beginner.json with this data:

{
  "client": "Cafe Batumi",
  "period": "March 2026",

  "meta_performance": {
    "reach": 45200,
    "impressions": 89300,
    "engagements": 3400,
    "spend": 180
  },

  "google_performance": {
    "clicks": 2800,
    "impressions": 34500,
    "ctr": 8.1,
    "spend": 70
  },

  "meta_top_ads": [
    {"name": "Spring Menu Launch", "reach": 12400, "impressions": 24800, "ctr": 3.2},
    {"name": "Coffee of the Week", "reach": 9800, "impressions": 18600, "ctr": 2.8},
    {"name": "Weekend Brunch Special", "reach": 8600, "impressions": 17200, "ctr": 3.5},
    {"name": "Live Jazz Nights", "reach": 7900, "impressions": 15800, "ctr": 2.1},
    {"name": "Loyalty Card Promo", "reach": 6500, "impressions": 12900, "ctr": 4.1}
  ],

  "google_top_campaigns": [
    {"name": "Batumi Cafe Near Me", "clicks": 980, "impressions": 11200, "ctr": 8.7},
    {"name": "Best Brunch Batumi", "clicks": 740, "impressions": 8900, "ctr": 8.3},
    {"name": "Coffee Delivery Batumi", "clicks": 620, "impressions": 7400, "ctr": 8.4},
    {"name": "Live Music Restaurant", "clicks": 460, "impressions": 7000, "ctr": 6.6}
  ],

  "monthly_trend": {
    "months": ["Oct 2025", "Nov 2025", "Dec 2025", "Jan 2026", "Feb 2026", "Mar 2026"],
    "reach": [28400, 31200, 35800, 38900, 42100, 45200],
    "engagements": [1800, 2100, 2500, 2900, 3100, 3400],
    "spend": [180, 200, 220, 230, 240, 250]
  }
}
```

### 3. Brand Kit

File: `exercises/06_final_project/brand_kits.md`

If this file does not exist yet, ask Claude to create it:

```
Create exercises/06_final_project/brand_kits.md with:

# Brand Kits

## Cafe Batumi
- Primary color: #2D6A4F (forest green)
- Secondary color: #95D5B2 (light green)
- Accent: #FFD166 (warm yellow)
- Dark background: use agency standard #191919
- Font: use agency standard Montserrat

## Agency Standards (MARTIVI DIGITAL)
- Dark background: #191919
- Card background: #262626
- Yellow accent: #ffc711
- Cyan accent: #3cc5ee
- Font: Montserrat (Google Fonts)
- Charts: Chart.js CDN
- Footer on every slide: "MARTIVI" in yellow (#ffc711) + "DIGITAL" in cyan (#3cc5ee)
```

---

## Requirements

Build a file at **`exercises/06_final_project/report.html`** with the following five slides.

### Slide 1 -- Title

- Client name: "Cafe Batumi"
- Report period: "Monthly Performance Report -- March 2026"
- MARTIVI DIGITAL branding (MARTIVI in yellow, DIGITAL in cyan)
- Clean, centered, professional title slide

### Slide 2 -- Meta Performance

- Section title: "Meta Performance"
- 4 stat cards: Reach (45,200), Impressions (89,300), Engagements (3,400), Spend ($180)
- Data table: Top 5 Meta ads with columns Ad Name, Reach, Impressions, CTR
- 1 bar chart: "Top Ads by Reach" (horizontal bars)
- MARTIVI DIGITAL footer

### Slide 3 -- Google Performance

- Section title: "Google Ads Performance"
- 4 stat cards: Clicks (2,800), Impressions (34,500), CTR (8.1%), Spend ($70)
- 1 chart of your choice showing the Google campaigns data (bar chart, or another type)
- MARTIVI DIGITAL footer

### Slide 4 -- Monthly Trend

- Section title: "6-Month Growth Trend"
- Line chart showing reach over the 6-month period
- Line chart or combined chart showing engagements over the same period
- You may combine them in one chart (dual axis) or use two separate charts
- MARTIVI DIGITAL footer

### Slide 5 -- Summary

- Section title: "Key Takeaways"
- 3-4 takeaway cards with insights drawn from the data, for example:
  - Month-over-month reach growth percentage
  - Best performing Meta ad
  - Google Ads CTR performance
  - A recommendation for next month
- Each card should be styled (not just plain text)
- MARTIVI DIGITAL footer

### Design Requirements

- Use CSS variables for all colors
- Montserrat font from Google Fonts
- Chart.js from CDN for all charts
- Dark theme (#191919 background, #262626 cards)
- Agency yellow (#ffc711) and cyan (#3cc5ee) as accent colors
- Each slide is full viewport height (min-height: 100vh)
- MARTIVI DIGITAL footer on every slide

---

## Success Criteria

Every item on this checklist must be satisfied:

- [ ] File exists at `exercises/06_final_project/report.html`
- [ ] All 5 slides are present and each fills the viewport
- [ ] Data matches `data_beginner.json` (numbers are accurate)
- [ ] At least 3 different chart types are used (bar, line, plus one more)
- [ ] Professional appearance -- no broken layouts, no overlapping elements
- [ ] MARTIVI DIGITAL footer appears on every slide
- [ ] Committed with message: `day-7: final test - cafe batumi monthly report`
- [ ] Pushed to GitHub
- [ ] Progress file updated

---

## Time Guide

- **Reading the brief and data:** 15 minutes
- **Building the report with Claude:** 60-90 minutes
- **Iterating and polishing:** 30-45 minutes
- **Committing and pushing:** 10 minutes

Total: approximately 2-3 hours.

---

## How to Approach This

1. **Start by reading the data file.** Ask Claude to show you the data so you understand what numbers are available.

2. **Build one slide at a time.** Do not try to create all 5 slides in one prompt. Start with Slide 1, verify it looks good, then move to Slide 2, and so on.

3. **Or build all at once with a detailed prompt.** If you feel confident from Day 6's prompt engineering lesson, write one comprehensive prompt that describes all 5 slides. This is faster but requires a good prompt.

4. **Check your work.** Open the file in your browser after each major change. Scroll through all slides. Make sure charts render, numbers are correct, and nothing looks broken.

5. **Polish at the end.** Once all 5 slides are working, do a final pass for consistency: spacing, font sizes, footer positioning, chart sizing.

---

## Commit and Submit

When you are satisfied with your report:

```
Commit all my changes with the message: "day-7: final test - cafe batumi monthly report"
```

Then push:

```
Push my changes to GitHub
```

Then notify Giorgi that your final test is ready for review. You can do this by sending a message or email saying:

> "My beginner track final test is complete and pushed to GitHub. The report is at exercises/06_final_project/report.html. Ready for review."

---

## Congratulations

You did it. In seven days, you went from zero to building professional client reports. Here is everything you learned:

| Day | Skill |
|-----|-------|
| 1 | Creating web pages by talking to Claude Code |
| 2 | Applying professional styling: fonts, colors, layouts, stat cards |
| 3 | Building data dashboards with tables and structured layouts |
| 4 | Visualizing data with interactive Chart.js charts |
| 5 | Creating multi-slide scrollable presentations |
| 6 | Writing prompts that get great results on the first try |
| 7 | Managing your work with git and publishing to GitHub |

You can now:
- Take a client brief and turn it into a professional HTML report
- Use stat cards, data tables, and charts to present data clearly
- Apply consistent branding and dark-themed design
- Write specific prompts that minimize back-and-forth
- Save your work with git and share it through GitHub

These are real, usable skills. The next track will build on this foundation with more advanced techniques.

**Well done. Your training journey continues.**
