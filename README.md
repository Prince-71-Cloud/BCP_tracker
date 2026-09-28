# 🛡️ BSCP Tracker

A free, open-source study tracker for the **Burp Suite Certified Practitioner (BSCP)** exam.

Plan your preparation, sync your solved PortSwigger labs automatically, log your mystery-lab practice, and keep a personal cheat sheet of working payloads, all in one page that runs entirely in your browser.

> **🔒 Privacy first:** This tool **never asks for your PortSwigger password**. It has no server, no login, no analytics, and no tracking. Your progress is stored only in your own browser.

**▶ Live demo:** https://prince-71-cloud.github.io/BCP_tracker/ *(available once GitHub Pages is enabled, see [For the maintainer](#for-the-maintainer))*

---

## Table of contents

- [Features](#features)
- [Quick start](#quick-start)
- [Step 1: Open the tracker](#step-1-open-the-tracker)
- [Step 2: Install the Sync bookmark (one time)](#step-2-install-the-sync-bookmark-one-time)
- [Step 3: Sync your solved labs](#step-3-sync-your-solved-labs)
- [Using the tracker](#using-the-tracker)
- [How the readiness score works](#how-the-readiness-score-works)
- [Where your data is stored](#where-your-data-is-stored)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)
- [Privacy and security](#privacy-and-security)
- [Contributing](#contributing)
- [For the maintainer](#for-the-maintainer)
- [Disclaimer](#disclaimer)
- [License](#license)

---

## Features

- **8-week study plan** in three phases: cover every topic, master the 8 key labs PortSwigger recommends, then simulate the exam.
- **One-click sync** from your PortSwigger account using a bookmarklet. Solved labs are checked off automatically, with no password required.
- **Readiness ring** showing how prepared you are across topics, mystery labs, and exam steps.
- **Mystery lab log** to record each cold-recon attempt, its result, and how long it took.
- **Cheat sheet** to save working payloads, tagged by exam stage (user access, admin access, reading the file).
- **Exam-day rules** pinned for quick review.
- **Export and import** your progress as files, to back it up, move between computers, or save your payloads as a Markdown cheat sheet.
- **Dark and light mode**, following your system setting.
- **Works offline** as a single HTML file, with nothing to install.

---

## Quick start

1. Open the [live demo](https://prince-71-cloud.github.io/BCP_tracker/), or download `index.html` and open it in your browser.
2. Drag the **Sync BSCP** button to your bookmarks bar.
3. Log in to PortSwigger, open the **All labs** page, and click the bookmark.
4. Paste the copied data into the tracker and click **Import**.

That's it. The detailed steps are below.

> 💻 **Use a desktop or laptop.** Bookmarklets are difficult to use on phones and tablets. Chrome, Edge, Firefox, and Brave all work.

---

## Step 1: Open the tracker

Choose one of these options:

**Option A: Use the live version (easiest)**
Visit https://prince-71-cloud.github.io/BCP_tracker/. Bookmark the page so you can come back to it.

**Option B: Run it locally**
1. Download `index.html` from this repository. Click the file, then click the **Download raw file** button.
2. Save it somewhere permanent, such as `Documents/BSCP/`.
3. Double-click the file to open it in your browser.

> ⚠️ Always open the tracker the same way (same browser, same file location or same URL). Your progress is saved per browser and per location, so opening a different copy will look empty.

---

## Step 2: Install the Sync bookmark (one time)

1. Show your bookmarks bar:
   - **Windows / Linux:** `Ctrl + Shift + B`
   - **Mac:** `Cmd + Shift + B`
2. In the tracker, click **Sync from PortSwigger** to open the panel.
3. **Drag** the orange **Sync BSCP** button onto your bookmarks bar.

**If dragging doesn't work:**
1. Click inside the grey code box below the button to select all the code, then copy it (`Ctrl + C` / `Cmd + C`).
2. Right-click your bookmarks bar and choose **Add page** (Chrome) or **Add bookmark** (Firefox).
3. Name it `Sync BSCP`.
4. Paste the code into the **URL** field and save.

---

## Step 3: Sync your solved labs

1. Log in to your PortSwigger account normally at [portswigger.net](https://portswigger.net).
2. Open the **All labs** page: `https://portswigger.net/web-security/all-labs`
3. Click the **Sync BSCP** bookmark.
4. A popup appears saying **"Found N solved labs"**. The data is copied to your clipboard automatically.
5. Go back to the tracker and paste into the import box (`Ctrl + V` / `Cmd + V`).
6. Click **Import**.

The tracker checks off every topic where you've solved at least one lab, and every one of the 8 key labs you've completed. Each synced topic also shows a small **"N solved"** badge.

**Sync as often as you like**, for example once a week. Importing never unchecks anything, so items you checked manually are always kept.

---

## Using the tracker

### Plan tab

Your study roadmap, split into three phases:

| Phase | Weeks | Goal |
|---|---|---|
| **P1: Cover every topic** | 1–4 | Solve Apprentice labs plus at least one Practitioner lab in every topic, without looking at solutions. |
| **P2: The eight key labs** | 5–6 | Complete the 8 labs PortSwigger recommends for exam preparation, then redo them from memory. |
| **P3: Simulate the exam** | 7–8 | Practice mystery labs, pass the practice exam, and prepare for proctoring. |

- **Click any item** (or press `Space` / `Enter`) to check or uncheck it.
- Items marked **tricky** are topics many candidates find hardest. Give them extra time.
- Some items, like "Read the exam hints page," can't be synced and must be checked manually.

### Mystery log tab

Mystery labs give you a random Practitioner lab with no hints about the vulnerability, which is the closest thing to the real exam. PortSwigger requires 5; aim for at least 20.

After each attempt:
1. Enter the **topic or vulnerability** it turned out to be.
2. Choose the **result**: *Solved unaided*, *Solved with hints*, or *Couldn't solve*.
3. Optionally add the **minutes** it took and a **note to self** (what tipped you off, or where you got stuck).
4. Click **Log attempt**.

Watching your times drop is the best sign you're ready. Only *solved* attempts count toward your readiness score.

### Cheat sheet tab

On exam day you'll adapt known payloads rather than invent new ones. Every time you solve a lab:
1. Choose the **exam stage** the technique helps with.
2. Write **the tell**: how you recognized the vulnerability.
3. Paste the exact **payload or steps** that worked.
4. Click **Save payload**.

Entries are grouped by stage, so during review you can quickly find "everything that gets me into a user account."

The BSCP exam has three stages per application:

| Stage | Goal |
|---|---|
| **Stage 1** | Get into any user account |
| **Stage 2** | Elevate to the admin interface |
| **Stage 3** | Read the contents of `/home/carlos/secret` |

---

## How the readiness score works

The ring at the top combines three parts, weighted by how much each matters for passing:

| Part | Weight | Measured by |
|---|---|---|
| 🟠 **Topics covered** | 45% | Phase 1 and Phase 2 items checked |
| 🔵 **Mystery labs** | 25% | Solved attempts logged (goal: 20) |
| 🟢 **Exam readiness steps** | 30% | Phase 3 items checked |

The score is a study guide, not a guarantee. Passing the official practice exam is the most reliable sign you're ready.

---

## Where your data is stored

- Everything is saved in your browser's **local storage** on your own computer.
- Nothing is uploaded or sent anywhere.
- Your data stays until you clear it.

**Your data will be lost if you:**
- Clear your browser's site data, cookies, or history for this page
- Use a private or incognito window
- Open the tracker in a different browser, on a different computer, or from a different file location

### Back up and move your data

Because storage is per-browser, use the buttons at the bottom of the page to keep a real copy on your computer:

- **Export backup (.json)** saves your entire progress (checked items, mystery log, and payloads) as a file in your Downloads. Keep it as a backup, or use it to move to another computer.
- **Export cheat sheet (.md)** saves just your saved payloads as a clean Markdown file, grouped by exam stage, handy for offline review or printing.
- **Import backup** loads a `.json` file you exported earlier. It **merges** into your current progress, so nothing already checked is removed and duplicate log entries are skipped. This is how you sync between two computers: export on one, import on the other.

To start over deliberately, click **Reset all progress** at the bottom of the page.

> 💡 Export a backup before clearing your browser, switching computers, or updating to a new version of the tracker.

---

## Troubleshooting

| Problem | Solution |
|---|---|
| **"Found 0 solved labs"** | Make sure you're logged in and on the **All labs** page (`/web-security/all-labs`), not a single topic page. Refresh the page and try again. |
| **Nothing was pasted** | Your browser blocked clipboard access. In the popup, select all the text in the box, copy it manually, then paste it into the tracker. |
| **"That doesn't look like the copied sync data"** | Something else was on your clipboard. Click the bookmark again and paste straight away. |
| **Clicking the bookmark does nothing** | The bookmark URL must start with `javascript:`. Delete it and create it again using the copy-and-paste method in [Step 2](#step-2-install-the-sync-bookmark-one-time). |
| **Synced count seems too low** | PortSwigger may have changed its page layout. Please [open an issue](https://github.com/Prince-71-Cloud/BCP_tracker/issues) so the sync can be updated. You can still check items manually. |
| **My progress disappeared** | You're probably opening a different copy or browser, or site data was cleared. See [Where your data is stored](#where-your-data-is-stored). |
| **Fonts look plain** | The custom fonts load from Google Fonts. Offline, the tracker falls back to your system fonts. Everything still works. |

---

## FAQ

**Is this an official PortSwigger tool?**
No. It's an independent community project. See the [Disclaimer](#disclaimer).

**Do I need Burp Suite Professional to use the tracker?**
No. The tracker works with any PortSwigger account. You will need Burp Suite Professional for the real exam and some preparation labs, though. PortSwigger requires it.

**Why doesn't it just log in to my account for me?**
Handling your password would put your account at risk, and PortSwigger has no public API. The bookmarklet reads only the page you're already viewing while logged in, which keeps your credentials completely out of the tool.

**Can I use it on my phone?**
You can view and check items on a phone, but the sync bookmarklet is much easier on a desktop.

**Can I sync my progress between two computers?**
Yes, manually. On the first computer click **Export backup (.json)**, move the file over, then click **Import backup** on the second. Your progress merges in without losing anything.

---

## Privacy and security

- **No passwords.** The tool never asks for, reads, or stores your PortSwigger credentials.
- **No servers.** It's a single static HTML file with no backend.
- **No tracking.** There are no analytics, cookies, or third-party scripts, apart from Google Fonts for typography.
- **The bookmarklet is read-only.** It reads which labs show as solved on the page you're viewing, copies that list to your clipboard, and does nothing else. It makes no network requests.
- **Everything is auditable.** The full source is in `index.html`. The bookmarklet source is the `bmFn` function inside it.

Found a security issue? Please report it privately to the maintainer instead of opening a public issue.

---

## Contributing

Contributions are welcome, especially:

- Updating the sync detection if PortSwigger changes its page layout
- Adding new Academy topics as PortSwigger releases them
- Export and import of progress
- Translations and accessibility improvements

**How to contribute:**
1. Fork this repository.
2. Edit `index.html`. The study plan is the `PLAN` array near the top of the `<script>` section.
3. Test your change by opening the file in your browser, including a sync on your own account.
4. Open a pull request describing what you changed and why.

Please keep the project dependency-free, credential-free, and runnable as a single HTML file.

---

## For the maintainer

To publish the live version with **GitHub Pages**:
1. Go to the repository's **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to *Deploy from a branch*.
3. Choose the `main` branch and the `/ (root)` folder, then click **Save**.
4. After a minute or two, the tracker will be live at https://prince-71-cloud.github.io/BCP_tracker/

---

## Disclaimer

This project is **not affiliated with, endorsed by, or sponsored by PortSwigger Ltd.** "Burp Suite" and "Burp Suite Certified Practitioner" are trademarks of PortSwigger Ltd.

The study plan is based on PortSwigger's publicly available exam guidance. Always check the [official BSCP pages](https://portswigger.net/web-security/certification) for the latest exam rules and requirements. This tool doesn't guarantee that you'll pass the exam.

Use of PortSwigger's website must comply with [PortSwigger's terms](https://portswigger.net/legal).

---

## License

Released under the [MIT License](LICENSE).

---

Made with ☕ for the security community by [Md Aman Bhuiyan](https://github.com/Prince-71-Cloud). If this helped you pass, give the repo a ⭐ and share it with others preparing for the BSCP.
