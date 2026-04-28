# Build your first website with Claude Code

This is a beginner's starter kit. By the end of it you'll have a personal website — your name, photo, bio, projects, resume — live on the internet at `https://<your-username>.github.io`. Claude Code will write the actual website for you. You'll mostly be giving it instructions in plain English.

You do not need to know any programming. If you can copy and paste, you can do this.

## What you'll build

A simple, fast portfolio site. Look at [nickwagner.info](https://nickwagner.info/) to see roughly what the finished product looks like. The [example-site/](example-site/) folder is the code for this.

## What it'll cost

- **Claude Pro subscription:** about $20/month. You need this to use Claude Code.
- **GitHub account:** free.
- **GitHub Pages hosting:** free.

That's it. No domain registration, no other services.

## Glossary (skim once, refer back as needed)

- **Repository (or "repo"):** a folder of files tracked by Git. Lives both on your computer and on GitHub.
- **GitHub:** a website where code repos live. We'll host your site here.
- **GitHub Pages:** a free GitHub feature that turns a repo into a public website.
- **Git:** a tool that records changes to files. You won't run it directly — Claude Code will.
- **Claude Code:** an app from Anthropic that lets Claude write and run code on your computer.
- **Commit:** a snapshot of your files saved to Git's history.
- **Push:** uploading your commits from your computer to GitHub.
- **Terminal:** a window where you type commands. Claude Code has one built in.

---

## Part 1 — Accounts and tools (one-time setup, ~20 min)

You only have to do this part once. Skip any step you've already done.

### 1. Create a GitHub account

Go to **https://github.com/signup** and create an account. **Write down your username** — you'll use it to name your repo in Part 2, and it becomes part of your website's URL.

### 2. Subscribe to Claude Pro

Go to **https://claude.ai/upgrade** and subscribe to Claude Pro (about $20/month). Pro is required to use Claude Code with reasonable usage limits.

### 3. Install Claude Code Desktop

Go to **https://claude.ai/download** and download the Claude desktop app for your operating system (Mac or Windows). Install it, open it, and sign in with the same account you used for Claude Pro.

When the app is open, find the **Claude Code** view (sidebar). This is where you'll do all your work.

### 4. Install Git

Git is a separate tool that Claude Code uses behind the scenes.

- **Mac:** open Claude Code, type the message: *"Please check whether Git is installed by running `git --version`."* If it isn't installed, Claude Code will guide you through installing it (usually by accepting macOS's prompt to install the Command Line Tools).
- **Windows:** download and run the installer at **https://git-scm.com/download/win**. Click "Next" through every screen with default options. Then restart Claude Code.

### 5. Verify everything works

In Claude Code, send this message:

```
Please run `git --version` and tell me the output.
```

You should see something like `git version 2.x.x`. If you do, you're ready.

---

## Part 2 — Create your site's repo on GitHub (~5 min)

GitHub has a special rule: if you name a repo `<your-username>.github.io`, it automatically becomes a free website at `https://<your-username>.github.io`. We'll use that.

1. Go to **https://github.com/new**.
2. In **Repository name**, type your GitHub username followed by `.github.io`, exactly. For example, if your username is `janedoe`, type `janedoe.github.io`.
3. Set the repo to **Public**.
4. Leave **Add a README**, **.gitignore**, and **license** *unchecked*. We want it empty.
5. Click **Create repository**.
6. On the next page, **copy the URL at the top** (it looks like `https://github.com/janedoe/janedoe.github.io`). You'll need it in Part 3.

---

## Part 3 — Get this starter kit and your repo onto your computer (~5 min)

In Claude Code, pick a folder where your projects will live (anywhere is fine — creating `~/Documents/websites` is a good default). Then send Claude Code this message, **replacing the username and URL with your own**:

```
I want to set up two folders inside ~/Documents/websites.

1. Clone https://github.com/Learning-Journey-AI/first-ai-made-website into a folder called "first-ai-made-website".
2. Clone https://github.com/<YOUR-USERNAME>/<YOUR-USERNAME>.github.io into a folder called "<YOUR-USERNAME>.github.io" right next to it.
3. Copy the file CLAUDE.md from first-ai-made-website into <YOUR-USERNAME>.github.io.

Then show me the folder structure so I can confirm.
```

When it's done you should have two folders side by side:

```
~/Documents/websites/
├── first-ai-made-website/      ← this starter kit
└── <YOUR-USERNAME>.github.io/  ← your empty site repo, with a CLAUDE.md inside
```

