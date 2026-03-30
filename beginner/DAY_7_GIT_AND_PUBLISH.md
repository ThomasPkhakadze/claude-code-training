# Day 7: Git and Publish

**NEW SKILL UNLOCKED: You can ship your work to the world**

Estimated time: 2-3 hours (plus final test time)

---

**What you will start with:** A week of work saved locally and pushed to GitHub through Claude.

**What you will end with:** A solid understanding of git, the ability to manage your own save history, and the confidence to move on to the final test.

---

## Review: Your Week in Seven Skills

Before diving into git, take a moment to appreciate how far you have come:

| Day | What You Learned | What You Built |
|-----|------------------|----------------|
| 1 | Create web pages through conversation | `exercises/01_hello_world/index.html` |
| 2 | Style pages with fonts, colors, and layouts | `exercises/02_html_page/profile.html` |
| 3 | Build dashboards with stat cards and tables | `exercises/03_dashboard/dashboard.html` |
| 4 | Add interactive charts (bar, doughnut, line) | Updated dashboard with 3 charts |
| 5 | Create multi-slide presentations | `exercises/04_landing_page/presentation.html` |
| 6 | Write prompts that get great results first try | `exercises/04_landing_page/landing_page.html` + prompt log |
| 7 | Today: manage your work with git | Practice commits + final test prep |

A week ago, you had never created a web page. Now you can build professional dashboards with charts and multi-slide presentations. That is real progress.

---

## Git Deep Dive

All week you have been asking Claude to "commit my work" and "push to GitHub." Today you will understand what those commands actually do.

### What Is Git?

Git is a version control system. Think of it like **save points in a video game**. Every time you reach a milestone, you create a save point. If something goes wrong later, you can go back to any previous save point.

Without git, your only option is "undo" -- and that only goes back so far. With git, you can jump back to the exact state of your project from any point in its history.

### The Four Commands You Need

There are only four git commands you need to know. Everything else is advanced, and Claude can handle it for you.

#### 1. git status -- "What changed since my last save?"

```bash
git status
```

This shows you:
- **Modified files:** Files that exist but have been changed since the last commit
- **Untracked files:** New files that git does not know about yet
- **Staged files:** Files that are ready to be committed (saved)

Think of it as checking your inventory before saving the game. "What do I have? What is new? What is different?"

#### 2. git add -- "Pick which changes to save"

```bash
git add exercises/04_landing_page/landing_page.html
```

This "stages" a file -- marks it as ready to be saved. You can add specific files by name, or add everything:

```bash
git add .
```

The `.` means "everything in the current folder." Use this when you want to save all your changes at once.

Think of it as putting items in a box before sealing it. You choose what goes in.

#### 3. git commit -- "Save with a description"

```bash
git commit -m "day-6: prompt engineering exercises and landing page"
```

This creates the save point. The `-m` flag lets you attach a message describing what you did. Good messages help you (and others) understand the history later.

Think of it as sealing the box and writing a label on it.

#### 4. git push -- "Upload to GitHub"

```bash
git push
```

This sends your saved commits to GitHub, a website that stores your code in the cloud. Once pushed, your work is backed up online. Even if your computer breaks, your code is safe.

Think of it as mailing the labeled box to a warehouse for safekeeping.

### Bonus: git log -- "See my history"

```bash
git log --oneline
```

This shows your commit history -- every save point you have created, with its message. You will see all the commits from this week.

---

## Practice: The Git Workflow

Let us practice the full workflow. Start Claude Code:

```bash
cd claude-code-training
claude
```

**Step 1:** Ask Claude to make a small change to any exercise file. For example:

```
In exercises/01_hello_world/index.html, add a line at the bottom
that says "Updated on Day 7 of training"
```

**Step 2:** Now, instead of asking Claude to commit for you, do it yourself. Open a separate terminal window (keep Claude running in the other one) and run:

```bash
git status
```

You should see `exercises/01_hello_world/index.html` listed as modified.

**Step 3:** Stage the file:

```bash
git add exercises/01_hello_world/index.html
```

**Step 4:** Commit with a message:

```bash
git commit -m "day-7: practiced manual git commit"
```

**Step 5:** Push to GitHub:

```bash
git push
```

**Step 6:** Check your history:

```bash
git log --oneline
```

You should see your new commit at the top, along with all the commits from the previous days.

---

## See Your Work on GitHub

Open your browser and go to your GitHub repository. You can find it at:

```
https://github.com/YOUR-USERNAME/claude-code-training
```

Replace `YOUR-USERNAME` with your actual GitHub username. You will see all your files, all your commits, and the full history of your training. Click on the "commits" link to see every save point you created this week.

This is your portfolio of work. Anyone with the link can see what you built.

---

## When Things Go Wrong

Git can feel intimidating when something unexpected happens. Here are the two most common situations and what to do:

**"I made a change but I do not want to keep it"**

Ask Claude:
```
Undo the changes to exercises/01_hello_world/index.html (revert to the last commit)
```

Claude will handle the git command for you.

**"I committed something by mistake"**

Ask Claude:
```
I want to undo my last commit but keep the files changed
```

Claude will use the right git command to undo the commit without losing your work.

The key insight: as long as you have committed your work, you can always get back to it. Git is your safety net.

---

## Preparing for the Final Test

Tomorrow -- or right now, if you have the energy -- you will take the final test. Here is what to expect:

- You will receive a **client brief** for Cafe Batumi
- You will receive **data** in a JSON file
- You will receive **brand guidelines**
- Your job: build a complete 5-slide monthly performance report
- You will use everything you learned this week: stat cards, tables, charts, multi-slide layout, agency branding

The test is open-book. You can look back at your previous exercises. You can use Claude Code. The point is not to test your memory -- it is to test whether you can take a real brief and deliver a professional result.

**When you are ready, proceed to the final test.**

---

## What You Accomplished Today

- Understood what git is and why it matters (save points for your code)
- Learned the four essential git commands: status, add, commit, push
- Practiced the git workflow manually (not through Claude)
- Viewed your commit history
- Saw your work on GitHub
- Prepared for the final test

**Next: [Final Test](FINAL_TEST.md)**
