# Claude Code Slash Commands

Type `/` inside Claude Code to see all commands. Here are the ones you'll use most:

## Essential Commands

| Command | What It Does | When To Use It |
|---------|-------------|----------------|
| `/help` | Shows all available commands | When you forget a command |
| `/exit` or `/quit` | Exits Claude Code | When you're done working |
| `/clear` | Clears conversation history | When conversation gets confusing or you want a fresh start |
| `/compact` | Compresses conversation to save context | When Claude starts "forgetting" earlier parts of your chat |
| `/cost` | Shows token usage and cost for this session | To check how much you've used |

## Model & Settings

| Command | What It Does | When To Use It |
|---------|-------------|----------------|
| `/model` | Switch between AI models (Sonnet, Opus) | Opus for complex work, Sonnet for faster simpler tasks |
| `/config` | Open settings | To change theme, model, or other preferences |
| `/theme` | Change the color scheme | If you prefer light/dark/other themes |
| `/doctor` | Diagnose your installation | When something seems broken |
| `/status` | Check version, model, account info | To verify everything is working |

## Session Management

| Command | What It Does | When To Use It |
|---------|-------------|----------------|
| `/resume` | Continue a previous session | To pick up where you left off yesterday |
| `/rename` | Rename current session | To organize your sessions by topic |
| `/export` | Export conversation as text | To save a conversation for reference |
| `/copy` | Copy last response to clipboard | To paste Claude's response somewhere else |

## Advanced (Developer Track)

| Command | What It Does | When To Use It |
|---------|-------------|----------------|
| `/init` | Create a CLAUDE.md for a new project | When starting a new project |
| `/diff` | View recent file changes | To review what Claude changed |
| `/context` | Visualize context window usage | To see how much context space is left |
| `/mcp` | Manage MCP server connections | To connect external tools (GitHub, Slack, etc.) |
| `/permissions` | View/update tool permissions | To allow or block specific actions |

## Quick Shell Commands

You can run terminal commands directly from Claude Code by prefixing with `!`:

```
! git status          # Check git status
! open file.html      # Open file in browser (Mac)
! start file.html     # Open file in browser (PC)
! ls                  # List files
```

---

*Tip: Type `/` and start typing to filter commands. For example, `/co` will show `/compact`, `/config`, `/copy`, `/cost`.*
