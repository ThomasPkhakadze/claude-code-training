# Day 4: Advanced Mastery

**NEW SKILL UNLOCKED: Advanced Claude Code mastery**

Estimated time: 3-4 hours

---

**What you will start with:** Three days of hands-on experience with Claude Code's core workflow.

**What you will end with:** Knowledge of advanced features (MCP, hooks, permission modes), mastery of prompt engineering patterns, and a prompt comparison exercise that reveals which approach works best for you.

---

## Advanced Features Overview

You have been using Claude Code's core tools for three days. Now learn the features that separate casual users from power users.

### MCP Servers (Model Context Protocol)

MCP servers are external integrations that extend Claude Code's capabilities beyond the local filesystem.

**What they do:** Connect Claude Code to external services -- GitHub, Slack, databases, APIs -- so Claude can read issues, post messages, query data, and more, all from within a conversation.

**Examples:**
- A GitHub MCP server lets Claude read issues, create PRs, and check CI status without you switching to the browser
- A database MCP server lets Claude query your Postgres or Supabase tables directly
- A Slack MCP server lets Claude read and post messages

**How to set up:** Use `/mcp` in Claude Code to view and configure MCP servers. The configuration lives in your project's `.mcp.json` or your global Claude config.

```json
// Example .mcp.json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your-token"
      }
    }
  }
}
```

**You do not need to configure one now.** Just know they exist. When you find yourself constantly switching between Claude Code and a browser to check GitHub issues or Slack messages, that is when MCP servers pay off.

### Hooks

Hooks are automated actions that run on specific Claude Code events. Think of them like git hooks but for Claude operations.

**What they do:** Run custom commands automatically when Claude performs certain actions -- after every file edit, before every commit, after a conversation ends.

**Example use cases:**
- Run a linter after every file edit
- Run tests after code changes
- Format code automatically after writes
- Send a notification when a long task completes

**Configuration:** Hooks are defined in your project's `.claude/settings.json`:

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "command": "npx prettier --write $CLAUDE_FILE_PATH"
      }
    ]
  }
}
```

**The concept is simple:** define a trigger event, an optional matcher (which tool or pattern), and a command to run. Claude Code handles the rest.

### Permission Modes

You have been using default mode. Here are all three:

| Mode | Behavior | Best For |
|------|----------|----------|
| **Default** | Asks before every tool call | Learning, unfamiliar codebases, sensitive operations |
| **Plan Mode** | Claude shows its full plan before executing | Complex multi-step tasks where you want to review the approach first |
| **Auto Mode** | Auto-approves safe operations (reads, globs, greps), asks for writes/edits/bash | Fast iteration on trusted projects, when you know the codebase well |

**Shift+Tab** cycles between modes. You can also start Claude in a specific mode:

```bash
claude --auto       # Start in auto mode
claude --plan       # Start in plan mode
```

**When to use Auto Mode:** When you are iterating rapidly on a project you know well. Auto mode lets Claude read and search freely, only stopping to ask when it wants to write or run commands. This eliminates dozens of "y" keypresses per session.

**When to use Plan Mode:** When you are about to ask Claude to do something complex -- like refactoring a module or building a multi-file feature -- and you want to see the plan before any files are touched.

### /init -- Scaffold CLAUDE.md for Any Project

This is how you bring Claude Code's power to any project. Try it:

```bash
mkdir /tmp/test-project && cd /tmp/test-project
claude
```

Then type:

```
/init
```

Claude will analyze the (empty) directory and generate a CLAUDE.md tailored to the project. For an existing project with code, it reads the codebase and generates conventions based on what it finds -- language, framework, test patterns, build tools, etc.

**The takeaway:** Every new project you start should get a `/init` early on. The 2 minutes it takes pays back hours of re-explaining context across sessions.

---

## Prompt Engineering for Developers

This is not about "magic words." It is about structuring information so Claude produces the best result with the fewest iterations.

### Pattern 1: The One-Shot (Context Dump)

Give Claude everything it needs in a single message. Works best when you have a clear specification.

**Structure:**
```
Create [file path] -- [what it is].

Data:
[paste or reference the data]

Layout:
[describe structure: sections, grids, components]

Styling:
[colors, fonts, spacing, brand standards]

Charts:
[chart types, which data maps where]

