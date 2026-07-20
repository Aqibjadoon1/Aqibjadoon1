# Profile README — New Sections Setup Guide

Two automated sections were added to the README. Here's what you need to do (if anything) for each one.

---

## ✅ Sections that work automatically (no setup needed)

| Section | Workflow file | How it works |
|---|---|---|
| 📋 Recent GitHub Activity | `.github/workflows/update-readme-activity.yml` | Uses the built-in `GITHUB_TOKEN` GitHub provides every repo. Runs every 6 hours. Just push the file and it's live. |
| 📈 Activity Graph | None (live public API) | `github-readme-activity-graph.vercel.app` is a public API — it renders directly from your public GitHub data with no action or secret required. |
| 📊 Summary Cards | None (live public API) | `github-profile-summary-cards.vercel.app` is also a public API. No setup needed. |
| 😄 Dev Joke | None (live public API) | `readme-jokes.vercel.app` renders a random joke on every page load. No setup. |

---

## ⚙️ Section that requires manual setup

### ⏱️ Weekly Coding Activity (WakaTime)

The `<!--START_SECTION:waka-->` block in the README stays empty until you complete these steps:

**Step 1 — Create a WakaTime account**

Go to [https://wakatime.com](https://wakatime.com) and sign up for a free account.

**Step 2 — Install the WakaTime IDE plugin**

- **VS Code**: open the Extensions panel (`Ctrl+Shift+X`), search for **WakaTime**, and install it.
- **JetBrains / other IDEs**: see [https://wakatime.com/plugins](https://wakatime.com/plugins) for the full list.

After installing, the plugin will prompt you for your API key (step 3). WakaTime then silently tracks your coding time in the background.

**Step 3 — Copy your API key**

Visit [https://wakatime.com/settings/api-key](https://wakatime.com/settings/api-key) and copy the key shown there.

**Step 4 — Add the key as a GitHub repository secret**

1. Open your profile repo on GitHub: `github.com/Aqibjadoon1/Aqibjadoon1`
2. Go to **Settings → Secrets and variables → Actions**
3. Click **New repository secret**
4. Set:
   - **Name**: `WAKATIME_API_KEY`
   - **Value**: *(paste your key from step 3)*
5. Click **Add secret**

**Step 5 — Trigger the workflow**

Once the secret is saved the workflow (`.github/workflows/waka-readme.yml`) will run automatically every 24 hours. To see stats immediately, go to **Actions → WakaTime Readme Stats → Run workflow**.

> **Note:** WakaTime needs at least a few hours of tracked coding time before it has anything to display. The section will populate on the next workflow run after you've coded with the plugin active.

---

## 🔒 Secrets summary

| Secret name | Required by | How to get it |
|---|---|---|
| `WAKATIME_API_KEY` | `waka-readme.yml` | [wakatime.com/settings/api-key](https://wakatime.com/settings/api-key) |
| `GITHUB_TOKEN` | `update-readme-activity.yml` | Provided automatically by GitHub — no action needed |
