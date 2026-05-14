# Günter — Dein Deutsch-Tagebuch-Assistent

A persistent German diary practice app powered by Claude AI.

## Project Structure

```
gunter/
├── index.html      ← The entire app
├── manifest.json   ← PWA manifest (home screen install)
├── icon.svg        ← App icon
└── README.md       ← This file
```

## Setup Guide

### Step 1 — Create the GitHub repository

1. Go to [github.com](https://github.com) and log in
2. Click the **+** button (top right) → **New repository**
3. Name it exactly: `gunter`
4. Set it to **Public** (required for free GitHub Pages)
5. Do **not** tick "Add README" — leave everything unchecked
6. Click **Create repository**

---

### Step 2 — Open the project in VSCode

1. Open **VSCode**
2. Open the terminal: `` Ctrl+` `` (backtick)
3. Navigate to where you want the project to live, e.g.:
   ```
   cd ~/Documents
   ```
4. Clone or initialise — since you already have the files, run:
   ```
   git init gunter
   cd gunter
   ```
5. Copy the project files (`index.html`, `manifest.json`, `icon.svg`, `README.md`) into this `gunter` folder

---

### Step 3 — Push to GitHub

In the VSCode terminal, run these commands one by one:

```bash
git add .
git commit -m "Initial Günter deploy"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/gunter.git
git push -u origin main
```

⚠️ Replace `YOUR_GITHUB_USERNAME` with your actual GitHub username.

---

### Step 4 — Enable GitHub Pages

1. Go to your repository on GitHub: `github.com/YOUR_USERNAME/gunter`
2. Click **Settings** (top tab)
3. In the left sidebar, click **Pages**
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**
6. Wait 1-2 minutes — GitHub will show you your live URL:
   ```
   https://YOUR_USERNAME.github.io/gunter/
   ```

---

### Step 5 — Open on your phone

1. Open that URL in your mobile browser
2. Bookmark it, or use **Add to Home Screen** for an app-like shortcut
3. Data is stored in your browser's IndexedDB — it persists across sessions as long as you use the same browser

---

## Making Updates

Any time you want to change something:

1. Edit the files in VSCode
2. In the terminal:
   ```bash
   git add .
   git commit -m "describe your change"
   git push
   ```
3. GitHub Pages updates automatically within ~30 seconds

---

## Data Backup

Type `export` inside Günter to download a JSON snapshot of all your entries, error log, and stats. Keep this somewhere safe (Google Drive, etc). To restore, type `import` and paste the JSON.

---

## Commands

| Command | Description |
|---|---|
| `template` | Generate today's diary template |
| `goal [n]` | Set word target (100/150/200/300/500/1000) |
| `wc` | Word count today |
| `wc-w` / `wc-m` / `wc-y` | Word count this week/month/year |
| `errors` | Error log grouped by category |
| `errors-w` / `errors-m` | Errors this week/month |
| `tip` | Targeted grammar tip |
| `vocab` | Vocabulary from today |
| `vocab-w` / `vocab-m` | Vocab this week/month |
| `streak` | Consecutive days written |
| `progress` | Dashboard overview |
| `stats` | Open statistics tab |
| `history [date]` | Retrieve a past entry |
| `review [date]` | Past entry with original feedback |
| `export` | Export all data as JSON |
| `import` | Restore from JSON snapshot |
| `reset-level` | Reset Günter's level assessment |
| `help` | Show all commands |
| `help [command]` | Detail on a specific command |
