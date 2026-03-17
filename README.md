# Bracket Genie — March Madness Optimizer

Bracket Genie is a free, self-contained web app that generates an optimized March Madness bracket tailored to your pool. It blends Vegas odds, advanced analytics (KenPom efficiency margins), and public pick percentages to identify high-leverage upset picks that can separate your bracket from the chalk-heavy crowd. No account or subscription required — just open the site and fill out the form.

---

## How to Deploy to Vercel (No Technical Experience Required)

### Step 1 — Create a GitHub Repository

1. Go to [github.com](https://github.com) and sign in (or create a free account).
2. Click the **+** icon in the top-right corner and select **New repository**.
3. Give it any name (e.g., `bracket-genie`) and leave all other settings as default.
4. Click **Create repository**.
5. On the next page, click **uploading an existing file**.
6. Drag and drop all three project files (`index.html`, `vercel.json`, `README.md`) onto the upload area.
7. Click **Commit changes**.

### Step 2 — Deploy to Vercel

1. Go to [vercel.com](https://vercel.com) and sign in with your GitHub account (or create a free account).
2. Click **Add New Project**.
3. Under "Import Git Repository", find and select the `bracket-genie` repo you just created.
4. Leave **all settings as default** — do not change the framework, build commands, or output directory.
5. Click **Deploy**.
6. Wait about 60 seconds. Your site will be live at a URL like `bracket-genie.vercel.app`.

### Step 3 — Share Your Bracket Genie URL

Copy the URL Vercel gives you and share it with friends or your pool group. The site works on both desktop and mobile.

---

## Entering Public Pick Percentages

For the best results, paste public pick % data from the ESPN People's Bracket into the form:

**ESPN People's Bracket:** [https://fantasy.espn.com/games/tournament-challenge-bracket-2026/peoplesbracket](https://fantasy.espn.com/games/tournament-challenge-bracket-2026/peoplesbracket)

Look up each team's advancement percentage per round and paste them into the "Public Pick %" field in the app. The app will parse comma-separated or pipe-delimited formats (e.g., `Duke, 88, 75, 58, 22`).

---

## How to Update Data Each Year

The embedded odds and KenPom data are hardcoded for the 2026 NCAA Tournament. To generate a fresh version for the next tournament:

1. Re-run this Zenflow agent with updated instructions referencing the new season's ESPN odds and bracket URLs.
2. The agent will fetch live data, rebuild `index.html` with updated constants, and output a new project package.
3. Upload the new `index.html` to your GitHub repo (replace the old file).
4. Vercel will automatically redeploy within 60 seconds.

---

## Project Structure

```
bracket-genie/
├── index.html    ← The entire app (single-page, self-contained, no dependencies)
├── vercel.json   ← Vercel deployment configuration
└── README.md     ← This file
```

The app is 100% client-side — no server, no database, no API calls at runtime. It works fully offline after the initial page load (once Google Fonts cache).
