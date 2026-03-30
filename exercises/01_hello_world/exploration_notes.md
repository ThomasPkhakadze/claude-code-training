# Day 1 Exploration Notes

**Trainee:** TOMA
**Date:** 2026-03-30

---

## 1. Tool Calls During the One-Shot Dashboard (Exercise 2)

**Total tool calls: 1**

The entire dashboard was created in a single Write tool call. Claude did not need to read existing files, check the directory, or verify the output -- because the prompt was fully specified with every detail: exact data values, colors, chart types, layout structure, and branding.

**Key takeaway:** A well-structured, specific prompt minimizes the number of tool calls. Vague prompts would have triggered multiple rounds of Read, Write, and Edit as Claude iterated toward the desired result.

---

## 2. The Agentic Loop -- Tools Called and In What Order

### Exercise 1 (Repo Exploration)

| Step | Prompt | Tool Used | Why |
|------|--------|-----------|-----|
| 1 | Show file structure | Bash (`find`) | Listing directories and files recursively |
| 2 | Find all JSON files | Glob (`**/*.json`) | Pattern-based file discovery |
| 3 | What about brand colors? | *(already in context)* | CLAUDE.md was loaded at session start |
| 4 | Search for Chart.js references | Grep (regex pattern) | Content search across all files |
| 5 | What exercise folders exist? | Bash (`ls` in a loop) | Checking directory contents and file counts |

### Exercise 2 (One-Shot Dashboard)

| Step | Tool Used | Why |
|------|-----------|-----|
| 1 | Write | Created the complete HTML file in one pass |

**Observation:** The agentic loop was minimal here because the prompt left no ambiguity. In more complex tasks, expect to see the full loop: Read (context) -> Plan -> Write/Edit (act) -> Read (verify) -> Edit (iterate).

---

## 3. Slash Commands

*Note: Add your own observations as you try each command.*

| Command | What It Does | Notes |
|---------|-------------|-------|
| `/help` | Shows all available commands | Good reference when you forget a command |
| `/clear` | Clears conversation history, starts fresh | Use between unrelated tasks |
| `/compact` | Summarizes conversation to free up context window | Use during long sessions when Claude starts losing earlier context |
| `/cost` | Shows token usage and cost for the session | Monitor your usage |
| `/model` | Shows or switches the current model | Check which model you are running |
| `/doctor` | Diagnoses installation and configuration issues | First thing to try when something breaks |
| `/status` | Shows current session status | Quick health check |
| `/init` | Scaffolds a new CLAUDE.md for a project | Use when starting a new project from scratch |

---

## 4. How Claude Code Differs from ChatGPT / Copilot

| Aspect | ChatGPT / Copilot | Claude Code |
|--------|-------------------|-------------|
| **Filesystem access** | None -- you copy/paste code back and forth | Direct -- reads, writes, and edits files on disk |
| **Context** | You manually paste code snippets | Reads your actual project files and structure |
| **Iteration** | You paste errors back, ask for fixes | Claude sees errors and fixes them in a loop |
| **Project config** | Re-explain conventions every session | CLAUDE.md persists project rules across sessions |
| **Output** | Text in a chat window you have to copy | Actual files created/edited in your project |
| **Permissions** | N/A | You approve every action -- like reviewing a PR |
| **Multi-step tasks** | One response at a time | Chains multiple tool calls autonomously |

**The fundamental difference:** ChatGPT and Copilot are text generators that happen to output code. Claude Code is an agent that operates on your codebase. It reads files, makes changes, runs commands, and verifies results -- all within your actual project directory.

---

*Edit this file with your own observations as you continue through the training.*
