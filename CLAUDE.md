# Instructions for Claude Code

You are helping a user who is **brand new to programming** build a personal portfolio website. This file tells you exactly how to behave. Read it fully before doing anything else.

## Audience

The user has never written code. Explain every choice in plain English. Avoid jargon unless you define it in the same sentence. When you ask the user a question, give them concrete options to pick from rather than open-ended prompts.

## What you are building

A simple, static personal website that will be deployed to GitHub Pages at `https://<their-username>.github.io`.

## Stack — strict constraints

- **Plain HTML, CSS, and vanilla JavaScript only.**
- **No build step.** No `npm install`, no bundlers, no compilers.
- **No frameworks.** No React, Next.js, Vite, Svelte, Astro, Jekyll, Hugo, or anything that needs to be built before deploying.
- **CSS:** a single `assets/css/styles.css` is preferred. Tailwind via the CDN `<script>` tag is acceptable if the user wants utility classes. 
- **JS:** a single `assets/js/main.js` is fine. If you need data (e.g. a list of projects), put it in `assets/data/projects.json` and load it with `fetch`.
- The site must work when you open `index.html` directly in a browser.

These constraints exist because GitHub Pages serves static files only and the user cannot debug a broken build pipeline.

## Inputs

- `context-files/` — the user's raw materials (resume, photo, bio, project notes, links). Read every file in this folder. Treat it as the ground truth for the user's life and work.
- `example-site/` — a reference example showing structure and style. Model the user's site on this. **Do not edit it. Do not deploy it.** It is someone else's website.

## Output location

Write the user's site files into the **current working directory** (their `<username>.github.io/` repo). Do not write site files anywhere else.

## Required pages and behaviors

- At minimum: `index.html` with the user's name, photo, a short intro, and links to anything else they have (resume, projects, contact).
- Strongly encouraged if the context supports it: an about page, a projects page, a contact page.
- The resume must be linked from the site. Copy the resume file into the user's site repo (e.g. `assets/resume.pdf`).
- The user's photo must be displayed somewhere prominent. Copy the photo into `assets/img/`.
- Add a `.gitignore` that ignores `.DS_Store`, `Thumbs.db`, and editor folders (`.vscode/`, `.idea/`).

## How to start

1. Read every file in `context-files/`. Summarize back to the user what you found, in 3–5 bullets.
2. Ask the user 3–5 clarifying questions. Suggested topics:
   - Color and tone (warm and friendly? clean and minimal? bold?)
   - Which projects to feature on the home page
   - Whether they want a contact form (email link is simpler) or just an email/LinkedIn link
   - Whether to include a photo on the home page or only on the about page
   - Anything they want left **out**
3. Propose a structure (which pages, what goes on each). Wait for confirmation.
4. Build the site.
5. Show the user how to preview it locally and tell them how it looks before they commit.

## What not to do

- Do not add analytics, tracking pixels, or third-party scripts beyond fonts and Tailwind CDN.
- Do not add a backend, database, or server-side anything.
- Do not suggest paid services (custom domains, Netlify Pro, Vercel Pro, etc.).
- Do not invent projects, jobs, skills, or credentials the user's resume does not support.
- Do not generate large lorem-ipsum filler. If you don't have content for a section, ask the user or leave the section out.

## Local preview

When the user wants to preview the site, run a static server from the site root:

```
python3 -m http.server 8000
```

Then tell them to open `http://localhost:8000` in their browser. If `python3` isn't available, try `python -m http.server 8000` or `npx --yes serve`.

## Deploying

GitHub Pages serves the `main` branch root automatically once the repo is named `<username>.github.io`. After the user pushes, tell them to:

1. Open the repo on GitHub.
2. Click **Settings → Pages**.
3. Confirm Source is **Deploy from a branch** and Branch is **main / (root)**.
4. Wait 1–2 minutes, then visit `https://<username>.github.io`.
