# 🔐 Authenticate With GitHub the Easy Way

**Related Project**: [confident_quizes](https://github.com/adamrossnelson/confident_quizes)
**Goal**: Get logged into GitHub from your terminal in about a minute — no SSH keys, no copy-pasting tokens, no "permission denied" headaches.

---

## 🤔 What Is This Guide For?

When you `git push` your work to GitHub, GitHub needs to know it's really you. There are a few ways to prove it, and historically the most common path was SSH keys which involve generating a cryptographic key pair, copying the public half to GitHub, hoping `ssh-agent` is running, etc.

That whole process is a notorious source of frustration. Good news is that there's a much friendlier way using a free official tool from GitHub called the GitHub CLI (short for "command line interface"). One command, a browser tab, and you're done.

This guide walks you through it. It works on Mac and Windows (and Linux, if you're curious).

---

## 📌 Before You Start

✅ Make sure you have:

- A GitHub account (free is fine... sign up at <https://github.com>).
- Git installed on your computer. If you don't have it yet, the videos linked in the [main README](https://github.com/adamrossnelson/confident_quizes/blob/main/README.md) walk you through it.
- A web browser (you've already got one which is what got you here!).
- A terminal app:
  - Mac: Open the Terminal app (press `Cmd + Space`, type "Terminal").
  - Windows: Use PowerShell, Command Prompt, or Git Bash (any of them work). (For Windows we recommend Git Bash).

---

## ✨ Why This Approach Is Easier

Compared to SSH keys, the GitHub CLI approach skips a lot of steps:

- ❌ No `ssh-keygen` and worrying about passphrases.
- ❌ No copying public keys into GitHub settings.
- ❌ No `ssh-agent` to start or troubleshoot.
- ❌ No accidentally pasting your private key somewhere it shouldn't go.
- ❌ No cryptic `Permission denied (publickey)` errors.

Instead: Install one tool, run one command, click "authorize" in your browser. ✅

---

## 🧭 Step-by-Step Instructions

### 📦 Step 1: Install the GitHub CLI

The GitHub CLI is a separate tool from Git. You need both:

- Git is the version-control program that tracks your changes.
- GitHub CLI (`gh`) is a friendly companion tool that handles things like logging in, cloning, and creating repositories.

Pick the instructions for your operating system below.

---

#### 🍎 On a Mac

The easiest way is with Homebrew, a popular Mac package manager.

Once Homebrew is ready, run (from the terminal):

```
brew install gh
```

That's it. ✅

You can also download the official installer directly:

1. Go to <https://cli.github.com>.
2. Click the Download for macOS button.
3. Open the `.pkg` file and follow the prompts (just like installing any other Mac app).

---

#### 🪟 On Windows

You have a few good options. Pick whichever feels easiest:

**Option A — winget (built into Windows 10 and 11):**

Open PowerShell or Command Prompt and run:

```
winget install --id GitHub.cli
```

**Option B — Direct installer:**

1. Go to <https://cli.github.com>.
2. Click the Download for Windows button.
3. Run the `.msi` installer like any other Windows program.

**Option C — Bundled with Git for Windows:**

If you're installing Git for Windows fresh (or reinstalling), the official installer at <https://git-scm.com> includes an option to install the GitHub CLI alongside Git. Look for the checkbox during setup. Two tools, one install.

---

#### ✅ Confirming It Worked

After installing, close and reopen your terminal, then run:

```
gh --version
```

You should see something like `gh version 2.x.x`. If you get "command not found," try closing the terminal completely and opening a fresh one. (Sometimes new tools aren't visible to terminals that were already open.)

---

### 🔑 Step 2: Run `gh auth login`

Now the magic happens. In your terminal, type:

```
gh auth login
```

The CLI will ask you a few questions. Here are the answers most students should pick:

1. **What account do you want to log into?**
   → Choose GitHub.com (unless your school uses GitHub Enterprise — your instructor will tell you if so).

2. **What is your preferred protocol for Git operations?**
   → Choose HTTPS. This is the easy path.

3. **Authenticate Git with your GitHub credentials?**
   → Choose Yes. This is the line that saves you from ever typing a password into `git push` again.

4. **How would you like to authenticate?**
   → Choose Login with a web browser.

The terminal will then show you a short one-time code (something like `ABCD-1234`) and tell you to press Enter to open your browser. Press Enter, your browser opens to a GitHub page, you paste in the code, click Authorize, and you're logged in. 🎉

---

### 📝 Step 3: Tell Git Who You Are

This step is separate from logging in. Telling Git who you are is about labeling your commits with your name and email so people can see who made what change. Run these two commands in your terminal, replacing the example info with your own:

```
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Use the same email address that's on your GitHub account so your commits will be linked to your profile.

---

### 🚀 Step 4: Try It Out!

You're done with setup. From now on, when you `git clone`, `git push`, or `git pull` from a private GitHub repository of your own, it'll just work. There should be no need for passwords, tokens, or SSH keys. The GitHub CLI silently provides credentials in the background.

To verify try:

```
gh auth status
```
---

## 🎁 Bonus: Cool Things You Can Do Now

The GitHub CLI has several handy shortcuts beyond authentication:

- **Clone a repo without typing the full URL**:
  `gh repo clone owner/repo-name`

- **Create a brand-new repo from your current folder**:
  `gh repo create`
  (Walks you through it interactively.)

- **Open the current repo in your web browser**:
  `gh repo view --web`

- **See your open pull requests**:
  `gh pr list`

You don't need any of these to complete this repository's sandbox quiz contribution but they're nice to know.

---

## ⚠️ A Few Things to Know

**Tokens expire eventually.** Once in a while (usually months later), you might be asked to log in again. If that happens, just run `gh auth login` again. Takes 30 seconds.

**WSL users on Windows**: If you use Windows Subsystem for Linux (WSL), it's a separate environment from regular Windows. You'll need to install `gh` *inside* WSL too (`sudo apt install gh` after adding GitHub's apt repository per the [official docs](https://github.com/cli/cli/blob/trunk/docs/install_linux.md)). If you've never heard of WSL, ignore this.

**Reminder: You can check your login status anytime** with:

```
gh auth status
```

This shows whether you're logged in, which account, and how Git is configured.

**Want to log out?** Run:

```
gh auth logout
```

---

## 🆘 Troubleshooting

**"Command not found: gh"** → The terminal can't find the GitHub CLI. Close and reopen your terminal. If still broken, the install didn't complete... try installing again.

**Browser didn't open automatically** → No worries. The terminal also prints a URL you can copy and paste into any browser manually.

**"Permission denied" when pushing** → If this happens after `gh auth login`, run `gh auth status` to confirm you're logged in. You may also need to run `gh auth setup-git` to make sure the credential helper is configured.

---

# Happy Authenticating! 🎉

That's it — you're authenticated and ready to push, pull, and contribute without password prompts ever again. Now go submit that quiz! 💻✨😄
