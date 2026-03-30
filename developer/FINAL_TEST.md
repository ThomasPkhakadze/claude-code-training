# Final Test: Production Report + Reusable Template

**THE FINAL CHALLENGE**

Estimated time: 3-4 hours

---

## Scenario

A new SaaS client, **TechFlow**, needs their February 2026 performance report. TechFlow is a project management tool for remote teams. They have been running Meta and Google ad campaigns, driving traffic to their website, and converting visitors into trial users and paid subscribers.

But this is not just about building one report. You also need to create documentation so that any team member -- including someone who has never used Claude Code -- can produce the same quality of report for a different client. This tests both your building speed and your ability to systematize.

---

## Provided Materials

Before you start, verify these files exist. If they do not, you will need to create them.

### Client Brief

Check for `exercises/06_final_project/brief_developer.md`. If it does not exist, ask Claude:

```
Create exercises/06_final_project/brief_developer.md with this content:
```

```markdown
# TechFlow -- February 2026 Performance Report Brief

## About TechFlow
TechFlow is a SaaS project management tool for remote teams. Founded in 2024, they are in growth mode -- focused on user acquisition through paid ads and organic content. Their target audience is tech startup founders and remote team managers.

## Report Requirements
- 8+ slides covering all digital marketing channels
- Executive summary with year-over-year comparisons
- Meta and Google ad breakdowns with charts
- Website analytics (sessions, bounce rate, traffic sources)
- Conversion funnel visualization
- 12-month trend data
- Actionable recommendations

## Tone
Professional but forward-looking. TechFlow is a tech company -- they appreciate clean data presentation and clear insights over decorative design.

## Delivery
Self-contained HTML file. Must be print-friendly (one slide per page). Must use CSS variables so we can adapt branding for other clients.
```

### Data

Check for `exercises/06_final_project/data_developer.json`. If it does not exist, ask Claude:

```
Create exercises/06_final_project/data_developer.json with this content:
```

