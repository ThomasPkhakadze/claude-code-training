# Day 3: Dashboard

**NEW SKILL UNLOCKED: You can build dashboards**

Estimated time: 3-4 hours

---

**What you will start with:** Experience creating styled pages with stat cards.

**What you will end with:** A full client dashboard with a header, stat cards, a data table, and professional layout -- the kind of deliverable agencies send to real clients.

---

## What Is a Dashboard?

A dashboard is a single page that shows someone the most important numbers about their business, all at a glance. Think of it like the instrument panel in a car -- you do not need to open the hood to know your speed, fuel level, and engine temperature. Everything is right there.

Clients want dashboards because they do not have time to dig through spreadsheets. They want to open one page and immediately understand: "Are things going well, or do I need to worry?"

Here is what a typical marketing dashboard contains:

- **Header:** Client name, reporting period, agency logo
- **Stat cards:** The 4-6 most important numbers (reach, impressions, clicks, spend)
- **Tables:** Detailed breakdowns (which ads performed best, which days had the most traffic)
- **Footer:** Agency branding

Today you will build exactly this.

---

## What Is CSS Grid?

Yesterday you put 3 cards in a row. Today you need a more complex layout -- cards, tables, and sections arranged in a specific way. CSS Grid handles this.

Think of CSS Grid like a spreadsheet. You define rows and columns, and then you place things into cells. You might say "I want 4 columns of equal width" and then drop one stat card into each column. Or "I want the table to span the full width below the cards."

You do not need to write any grid code. You just need to tell Claude the layout you want, and it will use CSS Grid behind the scenes. The important thing is knowing the word "grid" so you can use it in your descriptions.

---

## The Data

Before you start building, you need data. In a real project, this would come from Facebook Ads Manager or Google Analytics. For this exercise, here is the data for a fictional client.

First, ask Claude to create the data file:

```
Create exercises/03_dashboard/data.json with this data for "Cafe Batumi" social media metrics for March 2026:

Overall metrics:
- Total Reach: 45,200
- Total Impressions: 89,300
- Total Engagements: 3,400
- Total Spend: $250

Top 5 ads:
1. "Spring Menu Launch" -- Reach: 12,400, Impressions: 24,800, CTR: 3.2%
2. "Coffee of the Week" -- Reach: 9,800, Impressions: 18,600, CTR: 2.8%
3. "Weekend Brunch Special" -- Reach: 8,600, Impressions: 17,200, CTR: 3.5%
4. "Live Jazz Nights" -- Reach: 7,900, Impressions: 15,800, CTR: 2.1%
5. "Loyalty Card Promo" -- Reach: 6,500, Impressions: 12,900, CTR: 4.1%
```

Approve the file creation. This JSON file is now the "source of truth" for your dashboard.

---

## Exercise: Build the Dashboard

Now ask Claude to build the dashboard using this data:

```
Create exercises/03_dashboard/dashboard.html using the data from exercises/03_dashboard/data.json.

This is a client dashboard for "Cafe Batumi" for March 2026.

Layout and design:
- Background: #191919
- Cards: #262626 background
- Font: Montserrat from Google Fonts
- All text: white

Sections:

1. HEADER
   - Title: "Cafe Batumi" in large text
   - Subtitle: "Social Media Report -- March 2026"
   - A thin yellow (#ffc711) line underneath

2. STAT CARDS (4 cards in a row)
   - Reach: 45,200
   - Impressions: 89,300
   - Engagements: 3,400
   - Spend: $250
   - Each card has a #262626 background, yellow left border, large number, smaller label

3. DATA TABLE
   - Title above: "Top Performing Ads"
   - Columns: Ad Name, Reach, Impressions, CTR
   - 5 rows from the data
   - Table has subtle borders, alternating row colors for readability
   - Numbers right-aligned

4. FOOTER
   - "MARTIVI" in yellow (#ffc711) + "DIGITAL" in cyan (#3cc5ee)
   - Small text, centered

Make it look professional. Use CSS Grid for the card layout.
```

Approve the creation. Open it:

```bash
open exercises/03_dashboard/dashboard.html
```

---

## Iterate: Make It Better

Your dashboard is functional, but let us make it shine. Try these improvements one at a time:

**Add visual indicators to stat cards:**
```
Add up arrows (green, pointing up) to the Reach and Engagements stat cards,
and keep the other two neutral. This shows which metrics improved.
```

**Highlight the best ad:**
```
In the data table, highlight the row with the highest CTR
with a subtle yellow background tint.
```

**Add a section header style:**
```
Make "Top Performing Ads" look like a section header with a small
yellow accent bar to the left of it, similar to the card borders.
```

Each improvement teaches Claude more about your taste. Over time, you can include these preferences in your first prompt so the initial result is closer to what you want.

---

## Understanding What You Built

Take a moment to look at your dashboard in the browser. You have:

- A professional header with the client name and period
- Four stat cards showing key metrics at a glance
- A data table with detailed ad performance
- Agency branding in the footer

This is a real deliverable. If you exported this as a PDF or screenshot, it could go in a client email. You built it by having a conversation.

---

## Commit Your Work

```
Commit my work with the message: "day-3: cafe batumi dashboard with stat cards and data table"
```

Then push:

```
Push my changes to GitHub
```

---

## What You Accomplished Today

- Understood what dashboards are and why clients need them
- Created a JSON data file (your first structured data)
- Built a complete dashboard with header, stat cards, table, and footer
- Used CSS Grid for professional layout
- Iterated on the design to add visual indicators and highlights
- Applied agency branding (MARTIVI DIGITAL footer)

**Deliverable:** `exercises/03_dashboard/dashboard.html`

**Tomorrow:** You will add interactive charts to this dashboard -- bar charts, doughnut charts, and line charts that respond when you hover over them.

**Go to [Day 4: Charts](DAY_4_CHARTS.md)**
