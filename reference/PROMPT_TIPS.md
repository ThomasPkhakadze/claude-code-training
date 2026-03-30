# How to Write Good Prompts for Claude Code

The quality of what Claude builds depends on the quality of your instructions. Here's how to get the best results.

---

## The Golden Rule

**Be specific.** The more detail you give, the better the output.

---

## Bad vs Good Prompts

### Example 1: Creating a dashboard

**Bad:**
```
Make me a dashboard
```
Claude will guess everything -- colors, data, layout, style. You'll probably need to redo it.

**Good:**
```
Create a social media dashboard with:
- Dark background (#191919)
- 4 stat cards: Reach (45,200), Impressions (89,300), Engagements (3,400), Spend ($250)
- A data table showing the top 5 ads with columns: Name, Reach, Clicks, CTR
- A bar chart showing reach per ad
- Use Montserrat font, Chart.js for charts
- MARTIVI DIGITAL footer (MARTIVI in #ffc711, DIGITAL in #3cc5ee)
```
Claude knows exactly what to build. First try will be close to what you want.

### Example 2: Making changes

**Bad:**
```
Make it look better
```

**Good:**
```
Change three things:
1. Make the stat card numbers bigger (32px)
2. Add a yellow left border to each card
3. Put a subtle shadow on the chart containers
```

### Example 3: Fixing something

**Bad:**
```
The chart is broken
```

**Good:**
```
The bar chart on the dashboard isn't showing. I see a blank space where it should be. The canvas element exists but no chart renders. Can you check the Chart.js code?
```

---

## Five Prompt Patterns

### 1. The Context Dump (One-Shot)

Give Claude ALL the information upfront:

```
Create exercises/03_dashboard/dashboard.html

Data:
- Client: Cafe Batumi
- Period: March 2026
- Reach: 45,200 | Impressions: 89,300 | Engagements: 3,400 | Spend: $250

Layout:
- Dark theme (#191919 background, #262626 cards)
- 4 stat cards in a row
- Data table below
- Bar chart at the bottom

Style:
- Montserrat font
- Yellow accent (#ffc711)
- Cyan accent (#3cc5ee)
- MARTIVI DIGITAL footer
```

**Best for:** When you know exactly what you want.

### 2. The Iterative Build

Start broad, then refine:

```
Step 1: "Create the basic HTML structure with a title and 4 empty stat cards"
Step 2: "Fill in the stat cards with this data: Reach 45K, Impressions 89K..."
Step 3: "Add a data table below the cards"
Step 4: "Add a bar chart using Chart.js"
Step 5: "Polish the styling -- add shadows, spacing, footer"
```

**Best for:** Complex pages where you want to review each step.

### 3. The Reference Pattern

Point to something that already exists:

```
Look at reference/sample_dashboard.html. Create a similar dashboard but with this data: [your data]
```

**Best for:** When you have an example you want to match.

### 4. The Revision Pattern

Ask for specific changes:

```
In the dashboard, change these 3 things:
1. [Specific change 1]
2. [Specific change 2]
3. [Specific change 3]
```

**Best for:** When you're close but need adjustments.

### 5. The Exploration Pattern

When you're not sure what you want:

```
I need a landing page for a smart thermostat product. Show me 3 different approaches for the hero section -- describe them before building.
```

**Best for:** Early-stage design decisions.

---

## Tips for Better Results

1. **Include numbers** -- Don't say "some data", say "Reach: 45,200"
2. **Include colors** -- Don't say "dark theme", say "#191919 background"
3. **Include sizes** -- Don't say "big text", say "32px heading"
4. **Include layout** -- "4 cards in a row", "chart below the table"
5. **One thing at a time** -- If you're getting confused, break it into smaller requests
6. **Review the diff** -- When Claude shows you what it changed, actually read it before pressing `y`
7. **Say "don't change X"** -- If you like something, tell Claude to keep it: "Update the charts but don't change the stat cards"

---

## When Claude Gets It Wrong

It happens. Here's what to do:

- **Press `n`** to reject the change, then explain what was wrong
- **Be specific about the fix:** "The chart colors should be yellow (#ffc711), not blue"
- **Start over if needed:** `/clear` then give a better prompt
- **Use `/compact`** if the conversation is too long and Claude is confused

---

*Remember: Claude Code is a collaboration. You direct, Claude builds. The clearer your direction, the better the result.*