Constraints:
[responsive, print-friendly, self-contained, etc.]
```

**When to use:** You have a complete spec. You know exactly what you want. You want to see a full result and iterate from there.

**Pros:** Fast. One prompt, one result. Often good enough on the first try.
**Cons:** If the result is off, it is hard to know which part of your prompt was ambiguous.

### Pattern 2: The Iterative Build

Start with structure, layer on features. Works best for complex or exploratory work.

**Structure:**
```
Step 1: "Create the base HTML structure with CSS variables and layout."
Step 2: "Add the stat cards section with this data: ..."
Step 3: "Add a bar chart showing ..."
Step 4: "Polish: add responsive text, print styles, footer."
```

**When to use:** You are exploring a design. You want to see each piece before adding the next. The requirements are evolving.

**Pros:** Easy to course-correct. Each step is reviewable. You learn more about Claude's output.
**Cons:** Slower. More prompts, more approvals. Context window fills up faster.

### Pattern 3: The Reference

Point Claude at an existing file and say "like that, but different."

**Structure:**
```
Read reference/sample_dashboard.html. Create a new dashboard at exercises/new/report.html that follows the same structure and styling, but uses this data: [data]. Change the client name to X and the brand accent to Y.
```

**When to use:** You have a template or previous work that is close to what you need. This is the fastest approach for derivative work.

**Pros:** Extremely fast. Consistent output. Minimal ambiguity.
**Cons:** Requires a good reference file to exist.

### Pattern 4: The Pipe

Feed data directly into Claude from the command line. No need to open an interactive session.

```bash
cat exercises/03_dashboard/data.json | claude -p "Create an HTML dashboard from this data with dark theme, Chart.js charts, and MARTIVI DIGITAL branding. Output to exercises/new/piped_dashboard.html"
```

**When to use:** Quick one-off tasks. Scripted workflows. When you want Claude to process data without a conversation.

---

## Exercise: Prompt Mastery Challenge

You will build the same dashboard twice using different approaches, then compare the results.

### Dashboard Spec

Build a "Weekly Social Media Snapshot" dashboard with:
- Title: "Weekly Snapshot -- March 23-29, 2026"
- 3 stat cards: Posts Published (12), Total Reach (18.5K), Engagement Rate (4.2%)
- Bar chart: daily reach for Mon-Sun (2.1K, 2.8K, 3.2K, 1.9K, 2.5K, 3.8K, 2.2K)
- Doughnut chart: content type split (Reels 45%, Stories 30%, Posts 25%)
- Dark theme, MARTIVI DIGITAL footer, Montserrat font

### Attempt 1: One-Shot

Time yourself. Give Claude the entire spec in a single prompt. Save to `exercises/04_landing_page/oneshot_weekly.html`.

Write down: Time taken, number of tool calls Claude made, quality on first try (1-10).

### Attempt 2: Iterative

Time yourself. Build the same dashboard step by step:
1. Base HTML structure with CSS variables
2. Add stat cards
3. Add bar chart
4. Add doughnut chart
5. Polish (footer, spacing, responsive text)

Save to `exercises/04_landing_page/iterative_weekly.html`.

Write down: Time taken, total number of tool calls, quality on first try (1-10).

### Compare

Open both in the browser side by side. Ask yourself:
- Which was faster?
- Which produced better results?
- Which gave you more control?
- Which approach would you use for a tight deadline vs. a new design exploration?

Write a brief note documenting your comparison. You can ask Claude to help:

```
Create exercises/04_landing_page/prompt_comparison.md documenting my results from the one-shot vs iterative prompt exercise. I'll tell you my observations.
```

**Speed challenge:** You just built the same dashboard twice in ___ total minutes. By hand, that is at least 3 hours of work for a single version.

---

## Commit Your Work

```
Commit my work with the message: "day-4: prompt mastery exercise and comparison"
```

Then push:

```
Push my changes to GitHub
```

---

## What You Accomplished Today

- Learned about MCP servers for external integrations
- Understood hooks for automated post-action commands
- Mastered the three permission modes and when to use each
- Practiced `/init` for scaffolding CLAUDE.md in new projects
- Learned four prompt engineering patterns (one-shot, iterative, reference, pipe)
- Built the same dashboard two ways and compared the results

---

## Next Step: The Final Test

You are ready. Everything you have learned over 4 days comes together in the final test.

**Go to [Final Test](FINAL_TEST.md)**
