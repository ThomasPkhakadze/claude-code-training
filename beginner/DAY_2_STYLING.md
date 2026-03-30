# Day 2: Styling

**NEW SKILL UNLOCKED: You can style like a designer**

Estimated time: 2-3 hours

---

**What you will start with:** A plain web page with basic text on a dark background.

**What you will end with:** A polished profile page with professional fonts, colored stat cards, and a layout that looks like it was made by a designer.

---

## Quick Recap of Day 1

Yesterday you created your first web page by talking to Claude Code. You learned that Claude can create and edit real files on your computer, and that it always asks for permission before doing anything. You opened the page in your browser and made changes through conversation.

Today you will take that same approach and learn how to make things look professional.

---

## What Is CSS?

Every web page has two layers:

- **HTML** is the structure -- headings, paragraphs, images, sections. Think of it as the skeleton of a body.
- **CSS** is the style -- colors, fonts, spacing, borders, layout. Think of it as the clothing, makeup, and accessories.

When you asked Claude yesterday to make the background dark or the text white, Claude was writing CSS for you. Today you will ask for more sophisticated styling, and Claude will handle the CSS. You do not need to memorize any CSS rules -- you just need to describe what you want things to look like.

---

## What Are Google Fonts?

Your computer has a few default fonts (Arial, Times New Roman, etc.). They work, but they look generic. Google Fonts is a free library of hundreds of professional fonts that any web page can use.

The font we use at the agency is called **Montserrat**. It is clean, modern, and works well for both headings and body text. When you ask Claude to use Montserrat, it will add a line to your HTML that loads the font from Google -- no installation needed.

---

## What Are Stat Cards?

A "stat card" is a small box that highlights a single number. You see them everywhere on dashboards and reports. Each card typically has:

- A large number (like "45,200" or "97%")
- A label underneath (like "Total Reach" or "Satisfaction Rate")
- A background color or accent that makes it stand out

Imagine three small rectangles sitting side by side, each with a bold number and a caption. That is what you are building today.

---

## Exercise: Build Your Profile Page

Start Claude Code in your training folder:

```bash
cd claude-code-training
claude
```

Then ask Claude to create your profile page. Here is a prompt you can use -- feel free to personalize it:

```
Create exercises/02_html_page/profile.html with the following:

Background: #191919 (dark)
Font: Montserrat from Google Fonts
All text: white

Header section:
- My name "UJMA" in large bold text
- Subtitle: "Training Participant" in lighter/smaller text

Below the header, show 3 stat cards in a row:
- Card 1: "24" with label "Age" (or whatever number you like)
- Card 2: "1" with label "Years in Tech"
- Card 3: "3" with label "Coffees per Day"

Each card should have:
- Background color: #262626
- A yellow (#ffc711) left border (about 4px wide)
- White text
- The number should be large and bold
- The label should be smaller and slightly gray
- Some padding inside and spacing between cards
```

Approve the file creation when Claude shows it to you. Then open it in your browser:

```bash
open exercises/02_html_page/profile.html
```

---

## Iterate on Your Design

Now that you have a base, try asking Claude to adjust things. Here are some ideas:

```
Add more space between the cards
```

```
Make the numbers even bigger
```

```
Add a subtle shadow to each card
```

```
Put a horizontal line between the header and the cards
```

```
Change the yellow border to cyan (#3cc5ee) on the middle card
```

Each time, approve the change, refresh your browser, and see the result. This is the design workflow: describe, approve, see, refine.

---

## Learn to Read the Diff

When Claude edits a file, it shows you a "diff" -- a before-and-after view of what changed. Lines that are being removed show in red. Lines being added show in green.

You do not need to understand every line of code. But start noticing patterns:

- When you ask to change a color, look for the old color value being replaced by the new one
- When you ask for more spacing, look for numbers getting bigger (like `16px` becoming `32px`)
- When you ask for a new section, look for a block of new green lines being added

Over time, reading diffs will become second nature. For now, just glance at them to make sure they look reasonable before approving.

---

## Commit Your Work

When you are happy with your profile page, save your progress:

```
Commit my work with the message: "day-2: styled profile page with stat cards"
```

Then push:

```
Push my changes to GitHub
```

---

## What You Accomplished Today

- Learned what CSS does (styling and visual design)
- Used Google Fonts (Montserrat) to make text look professional
- Built stat cards -- a pattern you will use in every dashboard
- Practiced iterating on design through conversation
- Started reading diffs to understand what Claude changes

**Deliverable:** `exercises/02_html_page/profile.html`

**Tomorrow:** You will build your first real dashboard with client data, tables, and a professional layout.

**Go to [Day 3: Dashboard](DAY_3_DASHBOARD.md)**
