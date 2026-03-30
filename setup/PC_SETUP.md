# PC Setup -- Claude Code for Beginners (Windows)

Welcome! This guide will get Claude Code running on your Windows computer. Even if you have never typed a command before, you will be fine. Just follow each step.

---

## What Is PowerShell?

PowerShell is an app on Windows that lets you talk to your computer by typing commands instead of clicking buttons. Think of it like **texting your computer** -- you type a message, press Enter, and it responds.

It is the Windows version of what Mac users call "Terminal." Same idea, slightly different commands.

---

## Step 1: Open PowerShell

Press the **Windows key** on your keyboard (the one with the Windows logo, usually between Ctrl and Alt).

Type:

```
PowerShell
```

You will see **Windows PowerShell** appear in the search results. Click on it.

**What you will see:**

```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

PS C:\Users\YourName>
```

That last line is the **prompt**. The `PS C:\Users\YourName>` part tells you where you are on your computer. It is waiting for you to type something.

> **Tip:** If you see an option for "Windows PowerShell" and "PowerShell 7", either one works. Just pick whichever appears first.

---

## Step 2: Install Git for Windows (DO THIS FIRST)

Git is a tool that developers use to track changes in code. **Claude Code requires Git to be installed**, so we do this step first.

### Download and Install

1. Open your browser and go to: **https://git-scm.com/downloads/win**
2. The download should start automatically. If not, click the download link for your system (usually "64-bit Git for Windows Setup")
3. Run the downloaded file
4. The installer will ask many questions. **Just click "Next" for every screen** -- the default settings are fine
5. On the last screen, click **Install**, then click **Finish**

### Verify Git Is Installed

Close PowerShell completely (click the X button) and open it again. Then type:

```
git --version
```

**What you will see:**

```
git version 2.44.0.windows.1
```

If you see a version number, Git is installed. If you see an error, close PowerShell and open it again -- it sometimes needs a restart after installing new programs.

---

## Step 3: Install Claude Code

In PowerShell, copy and paste this entire line, then press Enter:

```
irm https://claude.ai/install.ps1 | iex
```

> **How to paste in PowerShell:** Right-click inside the PowerShell window. That pastes whatever is on your clipboard.

**What you will see:**

```
Downloading Claude Code...
Installing...
Claude Code has been installed successfully!
```

The exact messages may vary, but you should see a success message at the end.

---

## Step 4: Verify the Installation

Close PowerShell and open it again (new programs sometimes are not recognized until you restart PowerShell). Then type:

```
claude --version
```

**What you will see:**

```
claude 1.x.x
```

If you see a version number, the installation worked.

---

## Step 5: Navigate to the Training Project

When you clone the training repository (covered in [GITHUB_SETUP.md](GITHUB_SETUP.md)), it will create a folder on your computer. You need to navigate to that folder before launching Claude.

For example, if you cloned the repo into your user folder:

```
cd C:\Users\YourName\claude-code-training
```

**What you will see:**

```
PS C:\Users\YourName\claude-code-training>
```

The prompt now shows `claude-code-training` -- that tells you which folder you are in.

---

## Step 6: Launch Claude Code

While inside the project folder, type:

```
claude
```

**What you will see:**

```
Claude Code v1.x.x

>
```

You are in! That `>` prompt is where you talk to Claude. Try typing:

```
> What files are in this project?
```

Claude will look at the project and tell you what is there. Type `/exit` to leave the session when you are done.

---

## Common PowerShell Commands

Here are the only commands you need to know for now:

| Command | What It Does | Example |
|---------|-------------|---------|
| `pwd` | Shows where you are (which folder) | `pwd` |
| `ls` or `dir` | Lists files in the current folder | `ls` |
| `cd foldername` | Goes into a folder | `cd claude-code-training` |
| `cd ..` | Goes back one folder | `cd ..` |
| `cd ~` | Goes to your home folder | `cd ~` |
| `start filename` | Opens a file (like double-clicking) | `start index.html` |
| `cls` | Clears the screen | `cls` |

### Opening HTML Files in the Browser

When you create HTML files during exercises, you can open them in your browser directly from PowerShell:

```
start my-page.html
```

This opens the file in your default browser, just like double-clicking it in File Explorer.

You can also just find the file in File Explorer and double-click it -- that works too.

---

## Troubleshooting

### "not recognized as the name of a cmdlet"

This is the Windows version of "command not found." It means PowerShell does not know where the program is. Try:

1. Close PowerShell completely (click the X)
2. Open PowerShell again
3. Try the command again

If it still does not work for `claude`, run the install command from Step 3 again.

### "git is not recognized"

Git was not installed correctly or PowerShell was not restarted after installation. Try:

1. Make sure you completed the Git installation in Step 2 (all the way to "Finish")
2. Close PowerShell completely and open it again
3. Try `git --version` again

If it still fails, re-run the Git installer from https://git-scm.com/downloads/win.

### "execution of scripts is disabled on this system"

Windows sometimes blocks scripts for security. Run this command to allow them:

```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

It will ask you to confirm. Type `Y` and press Enter. Then try the Claude install command again.

### "Access is denied"

Try opening PowerShell as Administrator:
1. Press the Windows key
2. Type "PowerShell"
3. Right-click on "Windows PowerShell"
4. Click "Run as administrator"
5. Click "Yes" on the popup
6. Try the command again

### PowerShell looks different from the screenshots

There are a few versions of PowerShell and they look slightly different. As long as you see a prompt that ends with `>`, you are in the right place.

### I accidentally closed PowerShell

No problem. Just open it again the same way (Windows key, type PowerShell, click it). You will start in your home folder, so you will need to `cd` back to the project folder.

---

## You're Ready!

Your Windows PC is set up for Claude Code development. Here is what you accomplished:

- You opened PowerShell for the first time
- You installed Git for Windows
- You installed Claude Code
- You know how to navigate folders and open files

Next steps:
- Set up your GitHub account: [GITHUB_SETUP.md](GITHUB_SETUP.md)
- Set up your Claude Code login: [ACCOUNT_SETUP.md](ACCOUNT_SETUP.md)

You did it. The hardest part is the first time you open that command-line window, and that is already behind you.
