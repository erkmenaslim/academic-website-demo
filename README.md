# Academic Website Builder — Live Demo & Free Skill

**Turn a CV into a polished academic website in minutes — no frameworks, no servers, no web tooling.**

[![View Live Demo](https://img.shields.io/badge/▶_View-Live_Demo-1F3A5F?style=for-the-badge)](https://erkmenaslim.github.io/academic-website-demo/)
[![Download the Skill](https://img.shields.io/badge/⤓_Download-The_Skill-f4a01c?style=for-the-badge)](https://erkmenaslim.github.io/academic-website-demo/academic-website-builder-skill.zip)
&nbsp;
![Built with Claude Code](https://img.shields.io/badge/Built_with-Claude_Code-6C5CE7)
![Python 3](https://img.shields.io/badge/Python-3.8%2B-blue)
![No dependencies](https://img.shields.io/badge/dependencies-none-brightgreen)

This repo is **two things at once**:

1. 🌐 **A live demo academic website** — every page generated entirely from one CV.
   → **[erkmenaslim.github.io/academic-website-demo](https://erkmenaslim.github.io/academic-website-demo/)**
2. 📦 **The skill that built it** — free to download and use with [Claude Code](https://claude.com/claude-code).

> The person on the demo site, *"Adam Smith, Stockholm University,"* is **fictitious** — a worked
> example created to show off the skill. No real person, publications, or affiliations.

---

## 📦 Get the skill (free)

**Option 1 — Download the zip**

→ **[academic-website-builder-skill.zip](https://erkmenaslim.github.io/academic-website-demo/academic-website-builder-skill.zip)**

Unzip it and drop the `academic-website-builder/` folder into your Claude skills directory
(`~/.claude/skills/`).

**Option 2 — Clone & install from this repo**

```bash
git clone https://github.com/erkmenaslim/academic-website-demo.git
cp -r academic-website-demo/skill/academic-website-builder ~/.claude/skills/
```

**Then just ask Claude:**

```
Turn my CV into an academic website.
```

The skill source lives in [`skill/academic-website-builder/`](skill/academic-website-builder).

---

## ✨ What the skill does

You hand Claude a CV (PDF or DOCX); it extracts your publications, working papers, teaching,
advising, media coverage, bio, and links — then generates a clean, self-contained site.

- **One CV in → a real website out.** No copy-pasting into a template.
- **Three distinct designs, built every time** so you choose by *seeing* them with your content:
  | Theme | Vibe |
  |---|---|
  | **minimal-dark** | Charcoal + accent; research as a typed "ledger." Restrained, design-forward. |
  | **light-academic** | Cool paper + green, literary serif, card-based. Scholarly. |
  | **bold-modern** | Full-width bands, oversized type, a scrolling press "ticker." High-impact. |
- **One source of truth:** everything lives in **`cv-data.json`**.
- **One command to (re)build:** `python build.py` — regenerates the whole site in ~1 second.
- **No frameworks, no build pipeline, no dependencies** beyond Python 3.

---

## 🔁 Updating your site takes seconds

This is the whole point — **edit one file, run one command.** No HTML.

1. Open **`cv-data.json`** and make your change (add a paper, fix a title, update your bio).
2. Rebuild:
   ```bash
   python build.py
   ```
3. Publish (if hosted on GitHub Pages):
   ```bash
   git add -A && git commit -m "Update CV" && git push
   ```
   Pages auto-rebuilds in ~1 minute. Done.

**One-line tweaks (just edit `cv-data.json`):**

| Want to… | Change |
|---|---|
| Switch the whole design | `"theme": "minimal-dark" \| "light-academic" \| "bold-modern"` |
| Add a headshot | `"photo": "assets/your-photo.jpg"` |
| Add a profile link | add the URL under `"links"` (Scholar, ORCID, LinkedIn, …) |
| Add a paper | add one object to the `"publications"` list |
| Update the bio | edit `"bio"` (short / standard / extended) |

**Got a freshly updated CV?** Open the folder with Claude Code and say
*"update my website from my new CV"* — it refreshes `cv-data.json` for you (keeping your design,
photo, and links) and rebuilds.

---

## 🚀 Deploy anywhere (it's just static files)

The output is plain HTML, so it can be hosted free, with HTTPS, almost anywhere.

- **GitHub Pages** *(used for this demo)* — push the folder to a repo, then
  **Settings → Pages → Deploy from a branch → `main` / root**. Live at
  `https://<username>.github.io/<repo>/` in ~1 minute. *(An empty `.nojekyll` file serves all files raw.)*
- **Netlify** — drag-and-drop the folder for an instant URL, or connect the repo for auto-deploy.
- **Cloudflare Pages** — connect the repo, serve as-is; fast global CDN.
- **Vercel** — connect the repo, framework preset "Other," static output.
- **Just the files** — open `index.html` locally or host whenever; it works offline too.

All of these support a **custom domain** (e.g. `yourname.com`) with free HTTPS.

---

## 🗂️ What's in this repo

```
academic-website-demo/
├── index.html                 # the LIVE site (bold-modern theme) — what GitHub Pages serves
├── preview.html               # side-by-side chooser of all three themes
├── site-*.html                # the three generated themes
├── cv-data.json               # ← single source of truth for the demo site
├── build.py                   # `python build.py` rebuilds everything (~1s)
├── templates/                 # the three theme templates
├── assets/                    # headshot / images
├── CV/                        # the demo CV (PDF), linked as the download
├── academic-website-builder-skill.zip   # ⤓ the downloadable skill
└── skill/academic-website-builder/       # the skill source (clone & install)
```

---

## 🙋 FAQ

**Do I need to know how to code?** No. You edit one JSON file and run one command. Claude can do
even that for you if you ask.

**Is it really free?** Yes — the skill and the generated site are free and self-contained. Hosting on
GitHub Pages / Netlify / Cloudflare Pages is free too.

**Can I change the design?** Pick one of the three themes in one line, or edit a theme's template in
`templates/` for deeper changes (colors live in the CSS `:root` variables).

---

<sub>Built with [Claude Code](https://claude.com/claude-code) using the **academic-website-builder** skill.
The demo subject, "Adam Smith," is fictitious — created purely to demonstrate the skill.</sub>
