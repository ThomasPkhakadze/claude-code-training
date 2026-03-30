# Day 1: Power Features

**NEW SKILL UNLOCKED: Claude Code's full toolkit**

Estimated time: 3-4 hours

---

**What you will start with:** A training repo and your usual development workflow.

**What you will end with:** A deep understanding of Claude Code's tool system, a complete dashboard built from a single prompt, and notes on how the agentic loop works under the hood.

---

## The Tool Model

Claude Code is not a chatbot. It is an agent with access to six core tools. Every action Claude takes -- every file it reads, every edit it makes, every command it runs -- goes through one of these tools. Understanding them is the foundation.

| Tool | What It Does | When Claude Uses It |
|------|-------------|---------------------|
| **Read** | Reads file contents from disk | Examining source code, checking configs, reviewing data files |
| **Write** | Creates new files or completely rewrites existing ones | Scaffolding new files, generating entire HTML pages |
| **Edit** | Makes targeted string replacements in existing files | Fixing bugs, updating values, surgical changes |
| **Bash** | Executes shell commands | Running git, checking directory structure, opening files |
| **Glob** | Finds files by pattern (like `**/*.html`) | Discovering project structure, finding specific file types |
| **Grep** | Searches file contents by regex | Finding where a function is used, locating a CSS class, searching for patterns |

**Key insight:** Claude does not just generate text. It operates on your filesystem. When you ask it to "fix the chart colors," it will Read the file, identify the problem, and Edit the specific lines -- not dump the entire file back at you.

---

## The Agentic Loop

This is what makes Claude Code different from copy-pasting into ChatGPT.

When you give Claude a task, it does not just respond with text. It enters a loop:

```
1. READ CONTEXT    -- Reads relevant files, checks project structure
2. PLAN            -- Decides what needs to happen
3. ACT             -- Writes, edits, or runs commands
4. VERIFY          -- Reads the result, checks for errors
5. ITERATE         -- If something is wrong, goes back to step 1
```

A single prompt can trigger 5, 10, even 20+ tool calls as Claude chains actions together. This is the "agentic" part -- it does not stop after one action. It keeps going until the task is done.

Watch for this in the exercises below. When you ask Claude to build a dashboard, count how many tool calls it makes. You will see it chain Glob (find files) -> Read (check existing code) -> Write (create the file) -> possibly Read again (verify what it wrote).

---

## CLAUDE.md -- The Most Powerful Feature

Open your terminal, navigate to the training repo, and start Claude Code:

```bash
cd claude-code-training
claude
```

Now ask:

```
Read the CLAUDE.md file in this repo and tell me what it configures.
```

Claude will read it and explain. Here is what matters:

**CLAUDE.md is project-specific AI configuration.** It lives in your repo root and tells Claude:
- How to communicate (tone, language)
- What brand standards to follow (colors, fonts, patterns)
- What file structure to use
- What NOT to do (constraints, boundaries)
- How to handle commits and progress tracking

This is not a README for humans. It is an instruction file for Claude. Every project you work on should have one.

**Why this matters:** Without CLAUDE.md, you have to re-explain your brand colors, coding conventions, and project structure every session. With it, Claude reads it automatically at the start of every conversation and behaves accordingly.

You can create a CLAUDE.md for any project using `/init` (covered below).

---

## The Permission System

Every tool call requires your approval. This is by design.

When Claude wants to create a file, you see the content and a prompt:

```
Create file: exercises/01_hello_world/index.html
[content preview]
Allow? [y/n]
```

**Three modes you should know:**

| Mode | How It Works | When to Use |
|------|-------------|-------------|
| **Default** | Asks before every action | When learning, when working on unfamiliar code |
| **Allowlist** | Auto-approves specific tools you whitelist | When you trust the operations (e.g., allow Read and Glob) |
| **Auto** | Auto-approves safe operations | When you are iterating fast on trusted work |

**Shift+Tab** cycles between permission modes during a session. Start in default mode for today.

**The rule:** Always review diffs before approving writes and edits. This is your safety net. Read what Claude is about to do, just like you review a PR.

---

## Slash Commands Deep Dive

These are commands you type directly in Claude Code (not shell commands). They control the session.

