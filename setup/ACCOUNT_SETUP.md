# Account Setup -- Claude Code

Welcome! This guide will walk you through getting access to Claude Code. It only takes a few minutes.

---

## What You Need

Claude Code requires an **Anthropic account with a paid plan** (Max or Team). You do not need to purchase this yourself -- our team shares a subscription.

**Shared account email:** `content.martividigital@gmail.com`

You will log in using this shared account. Giorgi will give you the password.

> **Important:** Do not share these credentials with anyone outside the team. This is a paid subscription and access is limited to our group.

---

## Step 1: Make Sure Claude Code Is Installed

Before you can log in, Claude Code must be installed on your computer. If you have not done that yet, follow the setup guide for your system first:

- Mac users: see [MAC_SETUP.md](MAC_SETUP.md)
- Windows users: see [PC_SETUP.md](PC_SETUP.md)

Once installed, come back here.

---

## Step 2: Authenticate (Log In)

Open your terminal (Terminal on Mac, PowerShell on Windows) and type:

```
claude
```

The very first time you run this command, your web browser will open automatically and ask you to log in.

**What you will see in the terminal:**

```
Opening browser to authenticate...
Waiting for authentication...
```

**What you will see in the browser:**

A login page for Anthropic (claude.ai). Enter:
- Email: `content.martividigital@gmail.com`
- Password: (Giorgi will provide this separately)

**IMPORTANT -- Verification Code Step:**

After entering the email and password, Anthropic will send a **verification code** to `content.martividigital@gmail.com`. You don't have access to that inbox.

**What to do:**
1. When you see the "Enter verification code" screen, **message Giorgi immediately** (Telegram: @giorginozadze)
2. Tell him: "I need the login code"
3. Giorgi will check the email and send you the 6-digit code
4. Enter the code in the browser and you're in

> This only happens the first time you log in (or if your session expires). After that, Claude Code remembers your session.

After you enter the code, the browser will show a success message. You can close that tab and go back to your terminal.

**What you will see in the terminal after success:**

```
Successfully authenticated!
```

You are now logged in. Claude Code will remember your session, so you will not need to do this every time.

---

## Step 3: Verify Everything Works

Run this command to check your version:

```
claude --version
```

**What you will see:**

```
claude 1.x.x
```

(The exact number does not matter -- as long as you see a version, you are good.)

Now start a quick session to make sure everything is working:

```
claude
```

**What you will see:**

```
Claude Code v1.x.x

>
```

That `>` is the prompt where you type your questions and instructions to Claude. Try typing:

```
> Hello, who are you?
```

Claude will respond with a friendly introduction. Type `/exit` to leave when you are done.

---

## Troubleshooting

### "The browser did not open"

Sometimes the automatic browser launch fails. Look in your terminal output for a URL that looks like:

```
https://console.anthropic.com/auth/...
```

Copy that entire URL, open your browser manually, and paste it into the address bar.

### "Login failed" or "Invalid credentials"

- Double-check that you are using the exact email and password Giorgi provided
- Make sure there are no extra spaces before or after the email/password
- If you are still stuck, message Giorgi -- the password may have been updated

### "I need a verification code but can't reach Giorgi"

Wait until you can reach him. The code is sent to his email and expires after a few minutes, so you need to coordinate in real time. Best to message him on Telegram right when you're at the login screen.

### "Session expired"

If you see an authentication error after some time, just run `claude` again. It will re-open the browser for you to log in again.

### "Permission denied" or "Account not authorized"

This means your account has not been added to the paid plan yet. Contact Giorgi to confirm your access.

---

## You're Ready!

You have a working Claude Code installation and you are logged in. You can now:

- Start a Claude session anytime by typing `claude` in your terminal
- Use it inside any project folder on your computer
- Ask it questions, have it write code, fix bugs, and more

Next step: follow [GITHUB_SETUP.md](GITHUB_SETUP.md) to set up your GitHub account and get the training materials.
