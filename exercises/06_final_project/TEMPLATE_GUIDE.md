# TechFlow Report -- Template Guide

> How to reuse this report for any client. Follow these steps to produce a branded performance report without starting from scratch.

---

## 1. Quick Start

1. Copy `report.html` to a new location:
   ```
   cp exercises/06_final_project/report.html exercises/06_final_project/new_client_report.html
   ```
2. Open the new file in your editor or Claude Code.
3. Update the `:root` CSS variables (Section 2).
4. Replace all data values (Section 3).
5. Update the `<title>` tag and title slide content.
6. Review in browser, check print preview.

---

## 2. Color Theming

All colors are controlled by CSS variables in the `:root` block at the top of the `<style>` section.

| Variable | Controls | TechFlow Value |
|----------|----------|----------------|
| `--bg-dark` | Page background | `#191919` |
| `--bg-card` | Card/container backgrounds | `#0A1628` |
| `--bg-card-alt` | Gradient endpoint for chart containers | `#1e1e1e` |
| `--primary` | Main accent: headings, borders, chart color 1 | `#0066FF` |
| `--primary-light` | Secondary accent: alt borders, chart color 2 | `#00AAFF` |
| `--accent-warm` | Tertiary accent: chart color 3, medium-impact cards | `#FF6B35` |
| `--accent-gray` | Stat card value text color | `#F0F4F8` |
| `--success` | Positive indicators (green arrows, success charts) | `#10B981` |
| `--danger` | Negative indicators (red arrows) | `#EF4444` |
| `--text` | Primary body text | `#ffffff` |
| `--text-muted` | Secondary text, labels, chart axis text | `#888888` |
| `--text-dim` | Footer text | `#555555` |
| `--border` | Card borders, table row borders | `#1e2d4a` |
| `--grid-line` | Chart grid lines | `#1a2540` |
| `--agency-yellow` | MARTIVI footer yellow (do not change) | `#ffc711` |
| `--agency-cyan` | MARTIVI footer cyan (do not change) | `#3cc5ee` |

### Example: Swapping to Cafe Batumi branding

```css
:root {
    --bg-dark: #191919;
    --bg-card: #1e1e1e;        /* standard dark card */
    --bg-card-alt: #1e1e1e;
    --primary: #6F4E37;         /* Coffee Brown */
    --primary-light: #A0785A;   /* Lighter brown */
    --accent-warm: #FFFDD0;     /* Cream */
    --accent-gray: #FFFDD0;
    --success: #10B981;
    --danger: #EF4444;
    --text: #ffffff;
    --text-muted: #888888;
    --text-dim: #555555;
    --border: #333333;
    --grid-line: #2a2a2a;
    --agency-yellow: #ffc711;   /* always keep */
    --agency-cyan: #3cc5ee;     /* always keep */
}
```

**Key rule:** `--agency-yellow` and `--agency-cyan` stay the same for every client. They are only used in the MARTIVI DIGITAL footer.

---

## 3. Data Mapping

### Slide 1: Title
- `<h1>` tag -- update client name and `.accent` span
- `.subtitle` -- report type
- `.period` -- report period

### Slide 2: Executive Summary
- 8 `.stat-card` elements -- update `.value` text and `.change` text
- Swap `up`/`down` class on `.change` based on whether the metric improved
- Arrow characters: `&#9650;` (up triangle), `&#9660;` (down triangle)

### Slide 3: Meta Ads
- 4 `.stat-card` elements -- overview metrics (reach, impressions, engagements, spend)
- `<table>` rows -- one row per campaign, update all `<td>` values
- `metaBarChart` JavaScript -- update `labels` array and `data` array (sorted by clicks descending)

### Slide 4: Google Ads
- 4 `.stat-card` elements -- overview metrics
- `<table>` rows -- one row per campaign
- `googleBarChart` JavaScript -- update `labels` and `data` arrays

### Slide 5: Website Analytics
- 4 `.stat-card` elements -- sessions, bounce rate, avg duration, pages/session
- `sessionsLineChart` -- update `months12` labels and `data` array (12 values)
- `trafficDoughnut` -- update `labels` (with percentages) and `data` array (must sum to 100)

