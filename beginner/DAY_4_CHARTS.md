# Day 4: Charts

**NEW SKILL UNLOCKED: You can visualize data with charts**

Estimated time: 3-4 hours

---

**What you will start with:** A dashboard with stat cards and a data table.

**What you will end with:** The same dashboard, now with three interactive charts -- bar, doughnut, and line -- that respond to hover and bring data to life.

---

## What Is Chart.js?

Chart.js is a JavaScript library that draws charts inside a web page. When you include it in your HTML file, you get access to bar charts, line charts, pie charts, doughnut charts, and more -- all interactive, all animated.

Here is how it works at a high level:

1. You add a `<script>` tag that loads Chart.js from the internet (a CDN)
2. You create a `<canvas>` element in your HTML -- this is the blank space where the chart will appear
3. JavaScript code tells Chart.js what type of chart to draw, what data to use, and what colors to apply

**You do not need to understand any of this code.** Claude handles all the technical details. Your job is to describe what chart you want, what data it should show, and what colors to use. Claude writes the code. You approve it and see the result.

Think of it like ordering food at a restaurant: you tell the waiter what you want, and the kitchen prepares it. You do not need to know how to cook.

---

## Exercise: Add Charts to Your Dashboard

Today you will add three charts to the dashboard you built yesterday. Start Claude Code:

```bash
cd claude-code-training
claude
```

### Chart 1: Bar Chart -- Top Ads by Reach

```
Add a bar chart to exercises/03_dashboard/dashboard.html.

Chart title: "Top 5 Ads by Reach"
Type: horizontal bar chart
Data (from our data.json):
- Spring Menu Launch: 12,400
- Coffee of the Week: 9,800
- Weekend Brunch Special: 8,600
- Live Jazz Nights: 7,900
- Loyalty Card Promo: 6,500

Style:
- Bar color: #ffc711 (yellow)
- Background: transparent (so the dark page shows through)
- Labels: white text
- Grid lines: subtle, dark gray

Put it in a container with #262626 background, some padding,
and a title above the chart. Place it below the data table.

Use Chart.js from CDN.
```

Approve, refresh your browser. You should see a horizontal bar chart with yellow bars. Hover over a bar -- you will see the exact value pop up. That is Chart.js interactivity, and it came for free.

### Chart 2: Doughnut Chart -- Spend by Platform

```
Add a doughnut chart to the dashboard.

Chart title: "Spend by Platform"
Type: doughnut chart
Data:
- Meta Ads: $180
- Google Ads: $70

Colors:
- Meta: #ffc711 (yellow)
- Google: #3cc5ee (cyan)

Style:
- Legend: white text, below the chart
- Background: transparent

Put it in a #262626 container, same style as the bar chart container.
Place the bar chart and doughnut chart side by side (two columns).
```

Now you have two charts sitting next to each other. The doughnut chart shows the spend split between platforms. Hover over each section to see the values.

### Chart 3: Line Chart -- Monthly Engagement Trend

```
Add a line chart to the dashboard.

Chart title: "Monthly Engagement Trend"
Type: line chart
Data (6 months):
- October 2025: 1,800
- November 2025: 2,100
- December 2025: 2,500
- January 2026: 2,900
- February 2026: 3,100
- March 2026: 3,400

Style:
- Line color: #3cc5ee (cyan)
- Fill below the line with a subtle transparent cyan
- Point dots: white
- Grid lines: subtle dark gray
- Labels: white

Put it in a full-width #262626 container below the two charts.
```

Approve and refresh. You now have a line chart showing upward growth over 6 months. The filled area underneath creates a visual sense of progress.

---

## See the Full Picture

Open your dashboard in the browser and scroll through it. You now have:

1. A header with the client name and period
2. Four stat cards with key metrics
3. A data table with top ads
4. A bar chart showing reach by ad
5. A doughnut chart showing spend split
6. A line chart showing engagement trend over time
7. MARTIVI DIGITAL footer

This is a professional marketing dashboard. The charts make the data come alive in a way that tables alone cannot. When a client sees a line going up and to the right, they feel good about their investment. That visual impact is why charts matter.

---

## Experiment with Your Charts

Try asking Claude to make adjustments:

```
Make the bar chart sorted from highest to lowest (it might already be)
```

```
Add the actual numbers at the end of each bar in the bar chart
```

```
Change the doughnut chart to show percentages in the legend
```

```
Add dots at each data point on the line chart, and make the line thicker
```

```
Make the charts responsive so they look good on smaller screens too
```

Each of these is a real refinement you might make on a client project. Practice describing what you want and seeing Claude deliver it.

---

## Commit Your Work

```
Commit my work with the message: "day-4: added bar, doughnut, and line charts to dashboard"
```

Then push:

```
Push my changes to GitHub
```

---

## What You Accomplished Today

- Learned what Chart.js is and how Claude uses it to create charts
- Added a horizontal bar chart showing ad performance
- Added a doughnut chart showing platform spend split
- Added a line chart showing 6-month engagement trend
- All charts are interactive (hover to see values)
- All charts use agency brand colors
- Practiced iterating on chart styling and layout

**Deliverable:** Updated `exercises/03_dashboard/dashboard.html` (now with 3 charts)

**Tomorrow:** You will learn how to build multi-slide presentations -- full-screen pages you scroll through, each one telling part of the story.

**Go to [Day 5: Presentations](DAY_5_PRESENTATIONS.md)**
