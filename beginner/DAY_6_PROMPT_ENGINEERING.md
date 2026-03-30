# Day 6: Prompt Engineering

**NEW SKILL UNLOCKED: You can craft expert prompts**

Estimated time: 2-3 hours

---

**What you will start with:** The ability to ask Claude Code to build things, sometimes getting good results on the first try, sometimes needing several rounds of revision.

**What you will end with:** A clear understanding of what makes a prompt effective, plus a documented log of your own prompt experiments that you can reference for future projects.

---

## The Most Important Skill

Everything you have done this week -- pages, dashboards, charts, presentations -- was driven by the prompts you gave Claude. The quality of your output is directly connected to the quality of your prompts.

A vague prompt is like telling a taxi driver "take me somewhere nice." You might end up somewhere great, or somewhere irrelevant. A specific prompt is like giving the address, the route, and saying "avoid the highway."

Today you will learn the difference, practice both, and build a reference log of what works.

---

## Vague vs Specific: Side by Side

Here are two prompts asking for the same thing. Read both and notice the difference.

**Vague prompt:**
```
Make me a dashboard
```

What Claude might do: pick random data, choose its own colors, guess at the layout, use default fonts. The result might be decent, but it will not match what you had in mind. You will spend time iterating to fix things that a better prompt would have avoided.

**Specific prompt:**
```
Create a dashboard for "Cafe Batumi" social media report, March 2026.

Data:
- Reach: 45,200
- Impressions: 89,300
- Engagements: 3,400
- Spend: $250

Design:
- Background: #191919
- Card background: #262626
- Yellow accent: #ffc711
- Cyan accent: #3cc5ee
- Font: Montserrat from Google Fonts
- All text white

Layout:
- Header with client name and period
- 4 stat cards in a row
- Data table with top 5 ads below
- MARTIVI DIGITAL footer (MARTIVI in yellow, DIGITAL in cyan)
```

What Claude will do: build exactly what you described. First try. Minimal iteration needed.

**The lesson:** Specificity is not about writing more words. It is about removing ambiguity. Every detail you include is one less decision Claude has to guess about.

---

## The Five Elements of a Good Prompt

When you write a prompt for Claude Code, try to include these elements:

### 1. The File
Where should the output go? Always include the file path.
```
Create exercises/04_landing_page/landing_page.html
```

### 2. The Context
What is this for? Who is the audience?
```
This is a product landing page for a coffee subscription service.
```

### 3. The Structure
What sections should it have? In what order?
```
Sections:
1. Hero banner with product image description and tagline
2. Three feature cards (freshly roasted, delivered monthly, cancel anytime)
3. Pricing section with two tiers
4. Call to action button
```

### 4. The Design
What should it look like? Colors, fonts, spacing.
```
Design:
- Dark theme (#191919 background)
- Montserrat font
- Yellow (#ffc711) accent on headings and buttons
- Cards: #262626 with subtle border
```

### 5. The Data
What specific content should appear? Do not leave this to Claude's imagination.
```
Pricing:
- Basic: $19/month, 2 bags, free shipping
- Premium: $34/month, 4 bags, free shipping, exclusive blends
```

Not every prompt needs all five elements. A quick change like "make the heading bigger" only needs one. But for building something new, the more elements you include, the better your first result will be.

---

## Slash Commands

Claude Code has built-in commands that start with `/`. These are tools for managing your session:

| Command | What it does | When to use it |
|---------|-------------|----------------|
| `/help` | Shows all available commands | When you forget what commands exist |
| `/clear` | Clears the conversation history | When the conversation gets confusing or Claude starts referencing old context that no longer applies |
| `/compact` | Compresses the conversation to save memory | When you have been working for a long time and Claude starts forgetting things from earlier in the conversation |
| `/cost` | Shows how much the current session has cost | When you are curious about usage |
| `/exit` | Closes Claude Code | When you are done for the day |

### When to Use /clear vs /compact

**/clear** is a fresh start. Use it when you are switching to a completely different task and the old conversation would just confuse things.

**/compact** keeps the important parts of your conversation but compresses the details. Use it when you have been working on the same thing for a while and the conversation is getting long. Claude will remember the key decisions but forget the back-and-forth.

---

## Keyboard Shortcuts

These work inside Claude Code:

