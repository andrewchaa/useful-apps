# Landing Page Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a two-file static landing page showcasing three open-source developer tools, hosted on GitHub Pages.

**Architecture:** Pure HTML + CSS, no JavaScript, no build step. `index.html` contains all markup and content; `styles.css` contains all styles. Three app cards in a responsive grid with a dark purple/indigo gradient theme.

**Tech Stack:** HTML5, CSS3 (custom properties, CSS Grid, media queries), GitHub Pages

---

## File Map

| File | Action | Responsibility |
|------|--------|----------------|
| `README.md` | Create | One-line site description |
| `styles.css` | Create | All styles — reset, layout, components, responsive |
| `index.html` | Create | All markup — hero, app grid, footer |

---

## Task 1: Initialize repository

**Files:**
- Create: `README.md`
- Create: `.gitignore`

- [ ] **Step 1: Create README.md**

```markdown
# useful-apps

Landing page for open-source macOS and CLI developer tools. Hosted at https://andrewchaa.github.io/useful-apps/
```

- [ ] **Step 2: Create .gitignore**

```
.DS_Store
.superpowers/
```

- [ ] **Step 3: Initialize git and commit**

```bash
cd /Users/youngho/github/useful-apps
git init
git add README.md .gitignore
git commit -m "chore: initialize repo"
```

---

## Task 2: Create styles.css

**Files:**
- Create: `styles.css`

- [ ] **Step 1: Create styles.css with the full stylesheet**

```css
/* styles.css */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

:root {
  --bg-gradient: linear-gradient(135deg, #1e1b4b 0%, #312e81 50%, #1e1b4b 100%);
  --accent-gradient: linear-gradient(90deg, #6366f1, #8b5cf6);
  --text-primary: #ffffff;
  --text-secondary: #c7d2fe;
  --text-muted: #a5b4fc;
  --text-dim: #6b7280;
  --card-bg: rgba(255, 255, 255, 0.06);
  --card-border: rgba(165, 180, 252, 0.2);
  --font: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
}

body {
  font-family: var(--font);
  background: var(--bg-gradient);
  min-height: 100vh;
  color: var(--text-secondary);
}

/* ── Hero ── */

.hero {
  text-align: center;
  padding: 72px 24px 64px;
  max-width: 680px;
  margin: 0 auto;
}

.hero__badge {
  display: inline-block;
  background: rgba(165, 180, 252, 0.15);
  border: 1px solid rgba(165, 180, 252, 0.3);
  color: var(--text-muted);
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 5px 14px;
  border-radius: 20px;
  margin-bottom: 24px;
}

.hero__title {
  font-size: 48px;
  font-weight: 800;
  color: var(--text-primary);
  line-height: 1.15;
  letter-spacing: -0.02em;
  margin-bottom: 16px;
}

.hero__title span {
  color: var(--text-muted);
}

.hero__subtitle {
  font-size: 17px;
  line-height: 1.7;
  color: var(--text-secondary);
}

/* ── App Grid ── */

.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  max-width: 980px;
  margin: 0 auto 64px;
  padding: 0 24px;
}

/* ── Card ── */

.card {
  background: var(--card-bg);
  border: 1px solid var(--card-border);
  border-radius: 16px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.card__screenshot {
  height: 140px;
  overflow: hidden;
  background: rgba(0, 0, 0, 0.25);
  display: flex;
  align-items: center;
  justify-content: center;
}

.card__screenshot img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card__screenshot--placeholder {
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--text-dim);
}

.card__body {
  padding: 22px;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.card__platform {
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--text-muted);
  margin-bottom: 8px;
}

.card__title {
  font-size: 19px;
  font-weight: 700;
  color: var(--text-primary);
  margin-bottom: 10px;
}

.card__description {
  font-size: 14px;
  line-height: 1.65;
  color: var(--text-secondary);
  flex: 1;
  margin-bottom: 20px;
}

.card__actions {
  display: flex;
  gap: 10px;
}

/* ── Buttons ── */

.btn--primary {
  flex: 1;
  background: var(--accent-gradient);
  color: #ffffff;
  padding: 10px 0;
  border-radius: 8px;
  font-size: 13px;
  font-weight: 600;
  text-align: center;
  text-decoration: none;
  display: block;
}

.btn--secondary {
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid var(--card-border);
  color: var(--text-muted);
  padding: 10px 16px;
  border-radius: 8px;
  font-size: 13px;
  font-weight: 500;
  text-decoration: none;
  white-space: nowrap;
  display: block;
}

.btn--primary:hover  { opacity: 0.9; }
.btn--secondary:hover { background: rgba(255, 255, 255, 0.12); }

/* ── Footer ── */

.footer {
  text-align: center;
  padding: 0 24px 40px;
  font-size: 13px;
  color: var(--text-dim);
}

.footer a {
  color: var(--text-muted);
  text-decoration: none;
}

.footer a:hover { color: var(--text-primary); }

/* ── Responsive ── */

@media (max-width: 768px) {
  .hero__title {
    font-size: 36px;
  }

  .grid {
    grid-template-columns: 1fr;
  }
}
```

- [ ] **Step 2: Commit**

```bash
git add styles.css
git commit -m "feat: add stylesheet with dark gradient theme"
```

---

## Task 3: Create index.html

**Files:**
- Create: `index.html`

