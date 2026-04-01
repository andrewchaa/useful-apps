# Landing Page Design Spec

**Date:** 2026-04-01  
**Project:** useful-apps static landing page  
**Hosting:** GitHub Pages (main branch root)

---

## Purpose

A static landing page for developers to discover and install three open-source macOS and CLI tools. The primary goal is to help developers quickly understand what each app does and navigate to its GitHub Releases page to download it.

No personal branding. App-focused.

---

## Apps

### Sprout Pomodoro
- **Repo:** https://github.com/andrewchaa/sprout-pomodoro
- **Platform:** macOS · Menu Bar
- **Description:** A minimal Pomodoro timer that lives in your menu bar. Focus and break cycles with configurable durations and system notifications.
- **Screenshot:** `https://raw.githubusercontent.com/andrewchaa/sprout-pomodoro/main/assets/screenshot.png`
- **Releases:** https://github.com/andrewchaa/sprout-pomodoro/releases

### PR Agent
- **Repo:** https://github.com/andrewchaa/pr-agent
- **Platform:** CLI · Python
- **Description:** Automated GitHub PR creation using Claude Haiku. Analyzes your diffs and generates intelligent PR descriptions from the command line.
- **Screenshot:** None — show "CLI TOOL" label placeholder
- **Releases:** https://github.com/andrewchaa/pr-agent/releases

### GCloud Session Watch
- **Repo:** https://github.com/andrewchaa/gcloud-session-watch
- **Platform:** macOS · Menu Bar
- **Description:** Shows time remaining before your Google Cloud Application Default Credentials expire, right in your menu bar. Color-coded warning states.
- **Screenshot:** `https://raw.githubusercontent.com/andrewchaa/gcloud-session-watch/main/screenshot.png`
- **Releases:** https://github.com/andrewchaa/gcloud-session-watch/releases

---

## Visual Style

- **Background:** Dark gradient — `linear-gradient(135deg, #1e1b4b, #312e81, #1e1b4b)`
- **Accent color:** Indigo/purple — `#6366f1` to `#8b5cf6` gradient for primary buttons
- **Text:** White headings, `#c7d2fe` body, `#a5b4fc` labels and secondary elements
- **Cards:** Semi-transparent white (`rgba(255,255,255,0.06)`) with soft indigo border
- **Font:** System font stack (`-apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`)

---

## Page Structure

```
Hero
  badge: "✦ Open Source"
  h1: "Small tools. Big workflow gains."
  subtitle: "Free, open-source macOS and CLI utilities built for developer productivity."

App Grid (3 columns on desktop, stacked on mobile)
  [Sprout Pomodoro card]
  [PR Agent card]
  [GCloud Session Watch card]

Footer
  "Open source · Free forever · GitHub ↗" (links to https://github.com/andrewchaa)
```

### App Card Structure (per card)
1. Screenshot area — image if available, "CLI TOOL" label if not
2. Platform badge (e.g. "macOS · Menu Bar")
3. App name (h3)
4. Short description (2 sentences)
5. Two action buttons: **Download** (links to `/releases`) + **Source ↗** (links to repo)

---

## File Structure

```
useful-apps/
  index.html      — semantic markup and app content
  styles.css      — all styles
  README.md       — one-line description of the site
```

No build step. No JavaScript required. No external dependencies.

---

## Responsive Behavior

- **≥ 768px:** 3-column card grid
- **< 768px:** Single-column stacked cards

---

## GitHub Pages Deployment

Enable GitHub Pages on the `main` branch root in repository Settings → Pages. No build step or workflow required — the static files are served directly.

---

## Out of Scope

- Dynamic GitHub API calls
- Personal branding or author attribution
- More than one page
- JavaScript
