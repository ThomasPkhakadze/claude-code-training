# GitHub Setup -- From Scratch

Welcome! This guide will walk you through creating a GitHub account, installing Git, and getting a copy of the training materials on your computer. No experience required.

---

## What Is GitHub?

Think of GitHub as **Google Drive for code, but with a timeline of every change you make**.

When you work on a Google Doc, you can see the version history -- who changed what and when. GitHub does the same thing, but for code and any other files. Every time you save a change (called a "commit"), GitHub remembers exactly what changed, when, and why.

This is useful because:
- Your supervisor can see your progress without you sending files back and forth
- You can never lose your work -- every version is saved
- You can experiment freely and go back if something breaks

---

## Step 1: Create a GitHub Account

1. Go to **https://github.com** in your browser
2. Click **Sign up**
3. Enter your email address, create a password, and choose a username

### Choosing a Username

Pick something **professional** -- this will be visible to others. Good examples:
- `firstnamelastname` (e.g., `ujamosenashvili`)
- `firstname-lastname` (e.g., `ujama-osenashvili`)

Avoid joke names or random numbers. This is like your professional handle.

4. Complete the verification puzzle
5. Choose the **Free** plan (that is all you need)
6. You now have a GitHub account

---

## Step 2: Install Git on Your Computer

Git is the program that runs on your computer and talks to GitHub. Think of it this way: **GitHub is the website, Git is the tool on your computer.**

### Mac Users

Open Terminal (Cmd+Space, type "Terminal", press Enter) and type:

```
git --version
```

**If you see a version number:**

```
git version 2.39.0
```

Git is already installed. Skip to Step 3.

**If you see a popup or "command not found":**

```
xcode-select --install
```

Click **Install** when the popup appears. Wait for it to finish (5-10 minutes). Then try `git --version` again.

### Windows Users

If you followed [PC_SETUP.md](PC_SETUP.md), you already installed Git. You can verify by opening PowerShell and typing:

```
git --version
```

**What you will see:**

```
git version 2.44.0.windows.1
```

If Git is not installed, go to **https://git-scm.com/downloads/win**, download and install it (click "Next" on every screen), then restart PowerShell.

---

## Step 3: Configure Git (Tell Git Who You Are)

Git needs to know your name and email so it can label your changes. Open Terminal (Mac) or PowerShell (Windows) and run these two commands, replacing the values with your own:

```
git config --global user.name "Your Full Name"
```

```
git config --global user.email "your@email.com"
```

For example:

```
git config --global user.name "Ujama Osenashvili"
```

```
git config --global user.email "ujama@example.com"
```

> **Use the same email you used to create your GitHub account.** This links your computer's changes to your GitHub profile.

To verify it worked:

```
git config --global user.name
```

**What you will see:**

```
Ujama Osenashvili
```

```
git config --global user.email
```

**What you will see:**

```
ujama@example.com
```

You only need to do this once. Git remembers these settings.

---

## Step 4: Fork the Training Repository

A "fork" is your personal copy of a project. You will make a fork of the training materials so you have your own version to work in.

1. Make sure you are logged in to GitHub
2. Go to: **https://github.com/geganoza/claude-code-training**
3. In the top-right corner, click the **Fork** button
4. On the next screen, click **Create fork**

**What happens:** GitHub creates a copy of the project under your account. You will now see it at:

```
https://github.com/YOUR_USERNAME/claude-code-training
```

This is YOUR copy. You can make any changes you want without affecting the original.

---

## Step 5: Clone Your Fork (Download It to Your Computer)

"Cloning" means downloading your fork from GitHub to your computer so you can work on it locally.

Open Terminal (Mac) or PowerShell (Windows).

First, go to your home folder:

```
cd ~
```

Now clone the repository. Replace `YOUR_USERNAME` with your actual GitHub username:

```
git clone https://github.com/YOUR_USERNAME/claude-code-training.git
```

**What you will see:**

```
Cloning into 'claude-code-training'...
remote: Enumerating objects: 45, done.
remote: Counting objects: 100% (45/45), done.
remote: Compressing objects: 100% (32/32), done.
Receiving objects: 100% (45/45), 12.50 KiB | 6.25 MiB/s, done.
```

Now go into the project folder:

```
cd claude-code-training
```

List the files to see what is inside:

```
ls
```

**What you will see:**

```
README.md    beginner/    developer/    exercises/    setup/    ...
```

You now have all the training materials on your computer.

---

## Step 6: The 5 Git Commands You Will Use Daily

You only need five commands. Here is what each one does:

### 1. `git status` -- "What has changed?"

