# Günter — Dein Deutsch-Tagebuch-Assistent

A persistent German diary practice app powered by Claude AI. Write daily entries in German, get real-time feedback on grammar and vocabulary, and track your progress over time. All data stays on your device.

**Live:** https://sfitzknott.github.io/gunter/

---

## Features

- 📝 **Daily Diary Prompts** — Structured templates to get you writing
- 🧠 **AI Feedback** — Claude analyzes your entries and corrects errors
- 📊 **Statistics** — Track word counts, streaks, and error patterns
- 🗣️ **Grammar Tips** — Targeted lessons based on your mistakes
- 📱 **Mobile-First** — Installable PWA—works offline, stores data locally
- 🔐 **Private** — All data stored in your browser (IndexedDB). No server uploads.

---

## Getting Started

### 1. Get an Anthropic API Key

Günter uses Claude AI, which requires an API key. Don't worry—the free tier covers personal diary writing easily.

1. Visit [console.anthropic.com/keys](https://console.anthropic.com/keys)
2. Sign up (or log in) with your Google/email
3. Create a new API key
4. Copy the key (starts with `sk-ant-`)

### 2. Launch Günter with Your Key

**Option A: URL Query Parameter (Easiest)**

Open this URL in your browser and replace `YOUR_API_KEY`:

```
https://sfitzknott.github.io/gunter/?apikey=sk-ant-YOUR_API_KEY
```

The app will:
- Load your key automatically
- Store it securely in IndexedDB (local storage)
- Remove the key from the URL
- Never send it to any server

Bookmark this URL for future visits. You only need to do this once.

**Option B: Manual Command**

If you prefer not to use a URL parameter:

1. Open https://sfitzknott.github.io/gunter/
2. Type: `apikey sk-ant-YOUR_API_KEY`
3. Press send

Your key is now saved locally.

### 3. Start Writing

Type `template` to get today's diary prompt. Write freely, and Günter will:
- Correct grammar errors
- Suggest vocabulary improvements
- Track your progress

---

## How It Works

### Commands

| Command | What it does |
|---|---|
| `apikey [key]` | Save your Anthropic API key |
| `template` | Generate today's structured diary prompt |
| `goal [n]` | Set daily word target (100–1000) |
| **Word Count** | — |
| `wc` | Words written today |
| `wc-w`, `wc-m`, `wc-y` | This week/month/year |
| **Feedback** | — |
| `errors` | All grammar mistakes logged |
| `errors-w`, `errors-m` | Errors this week/month |
| `tip` | Personalized grammar lesson |
| `vocab` | Vocabulary from today |
| `vocab-w`, `vocab-m` | This week/month |
| **Progress** | — |
| `streak` | Consecutive days written |
| `progress` | Quick stats dashboard |
| `stats` | Full statistics tab |
| **History** | — |
| `history [date]` | Retrieve a past entry |
| `review [date]` | Past entry + original feedback |
| **Data** | — |
| `export` | Download all entries as JSON |
| `import` | Restore from JSON backup |
| **Other** | — |
| `help` | Show all commands |
| `help [cmd]` | Details on a specific command |
| `reset-level` | Reset difficulty assessment |

### Error Correction

Günter categorizes errors by severity:

- **Tier 1** — Meaning is lost (always corrected)
- **Tier 2** — Sounds wrong to a native speaker (corrected)
- **Tier 3** — Technically incorrect but understandable (gently noted)

Each correction includes:
- Your mistake in context
- The correct version in German
- A brief explanation in English

### Data Storage

- **Stored locally** in your browser's IndexedDB
- **Never uploaded** to any server
- **Persists** across browser sessions
- **Backed up** by you using `export`

Use `export` regularly to download a JSON snapshot of all your entries. Keep it on Google Drive, Dropbox, or your local machine.

---

## API Key Security

Your API key is:
- ✓ Stored locally on your device only
- ✓ Never sent to any server except Anthropic's API directly
- ✓ Never included in GitHub commits or browser history
- ✓ Safe to use in a query parameter on your own device

**Best practice:** Use the URL parameter method on **your own devices only**. Don't share the URL with the key in it publicly.

---

## Using Multiple Devices

If you want to use Günter on multiple devices (phone + tablet), generate separate bookmarks:

```
https://sfitzknott.github.io/gunter/?apikey=sk-ant-YOUR_KEY
```

Each device will store the key independently. Data does not sync between devices—each browser maintains its own diary.

To keep data in sync:
1. Regularly `export` from one device
2. Paste into a shared file (Google Drive, Dropbox)
3. `import` on other devices when needed

---

## Development / Self-Hosting

Günter is a single-file app (`index.html`). No build tools, no npm, no frameworks.

To make changes:

1. Clone this repo:
   ```bash
   git clone https://github.com/sfitzknott/gunter.git
   cd gunter
   ```

2. Edit `index.html` in your code editor

3. Test locally:
   ```bash
   # Option A: Open in browser
   open index.html
   
   # Option B: Simple local server (Python)
   python3 -m http.server 8000
   # Then open http://localhost:8000
   ```

4. Push to GitHub:
   ```bash
   git add .
   git commit -m "Your change"
   git push
   ```

5. GitHub Pages updates automatically (~30 seconds)

### Tech Stack

- **Single HTML file** — vanilla HTML, CSS, JavaScript
- **No build tools** — works directly in the browser
- **IndexedDB** — client-side data persistence
- **Claude API** — AI analysis and feedback via Anthropic
- **PWA** — installable on home screen (iOS/Android)

---

## FAQ

**Q: Is my diary private?**
Yes. All data stays in your browser's local storage. Nothing is sent to any server except your actual diary text and corrections to Anthropic's API (which they use per their [privacy policy](https://www.anthropic.com/privacy)).

**Q: Can I use this offline?**
Partially. The app loads offline, and you can read old entries. But writing new entries and getting AI feedback require an internet connection to reach Claude's API.

**Q: Can I restore entries if I clear my browser data?**
Only if you've exported. Always keep regular backups with `export`.

**Q: What's my API key usage like?**
A typical diary entry (~200 words) costs ~$0.01 using Claude 3.5 Sonnet. Günter is optimized to keep calls small. Anthropic's free tier usually gives you enough for months of daily use.

**Q: Can I share my bookmarked URL with others?**
⚠️ **No.** Your API key is in the URL. Anyone with that URL can use your API credits. Only share the base URL without the `?apikey=` part.

**Q: Can I self-host this?**
Yes! The app is static HTML. Upload `index.html`, `manifest.json`, and `icon.svg` to any web server (GitHub Pages, Netlify, Vercel, your own server, etc).

---

## Support

- Check `help` inside the app for command details
- Review your error log (`errors` command) to see patterns
- Export and inspect your data to troubleshoot issues

---

## License

Personal use. All rights reserved.