| Command | What It Does | When to Use |
|---------|-------------|-------------|
| `/help` | Shows all available commands | When you forget a command |
| `/clear` | Clears conversation history, starts fresh | When you want a clean slate |
| `/compact` | Summarizes conversation to free up context window | When Claude starts forgetting earlier context |
| `/cost` | Shows token usage and cost for the session | To monitor usage |
| `/model` | Shows or switches the current model | To check which model you are using |
| `/doctor` | Diagnoses installation and configuration issues | When something is not working |
| `/status` | Shows current session status | Quick health check |
| `/init` | Scaffolds a new CLAUDE.md for the current project | When starting a new project |

**The two you will use most:** `/compact` (when context fills up during long sessions) and `/clear` (when you want to start a new task from scratch).

Try each one now. Type them into Claude Code and see what happens. `/cost` and `/status` are informational and safe to run anytime.

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| **Escape** | Cancel the current generation |
| **Up Arrow** | Scroll through prompt history |
| **Shift+Tab** | Cycle permission modes |
| **Ctrl+C** | Exit Claude Code |

**Bonus -- the `!` prefix:** Typing `!ls` or `!git status` in Claude Code runs the shell command directly without Claude interpreting it. Useful for quick checks without waiting for Claude to process.

---

## Exercise 1: Explore the Training Repo Through Claude

Do not open any files manually. Use Claude Code exclusively.

Ask Claude these questions, one at a time:

```
Show me the file structure of this training repo.
```

```
Find all JSON files in this repo.
```

```
What does the CLAUDE.md say about brand colors?
```

```
Search for any reference to Chart.js across all files.
```

```
What exercise folders exist and are any of them empty?
```

Watch Claude's tool usage. For the file structure question, it will likely use Bash (`ls`). For JSON files, Glob. For searching content, Grep. For reading CLAUDE.md, Read.

---

## Exercise 2: The One-Shot Dashboard

This is the centerpiece of Day 1. You will ask Claude to build a complete dashboard in a single prompt.

Copy and paste this entire prompt into Claude Code:

```
Create exercises/02_html_page/one_shot_dashboard.html -- a social media analytics dashboard.

Specifications:
- Dark theme: background #191919, cards #262626
- Font: Montserrat from Google Fonts (400, 600, 700 weights)
- 4 stat cards in a grid: Reach (45,200), Impressions (89,100), Engagements (3,421), Ad Spend ($250)
- Each card has a left border accent (4px solid), alternating between #ffc711 and #3cc5ee
- A data table with 5 rows of campaign data: Campaign Name, Impressions, Clicks, CTR, Spend
- A bar chart using Chart.js showing impressions by campaign (5 campaigns)
- A doughnut chart using Chart.js showing spend distribution across campaigns
- Footer: "MARTIVI" in #ffc711 + "DIGITAL" in #3cc5ee, centered
- The whole page should be self-contained: inline CSS and JS, CDN links for fonts and Chart.js
- Professional quality -- this should look like a real client deliverable
```

**Now watch.**

Claude will not just spit out HTML. It will:
1. Possibly check if the directory exists
2. Create the file with all the specified components
3. Possibly verify the file was created

**Open the result in your browser:**

```
open exercises/02_html_page/one_shot_dashboard.html
```

You just built a production-quality dashboard from a single prompt.

**Speed challenge:** That took Claude about 30-60 seconds. How long would it take to write that HTML, CSS, and JavaScript by hand? 2 hours? 3?

---

## Exercise 3: Document What You Observed

Ask Claude to help you create your exploration notes:

```
Create exercises/01_hello_world/exploration_notes.md with a structured document covering:

1. How many tool calls Claude made during the one-shot dashboard (Exercise 2)
2. What the agentic loop looked like -- which tools were called and in what order
3. Which slash commands I tried and what each one does
4. My observations about how Claude Code differs from using ChatGPT or Copilot for coding
```

Claude will create the file, but you should edit it with your actual observations. Tell Claude what you noticed, and it will fill in the details.

---

## Commit Your Work

Save your progress:

```
Commit my work with the message: "day-1: explore claude code tools and build one-shot dashboard"
```

Then push:

```
Push my changes to GitHub
```

---

## What You Accomplished Today

- Learned the 6 core tools and when Claude uses each one
- Understood the agentic loop -- read, plan, act, verify, iterate
- Explored CLAUDE.md as project-level AI configuration
- Learned the permission system and how to control it
- Mastered slash commands and keyboard shortcuts
- Built a complete dashboard from a single prompt
- Documented your observations on the agentic workflow

**Tomorrow:** You will build a full 6-slide client report at production speed. Bring a stopwatch.

**Go to [Day 2: Dashboard Sprint](DAY_2_DASHBOARD_SPRINT.md)**
