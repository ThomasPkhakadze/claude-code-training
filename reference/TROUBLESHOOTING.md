# Troubleshooting Guide

## Problem: "command not found: claude"

**You see:** `claude: command not found` or `'claude' is not recognized`

**Fix:**
1. Close your terminal completely
2. Open a new terminal window
3. Try again: `claude --version`

Still not working?
- **Mac:** Run `export PATH="$HOME/.local/bin:$PATH"` then try again
- **PC:** Make sure Git for Windows is installed, then reinstall Claude Code

---

## Problem: Claude Code won't start / authentication error

**You see:** Error about authentication or login

**Fix:**
1. Run `claude` -- it should open your browser for login
2. Log in with the account credentials Giorgi provided
3. If browser doesn't open, look for a URL in the terminal output and paste it in your browser manually
4. After logging in, return to your terminal

---

## Problem: Claude is not responding

**You see:** You typed a message but nothing happens for 30+ seconds

**Fix:**
1. Wait 15-20 seconds -- Claude might be thinking (complex tasks take longer)
2. If still nothing, press `Escape` to cancel
3. Try your message again
4. If it keeps happening, type `/exit` and restart with `claude`

---

## Problem: "Permission denied" error

**You see:** Claude says it can't create or edit a file

**Fix:**
1. Make sure you're in the right folder (`pwd` to check)
2. Make sure you're asking Claude to create files in `exercises/` or `progress/`
3. If Claude asks `Allow? [y/n]`, type `y` and press Enter

---

## Problem: HTML file is blank in browser

**You see:** You open the HTML file but the page is empty or white

**Fix:**
1. Ask Claude: "Read my HTML file and check for syntax errors"
2. Common causes:
   - Missing closing tags (`</div>`, `</body>`, `</html>`)
   - CSS `color: #191919` on a `background: #191919` (same color = invisible text)
   - File was created but is empty
3. Try: Right-click the page → "View Page Source" to see if there's content

---

## Problem: Chart.js charts not showing

**You see:** The page loads but chart areas are blank

**Fix:**
1. Make sure this line is in the `<head>` section:
   ```html
   <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
   ```
2. Check that the canvas ID matches the JavaScript (e.g., `id="myChart"` must match `document.getElementById('myChart')`)
3. Open browser developer tools (F12 or Cmd+Option+I) → Console tab → look for red errors

---

## Problem: Fonts look wrong

**You see:** Text doesn't look like Montserrat / looks like default browser font

**Fix:**
1. Make sure this line is in the `<head>`:
   ```html
   <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&display=swap" rel="stylesheet">
   ```
2. Make sure CSS includes: `font-family: 'Montserrat', sans-serif;`
3. You need an internet connection for Google Fonts to load

---

## Problem: Git says "nothing to commit"

**You see:** `nothing to commit, working tree clean`

**Fix:**
- Your files might not be saved yet. Make sure Claude finished creating/editing them.
- Check `git status` -- if files show as "untracked", you need `git add` first
- If you already committed, this message is normal -- it means everything is saved

---

## Problem: Git push fails

**You see:** `error: failed to push` or `rejected`

**Fix:**
1. Make sure you committed first: `git add . && git commit -m "your message"`
2. Make sure you're pushing to YOUR fork, not the original repo
3. Try: `git push origin main`
4. If asked for credentials, use your GitHub username and a personal access token (not your password)

---

## Problem: "Context window full" or Claude forgets earlier conversation

**You see:** Claude seems to forget what you were working on, or mentions context limits

**Fix:**
1. Type `/compact` -- this compresses the conversation so Claude can keep going
2. If that's not enough, type `/clear` to start fresh (your files are still saved!)
3. After clearing, tell Claude what you're working on: "I'm on Day 3, working on the dashboard exercise"

---

## Problem: My changes disappeared

**You see:** You made changes but the file looks different / changes are gone

**Fix:**
1. You might have started a new Claude session. Check the file: ask Claude to "read exercises/.../filename.html"
2. Your changes might not have been approved -- did you type `y` when Claude asked?
3. Check git: `git diff` shows uncommitted changes, `git log` shows committed work

---

## Still Stuck?

1. **Ask Claude:** "I'm having a problem. [describe what you see]"
2. **Run diagnostics:** `claude doctor` (checks your setup)
3. **Check reference materials:** Look in the `reference/` folder
4. **Contact Giorgi:** Telegram @giorginozadze or giorgi.nozadze@martividigital.com

---

*Tip: When reporting a problem, include: what you were trying to do, what you expected, and what actually happened. Screenshots help!*