| Shortcut | What it does |
|----------|-------------|
| `Escape` | Cancels the current generation (if Claude is writing something and you realize you asked the wrong thing) |
| `Up arrow` | Recalls your previous message (so you can edit and resend it) |
| `! command` | Runs a shell command directly (example: `! open index.html` opens the file in your browser) |

The `!` shortcut is particularly useful. Instead of asking Claude to open a file and waiting for it to generate a response, you can just type:

```
! open exercises/04_landing_page/presentation.html
```

And it runs immediately.

---

## Exercise: The Prompt Experiment

This exercise has two parts. You will build the same thing twice -- once with a vague prompt, once with a specific prompt -- and compare the results.

### Part 1: The Vague Attempt

Start Claude Code:

```bash
cd claude-code-training
claude
```

Give Claude this intentionally vague prompt:

```
Create exercises/04_landing_page/landing_page.html -- make it a landing page for a coffee shop
```

Approve the file, open it in your browser, and take a mental note of the result. What did Claude choose for colors? Layout? Content? Fonts?

### Part 2: The Specific Attempt

Now clear the conversation and try again with a detailed prompt:

```
/clear
```

Then:

```
Create exercises/04_landing_page/landing_page.html -- a landing page for
"Batumi Beans" premium coffee subscription service.

DESIGN:
- Background: #191919
- Cards/sections: #262626
- Accent yellow: #ffc711
- Accent cyan: #3cc5ee
- Font: Montserrat from Google Fonts
- All text: white, except labels which are #aaaaaa

SECTIONS (top to bottom):

1. HERO
   - Full-width section with extra vertical padding
   - Large heading: "Premium Coffee, Delivered"
   - Subheading: "Freshly roasted beans from Batumi's finest farms, at your door every month"
   - Yellow call-to-action button: "Start Your Subscription"

2. FEATURES (3 cards in a row)
   - Card 1: "Freshly Roasted" -- "Every batch roasted within 48 hours of shipping"
   - Card 2: "Delivered Monthly" -- "Set it and forget it. Fresh coffee on the 1st of every month"
   - Card 3: "Cancel Anytime" -- "No contracts, no commitments. Pause or cancel with one click"
   - Each card: #262626 background, yellow top border, icon or emoji at top

3. PRICING (2 tiers side by side)
   - Basic: $19/month -- 2 bags, free shipping, roast preference
   - Premium: $34/month -- 4 bags, free shipping, exclusive blends, early access
   - Premium card should be slightly larger or highlighted with a yellow border
   - Each tier has a "Subscribe" button

4. FOOTER
   - "MARTIVI" in yellow + "DIGITAL" in cyan
   - Centered, small text
```

Approve the file (it will overwrite the vague version), open it, and compare.

### Part 3: Iterate on the Good Version

Now refine the specific version with 3 targeted changes:

```
1. Add a subtle background gradient to the hero section (from #191919 to #1a1a2e)
2. Make the pricing cards have a hover effect -- slight lift and brighter border
3. Add customer review quotes between the features and pricing sections:
   - "Best coffee subscription I've tried" -- Maria K.
   - "The Premium blend is incredible" -- Dato S.
```

### Part 4: Document What You Learned

Ask Claude to create a prompt log:

```
Create exercises/04_landing_page/PROMPT_LOG.md with a document comparing
my two approaches today.

Include:
- The vague prompt I used and what it produced (describe the result)
- The specific prompt I used and what it produced
- What was different between the two results
- My 3 iteration prompts and how they improved the page
- 3-5 lessons I learned about writing good prompts

Write it from my perspective as a training participant.
```

---

## Commit Your Work

```
Commit my work with the message: "day-6: prompt engineering exercises and landing page"
```

Then push:

```
Push my changes to GitHub
```

---

## What You Accomplished Today

- Understood the difference between vague and specific prompts
- Learned the five elements of a good prompt (file, context, structure, design, data)
- Practiced slash commands (/help, /clear, /compact, /cost, /exit)
- Learned keyboard shortcuts (Escape, Up arrow, ! command)
- Built the same page twice and compared the results
- Documented your prompt engineering lessons in a log

**Deliverables:**
- `exercises/04_landing_page/landing_page.html`
- `exercises/04_landing_page/PROMPT_LOG.md`

**Tomorrow:** You will learn git in depth and prepare for the final test -- building a complete client report from scratch.

**Go to [Day 7: Git and Publish](DAY_7_GIT_AND_PUBLISH.md)**