```json
{
  "client": "TechFlow",
  "period": "February 2026",
  "yoy_period": "February 2025",
  "executive_summary": {
    "total_spend": 4250,
    "total_spend_yoy": 3100,
    "total_leads": 892,
    "total_leads_yoy": 614,
    "cost_per_lead": 4.76,
    "cost_per_lead_yoy": 5.05,
    "revenue_attributed": 28400,
    "revenue_attributed_yoy": 18200
  },
  "meta": {
    "overview": {
      "impressions": 245000,
      "reach": 128000,
      "clicks": 8940,
      "spend": 2100,
      "ctr": "3.65%",
      "cpc": 0.24
    },
    "campaigns": [
      {"name": "Remote Work Solutions", "impressions": 82000, "clicks": 3200, "ctr": "3.9%", "spend": 720, "conversions": 186},
      {"name": "Free Trial Promo", "impressions": 68000, "clicks": 2840, "ctr": "4.2%", "spend": 580, "conversions": 210},
      {"name": "Case Study - Startup X", "impressions": 45000, "clicks": 1560, "ctr": "3.5%", "spend": 380, "conversions": 94},
      {"name": "Product Feature Highlight", "impressions": 32000, "clicks": 890, "ctr": "2.8%", "spend": 260, "conversions": 62},
      {"name": "Retargeting - Site Visitors", "impressions": 18000, "clicks": 450, "ctr": "2.5%", "spend": 160, "conversions": 88}
    ]
  },
  "google": {
    "overview": {
      "impressions": 184000,
      "clicks": 12600,
      "spend": 2150,
      "ctr": "6.85%",
      "cpc": 0.17,
      "conversions": 520
    },
    "campaigns": [
      {"name": "Brand Search", "impressions": 52000, "clicks": 4800, "ctr": "9.2%", "spend": 620, "conversions": 198},
      {"name": "Project Management Tools", "impressions": 48000, "clicks": 3200, "ctr": "6.7%", "spend": 540, "conversions": 142},
      {"name": "Remote Team Software", "impressions": 38000, "clicks": 2400, "ctr": "6.3%", "spend": 420, "conversions": 96},
      {"name": "Competitor Comparison", "impressions": 28000, "clicks": 1400, "ctr": "5.0%", "spend": 340, "conversions": 52},
      {"name": "Display Remarketing", "impressions": 18000, "clicks": 800, "ctr": "4.4%", "spend": 230, "conversions": 32}
    ]
  },
  "website": {
    "sessions": 34200,
    "sessions_yoy": 22800,
    "bounce_rate": 38.2,
    "bounce_rate_yoy": 44.6,
    "avg_session_duration": "3:42",
    "pages_per_session": 4.1,
    "traffic_sources": {
      "organic": 32,
      "paid_search": 28,
      "paid_social": 22,
      "direct": 12,
      "referral": 6
    },
    "monthly_sessions": {
      "months": ["Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec", "Jan", "Feb"],
      "values": [14200, 16800, 18400, 19200, 20100, 22400, 24800, 26200, 28400, 30100, 32000, 34200]
    }
  },
  "funnel": {
    "website_visits": 34200,
    "signups": 2840,
    "trial_starts": 1420,
    "active_trials": 892,
    "paid_conversions": 312
  },
  "monthly_trends": {
    "months": ["Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec", "Jan", "Feb"],
    "spend": [2200, 2400, 2600, 2800, 3000, 3100, 3200, 3400, 3600, 3800, 4000, 4250],
    "leads": [380, 420, 460, 510, 540, 580, 620, 680, 740, 790, 840, 892],
    "revenue": [12000, 13500, 15200, 16800, 18000, 19600, 21000, 22800, 24200, 25800, 27200, 28400],
    "cpl": [5.79, 5.71, 5.65, 5.49, 5.56, 5.34, 5.16, 5.00, 4.86, 4.81, 4.76, 4.76]
  },
  "recommendations": [
    {
      "title": "Double Down on Free Trial Campaign",
      "description": "The Free Trial Promo has the highest CTR (4.2%) and best conversion rate on Meta. Increase budget by 30% and test new creative variations.",
      "impact": "high",
      "channel": "Meta"
    },
    {
      "title": "Expand Brand Search Budget",
      "description": "Brand search converts at 9.2% CTR with the lowest CPC. There is likely untapped search volume -- increase budget to capture all branded queries.",
      "impact": "high",
      "channel": "Google"
    },
    {
      "title": "Optimize Competitor Comparison Campaigns",
      "description": "CTR is 5.0% but conversion cost is high relative to other campaigns. Review keyword targeting and landing page relevance.",
      "impact": "medium",
      "channel": "Google"
    },
    {
      "title": "Reduce Bounce Rate Further",
      "description": "Bounce rate improved from 44.6% to 38.2% YoY. Continue A/B testing landing pages, especially for paid traffic sources where first impressions are critical.",
      "impact": "medium",
      "channel": "Website"
    },
    {
      "title": "Improve Trial-to-Paid Conversion",
      "description": "Only 22% of active trials convert to paid. Implement an in-app onboarding sequence and targeted email nurture for trial users in week 2.",
      "impact": "high",
      "channel": "Product"
    }
  ]
}
```

### Brand Kit

Check for `exercises/06_final_project/brand_kits.md`. If it does not exist, ask Claude:

```
Create exercises/06_final_project/brand_kits.md with this content:
```

```markdown
# Client Brand Kits

## TechFlow

| Property | Value |
|----------|-------|
| Primary Color | #6C5CE7 (Purple) |
| Secondary Color | #00CEC9 (Teal) |
| Accent Color | #FD79A8 (Pink) |
| Dark Background | #1A1A2E |
| Card Background | #16213E |
| Text Color | #EAEAEA |
| Font | Inter (Google Fonts) |
| Logo Style | Minimal, geometric |

### Usage Notes
- Primary purple for headings and key metrics
- Teal for secondary data points and chart accents
- Pink for call-to-action elements and highlights
- Keep the dark, modern aesthetic -- TechFlow's audience is tech-savvy

## Agency Default (MARTIVI DIGITAL)

| Property | Value |
|----------|-------|
| Primary Color | #ffc711 (Yellow) |
| Secondary Color | #3cc5ee (Cyan) |
| Dark Background | #191919 |
| Card Background | #262626 |
| Text Color | #ffffff |
| Font | Montserrat (Google Fonts) |
```

---

## Part 1 -- Build the Report

Create `exercises/06_final_project/report.html` with **8 or more slides.**

### Required Slides

**Slide 1: Title**
- TechFlow branding (purple/teal palette from brand_kits.md)
- Client name, report period, subtitle
- Agency attribution (MARTIVI DIGITAL in footer)
- Visual treatment that reflects TechFlow's tech aesthetic

