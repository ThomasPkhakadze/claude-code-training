# Day 2: Dashboard Sprint

**NEW SKILL UNLOCKED: Production dashboards at 10x speed**

Estimated time: 4-5 hours

---

**What you will start with:** The one-shot dashboard from Day 1 and knowledge of Claude Code's tools.

**What you will end with:** A complete 6-slide social media report for a client, with stat cards, data tables, and multiple chart types -- built at a speed that would be impossible by hand.

---

## The Agency Dashboard Pattern

Before you build, understand the pattern. Every client report we produce at MARTIVI DIGITAL follows this structure. Once you know it, you can produce reports for any client by swapping data and colors.

### HTML Structure

Each "slide" is a full-viewport section:

```html
<section class="slide" id="slide-1">
  <!-- Slide content -->
  <div class="footer">
    <span class="footer-brand">MARTIVI</span>
    <span class="footer-digital">DIGITAL</span>
    <span class="slide-number">1 / 6</span>
  </div>
</section>
```

Every slide uses `min-height: 100vh` so it fills the screen. When printed, each slide becomes one page.

### CSS Pattern

All colors live in `:root` variables. This is non-negotiable -- it makes theming instant:

```css
:root {
  --bg-dark: #191919;
  --bg-card: #262626;
  --bg-card-alt: #1e1e1e;
  --primary: #ffc711;
  --secondary: #3cc5ee;
  --text: #ffffff;
  --text-muted: #888888;
  --border: #333333;
}
```

Stat cards use a left border accent and sit in a 4-column grid:

```css
.stats-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
}

.stat-card {
  background: var(--bg-card);
  border-left: 4px solid var(--primary);
  border-radius: 12px;
  padding: 1.5rem;
}
```

Charts live in containers with controlled dimensions:

```css
.chart-container {
  background: var(--bg-card);
  border-radius: 12px;
  padding: 1.5rem;
  max-height: 400px;
}
```

### Chart.js Pattern

Every chart follows this structure:

```html
<div class="chart-container">
  <canvas id="chartName"></canvas>
</div>

<script>
new Chart(document.getElementById('chartName'), {
  type: 'bar',  // or 'doughnut', 'line', 'horizontalBar', 'pie'
  data: {
    labels: [...],
    datasets: [{
      data: [...],
      backgroundColor: ['#ffc711', '#3cc5ee', '#ff6b6b', '#51cf66', '#845ef7']
    }]
  },
  options: {
    responsive: true,
    plugins: {
      legend: { labels: { color: '#ffffff' } }
    },
    scales: {
      x: { ticks: { color: '#888' }, grid: { color: '#333' } },
      y: { ticks: { color: '#888' }, grid: { color: '#333' } }
    }
  }
});
</script>
```

### The Reference

Before you start building, look at the reference file:

```
Ask Claude: Read reference/sample_dashboard.html and summarize its structure.
```

If the reference file exists, study it. If not, the patterns above are your reference.

---

## The Data

Your dashboard will use data from `exercises/03_dashboard/data.json`. Before you start, ask Claude to check if this file exists:

```
Does exercises/03_dashboard/data.json exist? If not, create it with this data:
```

If it does not exist, provide Claude with this data to create it:

```json
{
  "client": "Cafe Batumi",
  "period": "February 2026",
  "meta": {
    "overview": {
      "reach": 52300,
      "impressions": 118400,
      "engagements": 4870,
      "spend": 320
    },
    "top_ads": [
      {"name": "Spring Menu Launch", "impressions": 34200, "clicks": 1240, "ctr": "3.6%", "spend": 85},
      {"name": "Weekend Brunch Special", "impressions": 28100, "clicks": 980, "ctr": "3.5%", "spend": 72},
      {"name": "Coffee Loyalty Card", "impressions": 22500, "clicks": 870, "ctr": "3.9%", "spend": 58},
      {"name": "Valentine's Dinner", "impressions": 19800, "clicks": 650, "ctr": "3.3%", "spend": 62},
      {"name": "Live Music Friday", "impressions": 13800, "clicks": 420, "ctr": "3.0%", "spend": 43}
    ]
  },
  "google": {
    "overview": {
      "impressions": 67200,
      "clicks": 3150,
      "ctr": "4.7%",
      "spend": 480
    },
    "campaigns": [
      {"name": "Brand Search", "impressions": 22400, "clicks": 1340, "ctr": "6.0%", "spend": 156},
      {"name": "Menu Keywords", "impressions": 18900, "clicks": 890, "ctr": "4.7%", "spend": 132},
      {"name": "Local Discovery", "impressions": 14200, "clicks": 560, "ctr": "3.9%", "spend": 98},
      {"name": "Competitor Terms", "impressions": 11700, "clicks": 360, "ctr": "3.1%", "spend": 94}
    ]
  },
  "monthly_trends": {
    "months": ["Sep", "Oct", "Nov", "Dec", "Jan", "Feb"],
    "reach": [38200, 41500, 44800, 48100, 50200, 52300],
    "impressions": [82000, 91000, 98000, 105000, 112000, 118400],
    "spend": [240, 260, 280, 290, 310, 320],
    "engagements": [3200, 3500, 3800, 4100, 4500, 4870]
  },
  "recommendations": [
    {
      "title": "Scale Spring Menu Campaign",
      "description": "The Spring Menu Launch ad has the highest impressions and strong CTR. Increase budget by 20% to capitalize on seasonal interest.",
      "priority": "high"
    },
    {
      "title": "Optimize Competitor Terms",
      "description": "Google competitor terms campaign has the lowest CTR at 3.1%. Refine keyword targeting and ad copy to improve relevance.",
      "priority": "medium"
    },
    {
      "title": "Launch Retargeting Campaign",
      "description": "With 4,870 engagements this month, there is a strong audience to retarget. Set up a Meta retargeting campaign for website visitors.",
      "priority": "high"
    },
    {
      "title": "Test Video Content",
      "description": "Video ads typically see 2-3x higher engagement in food and beverage. Create a short-form video ad for the next campaign cycle.",
      "priority": "medium"
    }
  ]
}
```