---

## Part 4 — Add your stuff to context-files/

Open [context-files/](context-files/) inside `first-ai-made-website` (your file manager — Finder on Mac, Explorer on Windows — works fine).

Drag in:

- **Your resume.** PDF, Word, plain text — any format.
- **A photo of yourself.** Any photo you'd be happy to put on a website. JPG or PNG.
- **(Optional) A bio.** A `.txt` or `.md` file with a paragraph or two about yourself. If you skip this, Claude will write one from your resume.
- **(Optional) Project notes.** A list of projects you want to feature, one per paragraph.
- **(Optional) Links.** A `links.txt` with your LinkedIn, email, social profiles, etc.

File names don't matter. Drop in whatever you have — Claude Code will figure it out.

---

## Part 5 — Have Claude Code build your site (~15 min)

In Claude Code, **switch the working folder to your site repo**. Open the folder `<YOUR-USERNAME>.github.io/` directly in Claude Code.

Then send this **starter prompt** (copy and paste the whole thing):

```
I want you to build a personal portfolio website for me.

- Read every file in ../first-ai-made-website/context-files/ to learn about me.
- Look at ../first-ai-made-website/example-site/ as a structural and stylistic reference (do NOT deploy it — it belongs to someone else).
- Build my site as plain HTML, CSS, and vanilla JavaScript with no build step (no React, no npm install, no frameworks). It must work as a github io website.
- Write all output files into the current folder.
- Copy my resume into assets/ and my photo into assets/img/.
- Before you start writing files, summarize what you found in my context-files and ask me 3–5 clarifying questions about style, tone, and which projects to feature. Wait for my answers before building.
```

Claude will ask you questions — answer them in plain language. Then it'll build the site. This usually takes a few minutes.

**Tips:**
- Don't like something? Just tell Claude: *"Make the colors warmer."* / *"Move my photo to the about page."* / *"Make the headline bigger."*
- You can iterate as many times as you want. The site only "exists" on GitHub once you push it (Part 7).

---

## Part 6 — Preview your site locally

Send Claude Code:

```
Please start a local web server on port 8000 from the current folder so I can preview my site.
```

Open **http://localhost:8000** in your browser. You should see your site. When you're done previewing, come back to Claude Code and send `Stop the server.`

Look it over. Fix anything you don't like by asking Claude.

---

## Part 7 — Push to GitHub and go live

When you're happy with the site, send Claude Code:

```
Please commit all the files in this folder with a sensible commit message, then push to the GitHub repo.
```

Claude will ask for confirmation before pushing. 

Then, in your browser:

1. Go to your repo on GitHub: `https://github.com/<YOUR-USERNAME>/<YOUR-USERNAME>.github.io`.
2. Click **Settings** (top of the page).
3. Click **Pages** in the left sidebar.
4. Confirm **Source** is set to **"Deploy from a branch"** and **Branch** is **main / (root)**. If it isn't, set it and click Save.
5. Wait 1–2 minutes.
6. Visit `https://<YOUR-USERNAME>.github.io` in your browser.

**Your site is live.** Share the URL with anyone.

---

## Part 8 — Make changes later

Whenever you want to update the site:

1. Open Claude Code in the `<YOUR-USERNAME>.github.io/` folder.
2. Tell it what to change in plain English. *("Add a new project called X."  / "Change my bio.")*
3. When it's done, tell it: *"Commit and push."*
4. Wait a minute. The live site updates automatically.

You can also drop new files into `../first-ai-made-website/context-files/` and ask Claude to re-read them.

---

## Troubleshooting

**My site URL shows a 404 page.**
- Wait 2–3 more minutes. The first deploy can take a moment.
- Double-check the repo name is *exactly* `<your-username>.github.io` — no typos, all lowercase, matches your username exactly.
- Check **Settings → Pages** in the repo and confirm Source is "Deploy from a branch / main / (root)".

**Claude Code says "git: command not found".**
- Re-do step 4 of Part 1 to install Git, then close and reopen Claude Code.

**I pushed but the site didn't update.**
- Open the repo on GitHub and check the **Actions** tab — there'll be a "pages build and deployment" run. If it failed, click into it for the error.
- It can take up to 5 minutes for changes to appear after a successful deploy.

**Claude is suggesting I install something.**
- Go ahead and allow it. If you want to understand what Claude is asking for, copy its request to another chat and ask what it does.  