**Slide 2: Executive Summary**
- Key metrics with year-over-year comparison
- Each metric shows current value, previous value, and a directional arrow
- Green up-arrow for improvements, red down-arrow for declines
- Calculate and show the percentage change for each metric

**Slide 3: Meta Ad Performance**
- 4-6 stat cards from meta.overview
- Data table of all Meta campaigns with all available columns
- Bar chart: conversions by campaign
- Use the TechFlow color palette for chart colors

**Slide 4: Google Campaign Performance**
- 4-6 stat cards from google.overview
- Data table of all Google campaigns
- Horizontal bar chart: clicks by campaign
- Consistent styling with Slide 3

**Slide 5: Website Analytics**
- Sessions trend line chart (12 months from website.monthly_sessions)
- Bounce rate visualization (doughnut or gauge showing 38.2%)
- Traffic sources doughnut chart (from website.traffic_sources)
- Key website metrics as stat cards (sessions, bounce rate, avg duration, pages/session)

**Slide 6: Conversion Funnel**
- Funnel visualization showing the progression: Website Visits -> Signups -> Trial Starts -> Active Trials -> Paid Conversions
- Show the count at each stage and the conversion rate between stages
- This should be a visual funnel -- narrowing bars, a stepped diagram, or similar

**Slide 7: Monthly Trends**
- Multi-dataset line chart showing 12 months of data
- Include at least: Spend, Leads, and Revenue
- Use a secondary axis or separate chart for Cost Per Lead (different scale)
- Clear legends, gridlines, readable axis labels

**Slide 8: Recommendations**
- 5 action item cards from the recommendations data
- Each card shows: title, description, impact level (high/medium), and channel
- High impact cards get a prominent accent (purple or pink), medium gets a subtler treatment
- Overall summary paragraph at the top

### Technical Requirements

- **CSS variables for the ENTIRE color scheme.** Someone must be able to change the brand from TechFlow to another client by editing 4-5 variables in `:root`.
- **Responsive text with clamp()** on all font sizes -- headings, stat values, labels, body, table text, footer
- **Print-friendly:** `@media print` with `page-break-after: always` on each slide
- **All data from data_developer.json** -- no made-up numbers
- **At least 4 different chart types** (e.g., bar, horizontal bar, line, doughnut)
- **Professional quality** -- if you showed this to a real client, they would be impressed
- **Self-contained HTML** -- single file, inline CSS/JS, CDN links for fonts and Chart.js

### How to Build It

Use whichever prompt pattern you found most effective on Day 4. If you prefer one-shot, load the entire spec. If you prefer iterative, go slide by slide.

One effective approach:

```
Read exercises/06_final_project/data_developer.json and exercises/06_final_project/brand_kits.md. Then create exercises/06_final_project/report.html -- an 8-slide performance report for TechFlow.

Use the TechFlow brand colors from brand_kits.md as CSS variables. All data must come from data_developer.json. Include these slides: [list the 8 slides with brief descriptions].

Requirements: CSS variables for theming, clamp() for all font sizes, @media print rules, Chart.js for all charts (at least 4 types), MARTIVI DIGITAL footer on every slide, self-contained HTML.
```

**Important:** Commit incrementally as you build. Do not wait until the end.

---

## Part 2 -- Template Guide

After the report is complete, create `exercises/06_final_project/TEMPLATE_GUIDE.md`.

This document should enable any developer on the team to produce a report for a new client without starting from scratch. Include:

### Section 1: Quick Start
- How to copy the report and start customizing for a new client
- What to rename and where

### Section 2: Color Theming
- List every CSS variable in `:root` and what it controls
- Step-by-step: how to swap from TechFlow's palette to a new client's brand colors
- Example: what the `:root` block would look like for a hypothetical client

### Section 3: Data Mapping
- Which sections of the HTML correspond to which sections of the JSON data
- For each slide: where to update the data (which JavaScript variable, which table rows, which chart datasets)
- Format expectations: what shape the data should be in

### Section 4: Slide Management
- How to add a new slide
- How to remove a slide
- How to reorder slides
- How to update slide numbers in the footer

### Section 5: Chart Customization
- How to change chart types (e.g., bar to horizontal bar)
- How to add or remove datasets from a chart
- How to change chart colors
- How to adjust chart options (legend, gridlines, axis labels)