- [ ] **Step 1: Create index.html with the full page markup**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Free, open-source macOS and CLI utilities built for developer productivity.">
  <title>Useful Apps</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <header class="hero">
    <div class="hero__badge">✦ Open Source</div>
    <h1 class="hero__title">Small tools.<br><span>Big workflow gains.</span></h1>
    <p class="hero__subtitle">Free, open-source macOS and CLI utilities built for developer productivity.</p>
  </header>

  <main class="grid">

    <article class="card">
      <div class="card__screenshot">
        <img
          src="https://raw.githubusercontent.com/andrewchaa/sprout-pomodoro/main/assets/screenshot.png"
          alt="Sprout Pomodoro screenshot"
          loading="lazy"
        >
      </div>
      <div class="card__body">
        <p class="card__platform">macOS · Menu Bar</p>
        <h2 class="card__title">Sprout Pomodoro</h2>
        <p class="card__description">A minimal Pomodoro timer that lives in your menu bar. Focus and break cycles with configurable durations and system notifications.</p>
        <div class="card__actions">
          <a class="btn--primary" href="https://github.com/andrewchaa/sprout-pomodoro/releases">Download</a>
          <a class="btn--secondary" href="https://github.com/andrewchaa/sprout-pomodoro">Source ↗</a>
        </div>
      </div>
    </article>

    <article class="card">
      <div class="card__screenshot card__screenshot--placeholder">CLI Tool</div>
      <div class="card__body">
        <p class="card__platform">CLI · Python</p>
        <h2 class="card__title">PR Agent</h2>
        <p class="card__description">Automated GitHub PR creation using Claude Haiku. Analyzes your diffs and generates intelligent PR descriptions from the command line.</p>
        <div class="card__actions">
          <a class="btn--primary" href="https://github.com/andrewchaa/pr-agent/releases">Download</a>
          <a class="btn--secondary" href="https://github.com/andrewchaa/pr-agent">Source ↗</a>
        </div>
      </div>
    </article>

    <article class="card">
      <div class="card__screenshot">
        <img
          src="https://raw.githubusercontent.com/andrewchaa/gcloud-session-watch/main/screenshot.png"
          alt="GCloud Session Watch screenshot"
          loading="lazy"
        >
      </div>
      <div class="card__body">
        <p class="card__platform">macOS · Menu Bar</p>
        <h2 class="card__title">GCloud Session Watch</h2>
        <p class="card__description">Shows time remaining before your Google Cloud Application Default Credentials expire, right in your menu bar. Color-coded warning states.</p>
        <div class="card__actions">
          <a class="btn--primary" href="https://github.com/andrewchaa/gcloud-session-watch/releases">Download</a>
          <a class="btn--secondary" href="https://github.com/andrewchaa/gcloud-session-watch">Source ↗</a>
        </div>
      </div>
    </article>

  </main>

  <footer class="footer">
    Open source · Free forever · <a href="https://github.com/andrewchaa">GitHub ↗</a>
  </footer>

</body>
</html>
```

- [ ] **Step 2: Open in browser and verify desktop layout**

```bash
open /Users/youngho/github/useful-apps/index.html
```

Check:
- Dark purple/indigo gradient covers full viewport
- Hero badge, h1, and subtitle centered and readable
- Three cards appear side-by-side in a row
- Sprout Pomodoro and GCloud Session Watch show their screenshots
- PR Agent shows "CLI TOOL" placeholder label
- Each card has platform badge, title, description, Download + Source buttons
- Footer shows at the bottom

- [ ] **Step 3: Verify mobile layout**

In the browser, open DevTools (Cmd+Option+I on macOS) → toggle device toolbar (Cmd+Shift+M) → set width to 375px.

Check:
- Cards stack vertically (one column)
- Hero title is 36px (smaller, still readable)
- No horizontal overflow or scrollbar

- [ ] **Step 4: Verify all links point to correct targets**

Check each href manually:
- Sprout Pomodoro Download → `https://github.com/andrewchaa/sprout-pomodoro/releases`
- Sprout Pomodoro Source → `https://github.com/andrewchaa/sprout-pomodoro`
- PR Agent Download → `https://github.com/andrewchaa/pr-agent/releases`
- PR Agent Source → `https://github.com/andrewchaa/pr-agent`
- GCloud Watch Download → `https://github.com/andrewchaa/gcloud-session-watch/releases`
- GCloud Watch Source → `https://github.com/andrewchaa/gcloud-session-watch`
- Footer GitHub → `https://github.com/andrewchaa`

- [ ] **Step 5: Commit**

```bash
git add index.html
git commit -m "feat: add landing page markup with three app cards"
```

---

## Task 4: Push to GitHub and enable Pages

**Prerequisite:** A GitHub repo named `useful-apps` must exist under the `andrewchaa` account. Create it at https://github.com/new if it doesn't exist — set it to Public, no template, no auto-init.

- [ ] **Step 1: Add remote and push**

```bash
git remote add origin https://github.com/andrewchaa/useful-apps.git
git branch -M main
git push -u origin main
```

Expected output ends with:
```
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

- [ ] **Step 2: Enable GitHub Pages**

1. Go to https://github.com/andrewchaa/useful-apps/settings/pages
2. Under **Source**, select **Deploy from a branch**
3. Branch: `main`, folder: `/ (root)`
4. Click **Save**

GitHub will show: "Your site is being published at `https://andrewchaa.github.io/useful-apps/`"

- [ ] **Step 3: Verify live site**

Wait ~60 seconds for Pages to deploy, then open:

```
https://andrewchaa.github.io/useful-apps/
```

Check that the page renders identically to the local file:// version.