---

## The Exercise: Build the Complete Report

Now build it. You have the pattern, the data, and the tools. Ask Claude to build `exercises/03_dashboard/client_report.html` with these 6 slides:

### Slide 1: Title Slide

- Client name: "Cafe Batumi"
- Report period: "February 2026"
- Subtitle: "Monthly Social Media Performance Report"
- MARTIVI DIGITAL branding
- Styled background -- gradient, pattern, or visual treatment that sets it apart from the data slides

### Slide 2: Meta Overview

- 4 stat cards: Reach, Impressions, Engagements, Spend (from data.json meta.overview)
- Data table of top 5 ads (from data.json meta.top_ads): Name, Impressions, Clicks, CTR, Spend
- Bar chart: impressions by ad name

### Slide 3: Google Overview

- 4 stat cards: Impressions, Clicks, CTR, Spend (from data.json google.overview)
- Bar chart or horizontal bar chart: clicks by campaign
- Styled consistently with Slide 2

### Slide 4: Ad Performance Comparison

- Horizontal bar chart comparing all ads (both Meta and Google) by impressions
- Clear visual distinction between Meta ads and Google campaigns (different color groups)

### Slide 5: Monthly Trends

- Line chart with 6 months of data (from data.json monthly_trends)
- Multiple datasets on one chart: Reach, Impressions, Engagements
- Second chart or dual-axis for Spend trend

### Slide 6: Summary and Recommendations

- Styled recommendation cards (from data.json recommendations)
- Each card shows title, description, and priority level
- High priority gets a yellow accent, medium gets cyan
- Overall summary paragraph

### Requirements

- **CSS variables for ALL colors** -- someone should be able to retheme the entire report by editing the `:root` block
- **Print-friendly:** Add `@media print` rules with `page-break-after: always` on each slide
- **MARTIVI DIGITAL footer** on every slide with slide numbers (e.g., "1 / 6")
- **All data from data.json** -- do not make up numbers. Tell Claude to use the exact values from the JSON file.
- **Self-contained HTML** -- inline CSS, inline JS, CDN links only

### How to Prompt This

You can do this as one large prompt or break it into slides. Here is the recommended approach for your first time:

**Option A -- The one-shot (advanced):**
Give Claude the entire specification above in a single prompt, referencing the data.json file.

**Option B -- Slide by slide (recommended for learning):**
1. "Create exercises/03_dashboard/client_report.html with the base structure: HTML boilerplate, CSS variables, Montserrat font, dark background, and the first slide (title slide). Read exercises/03_dashboard/data.json for the client details."
2. "Add Slide 2: Meta Overview with stat cards, data table, and bar chart. Use the meta data from data.json."
3. Continue for each slide.

Either approach works. Option B lets you inspect each slide as it is built.

---

## Speed Challenge

Time yourself from the moment you send your first prompt to the moment all 6 slides are complete and displaying correctly in the browser.

**Target: under 45 minutes for all 6 slides.**

If you hit that, you just built a complete client report in the time it would take to set up the CSS grid by hand.

**Speed challenge reflection:** You just built that in ___ minutes. How long would it take by hand? For most developers, a 6-slide dashboard with 4 charts, data tables, and responsive design takes 4-6 hours of manual work.

---

## Verification

Open the file in your browser and check:

```
open exercises/03_dashboard/client_report.html
```

- [ ] All 6 slides render and fill the viewport
- [ ] Stat cards show correct data from data.json
- [ ] All charts render with correct data
- [ ] Data tables are populated with the right values
- [ ] Footer appears on every slide with slide numbers
- [ ] Colors use CSS variables (inspect the `:root` block)
- [ ] Print preview shows one slide per page (Cmd+P to check)

If anything is off, tell Claude what needs fixing. Watch how it uses Read -> identifies the issue -> Edit to fix it surgically.

---

## Commit Your Work

```
Commit my work with the message: "day-2: build cafe batumi 6-slide client report"
```

Then push:

```
Push my changes to GitHub
```

---

## What You Accomplished Today

- Learned the agency dashboard pattern (slides, CSS variables, stat cards, Chart.js)
- Built a complete 6-slide client report with real data
- Used Chart.js for bar charts, horizontal bar charts, line charts, and potentially doughnut charts
- Made the report print-friendly
- Experienced the speed difference between AI-assisted and manual development

**Tomorrow:** You will debug a broken dashboard, make your report responsive, and handle rapid client feedback -- all through Claude Code.

**Go to [Day 3: Debug and Optimize](DAY_3_DEBUG_AND_OPTIMIZE.md)**
