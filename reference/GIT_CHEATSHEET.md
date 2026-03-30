# Git Cheatsheet

You only need 5 commands. Here they are.

---

## The 5 Commands

### 1. Check what changed

```bash
git status
```

Shows which files you've created or modified since your last commit. Red = not staged. Green = staged (ready to commit).

### 2. Stage your work

```bash
git add exercises/
```

Tells git "I want to save these changes." You can also add specific files:

```bash
git add exercises/03_dashboard/dashboard.html
```

Or add everything:

```bash
git add .
```

### 3. Save a checkpoint

```bash
git commit -m "day-3: build social media dashboard with charts"
```

Creates a save point with a description. Use the format: `day-X: brief description`

### 4. Upload to GitHub

```bash
git push origin main
```

Sends your commits to GitHub so your supervisor can see your progress.

### 5. View your history

```bash
git log --oneline -10
```

Shows your last 10 commits. Each line is a save point you can return to.

---

## The Daily Workflow

After completing an exercise:

```bash
git status                                           # 1. See what changed
git add exercises/03_dashboard/                      # 2. Stage the exercise folder
git commit -m "day-3: build dashboard with charts"   # 3. Save with a message
git push origin main                                 # 4. Upload to GitHub
```

That's it. Four commands, every time.

---

## Commit Message Format

Always use: `day-X: brief description`

**Good examples:**
```
day-1: create hello world page
day-2: build styled profile page with stat cards
day-3: build social media dashboard with data table
day-4: add bar and doughnut charts to dashboard
day-5: create 4-slide presentation
day-6: build landing page with iterative prompting
day-7: final test - cafe batumi monthly report
```

**Bad examples:**
```
update                    # Too vague
fixed stuff               # What stuff?
aslkdjf                   # Not a message
day 3                     # What did you do on day 3?
```

---

## Common Situations

### "I forgot to add a file"

```bash
git add exercises/the_file_i_forgot.html
git commit -m "day-3: add missing file"
git push origin main
```

### "I want to see what I changed"

```bash
git diff                  # See uncommitted changes
git diff --staged         # See staged changes (after git add)
```

### "I want to undo my last change" (before committing)

```bash
git checkout -- exercises/03_dashboard/dashboard.html
```

This reverts the file to the last committed version. Be careful -- your changes will be lost.

---

## Don't Worry About

- Branches (for now)
- Merge conflicts
- Rebasing
- Tags
- Anything not in this cheatsheet

You'll learn more advanced git later. For this training, the 5 commands above are all you need.

---

*Tip: If something goes wrong with git, ask Claude Code for help: "I accidentally committed the wrong file, how do I fix it?"*
