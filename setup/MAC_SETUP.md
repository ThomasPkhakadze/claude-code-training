# Mac Setup -- Claude Code for Beginners

Welcome! This guide will get Claude Code running on your Mac. Even if you have never used a terminal before, you will be fine. Just follow each step.

---

## What Is Terminal?

Terminal is an app on your Mac that lets you talk to your computer by typing commands instead of clicking buttons. Think of it like **texting your computer** -- you type a message, press Enter, and it responds.

It might look intimidating at first, but you will only need a handful of commands. And once you get comfortable, it actually feels faster than clicking through menus.

---

## Step 1: Open Terminal

Press these keys at the same time:

```
Cmd + Space
```

This opens **Spotlight Search** (a search bar in the middle of your screen). Type:

```
Terminal
```

Press **Enter**. The Terminal app will open.

**What you will see:**

```
Last login: Sat Mar 29 10:00:00 on ttys000
yourname@YourMac ~ %
```

That last line is called the **prompt**. It is waiting for you to type something. The `%` (or sometimes `$`) at the end is just the computer saying "I'm ready."

> **Tip:** You can also find Terminal in Applications > Utilities > Terminal. But Spotlight is faster.

---

## Step 2: Install Git (If Not Already Installed)

Git is a tool that developers use to track changes in their code. Claude Code needs it. Your Mac might already have it. Let us check.

Type this and press Enter:

```
git --version
```

**If you see something like this, Git is already installed:**

```
git version 2.39.0
```

Skip ahead to Step 3.

**If you see a popup asking to install "command line developer tools":**

Click **Install** and wait. It may take 5-10 minutes. When it finishes, try `git --version` again to confirm.

**If nothing happens and you see "command not found":**

Type this and press Enter:

```
xcode-select --install
```

A popup will appear. Click **Install**, then wait for it to finish. After that, run `git --version` again to confirm.

---

## Step 3: Install Claude Code

Copy and paste this entire line into Terminal, then press Enter:

```
curl -fsSL https://claude.ai/install.sh | bash
```

**What you will see:**

```
Downloading Claude Code...
Installing...
Claude Code has been installed successfully!
```

The exact messages may vary slightly, but you should see a success message at the end.

---

## Step 4: Verify the Installation

Type this and press Enter:

```
claude --version
```

**What you will see:**

```
claude 1.x.x
```

If you see a version number, the installation worked.

> **Note:** If you see "command not found", close Terminal completely (Cmd+Q) and open it again. Then try the command once more. Sometimes Terminal needs a fresh start to recognize new programs.

---

## Step 5: Navigate to the Training Project

When you clone the training repository (covered in [GITHUB_SETUP.md](GITHUB_SETUP.md)), it will create a folder on your computer. You need to navigate to that folder before launching Claude.

For example, if you cloned the repo into your home directory:

```
cd ~/claude-code-training
```

**What you will see:**

```
yourname@YourMac claude-code-training %
```

Notice the prompt now shows `claude-code-training` -- that tells you which folder you are in.

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

## Common Terminal Commands

Here are the only commands you need to know for now:

| Command | What It Does | Example |
|---------|-------------|---------|
| `pwd` | Shows where you are (which folder) | `pwd` |
| `ls` | Lists files in the current folder | `ls` |
| `cd foldername` | Goes into a folder | `cd claude-code-training` |
| `cd ..` | Goes back one folder | `cd ..` |
| `cd ~` | Goes to your home folder | `cd ~` |
| `open filename` | Opens a file (like double-clicking) | `open index.html` |
| `clear` | Clears the screen | `clear` |

### Opening HTML Files in the Browser

When you create HTML files during exercises, you can open them in your browser directly from Terminal:

```
open my-page.html
```

This opens the file in your default browser (Safari or Chrome), just like double-clicking it in Finder.

---

## Troubleshooting

### "command not found: claude"

This usually means Terminal has not refreshed its list of available programs. Try:

1. Close Terminal completely (Cmd+Q, not just the red X button)
2. Open Terminal again
3. Try `claude --version` again

If it still does not work, run the install command from Step 3 again.

### "command not found: git"

Run `xcode-select --install` (from Step 2) and follow the prompts.

### "permission denied"

This sometimes happens when running install scripts. Try adding `sudo` before the command:

```
sudo curl -fsSL https://claude.ai/install.sh | bash
```

It will ask for your Mac password (the one you use to log in). When you type it, you will not see any characters appear -- that is normal. Just type it and press Enter.

### "zsh: no such file or directory"

This means you tried to go to a folder that does not exist. Check the spelling. Use `ls` to see what folders are available in your current location.

### Terminal is confusing and I want to start over

Just close Terminal (Cmd+Q) and open it again. Every time you open Terminal, you get a fresh start in your home folder. Nothing you type in Terminal can break your computer -- the worst that can happen is an error message.

---

## You're Ready!

Your Mac is set up for Claude Code development. Here is what you accomplished:

- You opened Terminal for the first time
- You installed Git
- You installed Claude Code
- You know how to navigate folders and open files

Next steps:
- Set up your GitHub account: [GITHUB_SETUP.md](GITHUB_SETUP.md)
- Set up your Claude Code login: [ACCOUNT_SETUP.md](ACCOUNT_SETUP.md)

You are doing great. Seriously -- opening a terminal for the first time is the hardest part, and you already did it.