### Slide 6: Conversion Funnel
- 4 `.funnel-step` elements -- update `.funnel-value` numbers
- 3 `.funnel-rate` elements -- update conversion percentages
- Overall conversion rate at the bottom

### Slide 7: Monthly Trends
- `trendsChart` -- update `data` arrays for Sessions, Signups, and Paid datasets
- `revenueSpendChart` -- update Revenue and Ad Spend `data` arrays
- `roiChart` -- automatically calculates from `revenue` and `spend` arrays (just update those two)

### Slide 8: Recommendations
- Summary paragraph -- rewrite for the new client
- 5 `.rec-card` elements -- update title, description, `.channel-tag`, and impact level
- Swap `.high`/`.medium` class on cards based on impact

---

## 4. Slide Management

### Adding a slide
1. Copy an existing `<div class="slide">` block.
2. Paste it in the desired position between other slides.
3. Update the slide content.
4. Update all footer `<span>` page numbers (e.g., `5 / 9` becomes `5 / 10`).
5. If the slide has a chart, add a new `<canvas>` with a unique `id` and a corresponding `new Chart(...)` block in the `<script>` section.

### Removing a slide
1. Delete the entire `<div class="slide">...</div>` block.
2. If it contained charts, also delete the corresponding `new Chart(...)` block in `<script>`.
3. Update all footer page numbers.

### Reordering slides
1. Cut the entire `<div class="slide">...</div>` block.
2. Paste it in the new position.
3. Update all footer page numbers.

---

## 5. Chart Customization

All charts use Chart.js and read colors from CSS variables via `getComputedStyle`. This means changing `:root` variables automatically updates chart colors.

### Changing chart type
In the `new Chart(...)` call, change the `type` property:
- `'bar'` -- vertical bars
- `'bar'` with `indexAxis: 'y'` -- horizontal bars
- `'line'` -- line chart
- `'doughnut'` -- doughnut chart
- `'pie'` -- pie chart
- `'radar'` -- radar chart

### Adding a dataset
Inside the `datasets` array, add a new object:
```js
{
    label: 'New Dataset',
    data: [10, 20, 30],
    backgroundColor: primary,
    borderColor: primary,
    // ... other options
}
```

### Removing a dataset
Delete the dataset object from the `datasets` array.

### Changing chart colors
Colors reference the CSS variable values read at the top of the script:
```js
const primary = rs.getPropertyValue('--primary').trim();
```
To use a different variable, swap the reference (e.g., `primary` to `warm`). Or use a hex string directly.

### Adjusting chart options
- **Legend:** `plugins.legend.display` (true/false), `plugins.legend.position` ('top'/'bottom'/'left'/'right')
- **Grid lines:** `scales.x.grid.color` / `scales.y.grid.color`, or `display: false` to hide
- **Axis labels:** `scales.y.ticks.callback` for formatting (e.g., `v => '$' + v`)
- **Dual axes:** Add `yAxisID: 'y1'` to a dataset and define a `y1` scale in options

---

## 6. New Report Checklist

- [ ] Copy `report.html` to new file
- [ ] Update `<title>` tag
- [ ] Update `:root` CSS variables for new client brand
- [ ] Update title slide (client name, period, subtitle)
- [ ] Update executive summary stat cards with new YoY data
- [ ] Update Meta slide (stat cards, table rows, chart data)
- [ ] Update Google slide (stat cards, table rows, chart data)
- [ ] Update website analytics (stat cards, sessions chart, traffic doughnut)
- [ ] Update conversion funnel (values and rates)
- [ ] Update monthly trends (all 3 chart datasets)
- [ ] Rewrite recommendations (summary paragraph + 5 cards)
- [ ] Update all footer slide numbers if slide count changed
- [ ] Open in browser -- verify all charts render
- [ ] Check print preview (Ctrl+P) -- one slide per page
- [ ] Check mobile width -- cards and charts stack properly
- [ ] Verify MARTIVI DIGITAL footer appears on every slide
