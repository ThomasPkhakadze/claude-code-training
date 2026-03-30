# Day 1: First Web Page

**NEW SKILL UNLOCKED: You can create web pages**

Estimated time: 2-3 hours

---

**What you will start with:** A blank folder and a blinking cursor in the terminal.

**What you will end with:** A personal web page with your name, a dark background, and styled text -- created entirely through conversation.

---

## What Is Claude Code?

You may have used ChatGPT or similar tools before. Those tools live inside a browser window -- you type, they respond, and the conversation stays in that window. Claude Code is different.

| Feature | ChatGPT (browser) | Claude Code (terminal) |
|---------|--------------------|------------------------|
| Where it runs | In your web browser | In your terminal, on your computer |
| Can create files | No -- it only shows text | Yes -- it creates real files on your machine |
| Can edit files | No | Yes -- it can modify any file you allow |
| Can read your project | No -- you paste code in | Yes -- it sees your entire project folder |
| Can run commands | No | Yes -- it can run terminal commands for you |
| Needs approval | No -- just text | Yes -- it asks before doing anything |

Think of it this way: ChatGPT is like texting a smart friend. Claude Code is like having a developer sitting at your computer, asking permission before every action.

---

## Step 1: Launch Claude Code

Open your terminal. Navigate to your training folder:

```bash
cd claude-code-training
```

Then start Claude Code:

```bash
claude
```

You should see Claude Code start up and wait for your input. This is your workspace -- everything you create during training will live in this folder.

---

## Step 2: Your First Conversation

Type this (or something like it):

```
Hello! What files are in this folder?
```

Claude will look at the folder and tell you what it finds. This is your first interaction. Notice that Claude read your filesystem -- it did not ask you to paste anything.

Try a few more things:

```
What is this training about?
```

```
What day am I on?
```

Get comfortable with the back-and-forth. There is no wrong thing to say.

---

## Step 3: The Approval System

This is the most important thing to understand about Claude Code.

When Claude wants to do something on your computer -- create a file, edit a file, run a command -- it will ask for your permission first. You will see a prompt like:

```
Do you want to create this file? [y/n]
```

**Before you press `y`, read what Claude is about to do.** Look at the file path, look at the content. This is your safety net. If something looks wrong, press `n` and tell Claude what to change.

Think of it like signing a document: always read before you sign.

---

## Step 4: Exercise -- Create Your First Web Page

Now the real work begins. Ask Claude to create a web page for you. Here is an example of what to say:

```
Create a file at exercises/01_hello_world/index.html with:
- A big heading with my name (use "UJMA" as the name)
- A dark background using the color #191919
- White text
- A short paragraph underneath that says something about me
```

Claude will show you the file it wants to create and ask for your approval. Read through it, then approve.

**What just happened?** Claude created a real HTML file on your computer. This is not a simulation. The file exists.

---

## Step 5: Open It in Your Browser

To see your page, run this command in your terminal (you can ask Claude to run it for you, or open a new terminal window):

**Mac:**
```bash
open exercises/01_hello_world/index.html
```

**PC:**
```bash
start exercises/01_hello_world/index.html
```

Your browser will open and you will see your web page. Your name, on a dark background, in white text. You made that.

---

## Step 6: Experiment and Iterate

Now that you have a page, try asking Claude to change things. This is where it gets fun:

```
Change the background to dark blue instead
```

```
Make my name bigger
```

```
Add a yellow border around the paragraph
```

```
Center everything on the page
```

Each time Claude will show you the change it wants to make. Approve it, refresh your browser, and see the result. This cycle -- ask, approve, refresh, see -- is the core workflow you will use every day.

Notice how Claude edits the existing file rather than creating a new one. It knows the file is there because it can see your project.

---

## Step 7: How to Exit

When you are done for the day:

- Type `/exit` to leave Claude Code
- Or press `Ctrl+C` to interrupt and exit

Claude Code will remember your conversation for the current session, but when you start a new session tomorrow, it will start fresh. That is fine -- your files are saved on your computer.

---

## Commit Your Work

Before you close everything, save your progress with git. Ask Claude:

```
Commit my work with the message: "day-1: first web page"
```

Claude will run the git commands for you. Approve them. Then push to GitHub:

```
Push my changes to GitHub
```

This saves your work in the cloud so it is never lost.

---

## What You Accomplished Today

- Launched Claude Code for the first time
- Had a conversation with an AI that can see and modify your files
- Created a real HTML file on your computer
- Opened it in a browser and saw the result
- Made changes through conversation and saw them live
- Learned the approval workflow
- Committed and pushed your work

**Deliverable:** `exercises/01_hello_world/index.html`

**Tomorrow:** You will learn how to make things look professional with styling, fonts, and layouts.

**Go to [Day 2: Styling](DAY_2_STYLING.md)**