### Section 6: New Report Checklist
A step-by-step checklist for creating a report for a new client:
- [ ] Copy report.html to new location
- [ ] Update CSS variables for new brand
- [ ] Replace all data values from new client's JSON
- [ ] Update client name on title slide
- [ ] Update report period
- [ ] Review all charts render correctly
- [ ] Check print preview
- [ ] Verify footer on all slides

---

## Rules

### Commit Incrementally

You must have **at least 4 commits** showing incremental progress. Not one giant commit at the end.

Suggested commit points:
1. After creating the data files and brief (if they did not exist)
2. After completing the first 4 slides
3. After completing all 8 slides
4. After creating the TEMPLATE_GUIDE.md

**Commit message format:** `day-4: description`

Examples:
- `day-4: scaffold TechFlow report with title and executive summary`
- `day-4: add meta, google, and website analytics slides`
- `day-4: add funnel, trends, and recommendations slides`
- `day-4: create template guide for report reuse`

### Push to GitHub

After each commit, push your work:

```
Push my changes to GitHub
```

---

## Success Criteria

Before you declare this done, verify every item:

- [ ] `exercises/06_final_project/report.html` exists
- [ ] Report has 8 or more slides
- [ ] CSS variables control the entire color scheme (test by changing one variable)
- [ ] All font sizes use `clamp()` for responsive scaling
- [ ] `@media print` rules exist with page breaks between slides
- [ ] At least 4 different Chart.js chart types are used
- [ ] All data matches `data_developer.json` (no invented numbers)
- [ ] MARTIVI DIGITAL footer on every slide with slide numbers
- [ ] YoY comparison arrows on executive summary (green up, red down)
- [ ] Funnel visualization clearly shows conversion stages
- [ ] `exercises/06_final_project/TEMPLATE_GUIDE.md` exists and is thorough
- [ ] Template guide covers: color theming, data mapping, slide management, chart customization
- [ ] 4 or more commits with `day-4:` prefix
- [ ] All commits pushed to GitHub
- [ ] Report looks professional when opened in a browser

Open the report one final time:

```
open exercises/06_final_project/report.html
```

Check every slide. Check print preview (Cmd+P). Check at mobile width. If it passes, you are done.

---

## Congratulations

You have completed the Developer Track.

### What You Learned

**Day 1 -- Power Features:**
You learned Claude Code's 6 core tools (Read, Write, Edit, Bash, Glob, Grep), the agentic loop, CLAUDE.md as project-level AI configuration, the permission system, slash commands, and keyboard shortcuts. You built a complete dashboard from a single prompt.

**Day 2 -- Dashboard Sprint:**
You learned the agency dashboard pattern -- slides, CSS variables, stat cards, Chart.js -- and built a 6-slide client report with multiple chart types, data tables, and print-friendly layout. You experienced the speed: 45 minutes for what would take 4-6 hours by hand.

**Day 3 -- Debug and Optimize:**
You debugged a broken dashboard using Claude's Read/Edit surgical workflow, made an entire report responsive with clamp() and grid breakpoints, and handled 5 rounds of client feedback in minutes. You practiced clean git workflow with branching and incremental commits.

**Day 4 -- Advanced Mastery:**
You learned MCP servers, hooks, and permission modes. You mastered prompt engineering patterns -- one-shot, iterative, reference, and pipe. You compared approaches and found your preferred workflow.

**Final Test:**
You built a production-quality 8-slide report for TechFlow with 4+ chart types, responsive design, print styles, and CSS variable theming. You documented the entire system in a reusable template guide so any team member can produce the same quality of output.

### What You Can Do Now

- Build production client dashboards 10x faster than writing HTML by hand
- Debug and iterate on code through conversation instead of manual find-and-fix
- Handle rapid client feedback in minutes, not hours
- Set up CLAUDE.md to configure Claude for any project
- Choose the right prompt pattern for any task
- Create reusable systems that scale beyond a single developer

### What Comes Next

- Set up CLAUDE.md (`/init`) for your actual work projects
- Explore MCP servers for GitHub, Slack, or database integrations
- Try hooks to automate linting and formatting
- Use Auto Mode for rapid iteration on trusted codebases
- Build templates that your team can reuse across clients

You came in knowing how to code. You leave knowing how to code with an agent that reads your project, plans its approach, acts on your behalf, and iterates until the work is done.

That is a different kind of development.