This shows you which files you have modified, added, or deleted since your last save.

```
git status
```

**What you will see (when you have made changes):**

```
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)

        modified:   exercises/my-solution.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        exercises/new-file.html
```

**What you will see (when everything is saved):**

```
On branch main
nothing to commit, working tree clean
```

### 2. `git add` -- "I want to include these changes"

This tells Git which files you want to include in your next save. You can add specific files:

```
git add exercises/my-solution.html
```

Or add everything that has changed:

```
git add .
```

(The `.` means "everything in the current folder.")

### 3. `git commit -m "message"` -- "Save my changes with a note"

This saves your changes with a description of what you did. Always write a clear, short message:

```
git commit -m "Complete exercise 1: personal landing page"
```

**What you will see:**

```
[main abc1234] Complete exercise 1: personal landing page
 1 file changed, 25 insertions(+)
```

Good commit messages describe **what you did**, not what the file is:
- Good: `"Add contact section to landing page"`
- Good: `"Fix broken image link in about page"`
- Bad: `"update"`
- Bad: `"stuff"`

### 4. `git push` -- "Upload my saves to GitHub"

This sends your committed changes from your computer to GitHub so others can see them:

```
git push
```

**What you will see:**

```
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 350 bytes | 350.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To https://github.com/YOUR_USERNAME/claude-code-training.git
   abc1234..def5678  main -> main
```

> **First time pushing:** Git may ask you to log in to GitHub. Follow the prompts -- it will open a browser window or ask for your username and a "personal access token" (which acts like a password). If asked for a token, see the troubleshooting section below.

### 5. `git log` -- "Show me my save history"

This shows all your previous commits:

```
git log --oneline
```

**What you will see:**

```
def5678 Complete exercise 1: personal landing page
abc1234 Initial commit
```

Press `q` to exit the log view.

### The Typical Workflow

Every time you finish a task or exercise, you will do this:

```
git add .
git commit -m "Describe what you did"
git push
```

That is it. Three commands, and your work is saved and visible on GitHub.

---

## How Your Supervisor Reviews Your Work

Your supervisor (Giorgi) will review your progress by visiting your fork on GitHub:

```
https://github.com/YOUR_USERNAME/claude-code-training
```

There, they can see:
- Every file you have created or changed
- Your commit history (the timeline of all your saves)
- When you made each change

You do not need to send files or screenshots. Just push your commits, and your supervisor can see everything.

---

## Troubleshooting

### "Authentication failed" when pushing

GitHub no longer accepts passwords for pushing code. You need a **Personal Access Token**:

1. Go to https://github.com/settings/tokens
2. Click **Generate new token (classic)**
3. Give it a name like "My Computer"
4. Check the box next to **repo** (this gives it permission to push code)
5. Click **Generate token** at the bottom
6. Copy the token (it looks like `ghp_xxxxxxxxxxxxxxxxxxxx`)
7. When Git asks for your password, **paste this token instead**

> **Important:** Save this token somewhere safe. GitHub will only show it to you once.

### "fatal: repository not found"

Make sure you replaced `YOUR_USERNAME` with your actual GitHub username in the clone command. Check the URL:

```
https://github.com/YOUR_USERNAME/claude-code-training.git
```

### "fatal: not a git repository"

You are not inside the project folder. Navigate to it first:

```
cd ~/claude-code-training
```

### "Updates were rejected because the remote contains work that you do not have locally"

This means someone (or you, from another computer) pushed changes that you do not have yet. Pull first, then push:

```
git pull
git push
```

### I made a mess and want to start over

If things get really confusing, you can always delete the folder and clone again:

Mac:
```
cd ~
rm -rf claude-code-training
git clone https://github.com/YOUR_USERNAME/claude-code-training.git
```

Windows:
```
cd ~
Remove-Item -Recurse -Force claude-code-training
git clone https://github.com/YOUR_USERNAME/claude-code-training.git
```

Your commits on GitHub are safe -- cloning again just re-downloads everything.

---

## You're Ready!

You now have:
- A GitHub account
- Git installed and configured on your computer
- Your own fork of the training repository
- The 5 commands you need to save and share your work

This is a real developer workflow. Every professional software team in the world uses Git and GitHub (or something very similar) every single day. You are now part of that world.

Next steps:
- Set up Claude Code on your system: [MAC_SETUP.md](MAC_SETUP.md) or [PC_SETUP.md](PC_SETUP.md)
- Log in to Claude Code: [ACCOUNT_SETUP.md](ACCOUNT_SETUP.md)

Then open the training exercises and start building.
