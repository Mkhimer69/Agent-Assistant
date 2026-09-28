<div align="center">

# 🤖 Agent Assistant

**A compact, themeable productivity console for support agents — built entirely on Google Apps Script. One screen. Zero servers. Zero cost.**

<img src="https://img.shields.io/badge/weekly%20users-100%2B-brightgreen?style=flat">
<img src="https://img.shields.io/badge/version-1.0-orange?style=flat">
<img src="https://img.shields.io/badge/engine-Google%20Apps%20Script-4285F4?logo=google&logoColor=white">
<img src="https://img.shields.io/badge/backend-Google%20Sheets-34A853?style=flat">
<img src="https://img.shields.io/badge/status-actively%20maintained-2ea44f?style=flat">

</div>

---

> **v1.0 — redesigned for productivity.** The whole app now lives on a single focused screen: generate the comment, manage your templates, and pull snippets — without ever leaving the page. No tabs, no context switching.

## ✨ What it does

| | |
|---|---|
| 🧾 **Comment Generator** | Turns a few quick fields — tier, summary, workflow, resolution code — into a clean, copy-ready interaction comment. One click, straight to clipboard. |
| 🗂 **Personal Comment Templates** | Your own library, auto-seeded with 5 starter templates on first run. Click to copy, ✎ to edit inline, ✓ to save, 🗑 to remove — with confirmation. |
| 💬 **Saved Responses Inbox** | Type `/` in the editor to instantly filter your snippets. `Enter` copies and clears. Save, edit, or delete anytime. |
| 🎨 **3 Themes** | Ops, Gold, and Aurora. Cycle with the corner button or `Ctrl + Alt + D` — remembered per user. |
| 🔒 **Per-User Data Isolation** | Templates and snippets live in **your own** `RP` spreadsheet, auto-created in your Drive on first launch. Nothing shared, nothing leaked. |
| 📊 **Access Logging** | Optional lightweight visit log to your own spreadsheet. |

## 📸 Screenshots

<p align="center"><img src="https://raw.githubusercontent.com/Mkhimer69/Agent-Assistant/refs/heads/main/screenshots/comment-assistant.png" width="720"></p>
<p align="center"><em>Comment Generator + personal Comment Templates, side by side on one screen</em></p>

<p align="center"><img src="https://raw.githubusercontent.com/Mkhimer69/Agent-Assistant/refs/heads/main/screenshots/chat-assistant.png" width="720"></p>
<p align="center"><em>Saved Responses — type <code>/</code> to filter your snippets, Enter to copy</em></p>

## 🚀 How it works

```
┌────────────────────────── Your Google Drive ──────────────────────────┐
│                                                                        │
│   RP  (auto-created per user)                                          │
│   ├── Comments          ← your personal comment templates              │
│   └── Canned Responses  ← your / snippets                              │
│                                                                        │
└────────────────────────────────────────────────────────────────────────┘
```

On first launch, the app creates an `RP` spreadsheet **in the current user's Drive** and seeds the Comments sheet with generic starter templates. Every edit, add, and delete from then on touches only that user's copy — other users are never affected.

## 📦 Project structure

```
Agent-Assistant/
├── Code.gs        # Server: data layer (comments, snippets, themes), access log
├── Index.html     # Main page: layout, comment generator, templates UI, theme engine
├── Style.html     # CSS: 3-theme design system built on CSS variables
├── Chat.html      # Saved responses: Quill editor (with fallback), / suggestions
├── appsscript.json
└── screenshots/
```

## ⚙️ Deployment (5 minutes)

1. **Create the project** — [script.google.com](https://script.google.com) → **New Project**.
2. **Add the files** — create `Code.gs`, `Index.html`, `Style.html`, `Chat.html` and paste in each file's contents from this repo.
3. **Set the manifest** — enable *Show "appsscript.json"* in Project Settings, then replace it with this repo's version.
4. **Deploy** — *Deploy → New deployment → Web app*:
   - **Execute as:** `User accessing the web app` ← required for per-user data
   - **Who has access:** your choice (`Domain` for workspace, `Anyone` for public)
5. **Open the URL** — your `RP` file is created automatically and you're in.

> 📌 **After any code change:** create a *new deployment version* — Apps Script serves cached HTML from old versions.

## 🔧 Configuration

| What | Where | Note |
|---|---|---|
| Access log spreadsheet ID | `logAccess()` in `Code.gs` | Point at your own log file |
| Feedback destination | `submitfeedback()` in `Code.gs` | Point at your own file |
| Starter templates | `seedDefaultComments()` in `Code.gs` | Runs only on first-time sheet creation |
| Themes | `:root` / `[data-theme]` blocks in `Style.html` | Add a block + push its name into the `CYCLE` array in `Index.html` |

## 🔐 Privacy

- Your templates and snippets are stored **only in your own Google Drive**.
- Scopes are limited to Spreadsheets + Drive, for files the app creates for you.
- Theme preference is stored in per-user Script Properties.
- No third-party analytics or trackers. (Quill and Ionicons load from public CDNs.)

## 🧰 Troubleshooting

<details>
<summary><b>Buttons / editor not responding</b></summary>

Hard-refresh with cache disabled and open the URL of your newest deployment. Apps Script aggressively caches HTML.
</details>

<details>
<summary><b>Access log shows "(unknown)"</b></summary>

Google may withhold the user's email depending on deployment access settings. Deploy with <code>DOMAIN</code> access on a Workspace account for reliable identity, and make sure every accessing user has <strong>Editor</strong> access to the log spreadsheet (the script runs <em>as them</em>).
</details>

<details>
<summary><b>Enter no longer copies in the snippet editor</b></summary>

The Enter override must be unshifted into Quill's keyboard bindings so it runs before Quill's default newline handler — see <code>startQuill()</code> in <code>Chat.html</code>.
</details>

## 🗺 Roadmap

- [ ] Export / import templates as JSON
- [ ] Keyboard shortcuts for snippet insertion while typing
- [ ] Optional shared team template layer (read-only)
- [ ] Light theme

## 🖼 Gallery — earlier releases

<details>
<summary>Modules from the v0.x multi-tab era</summary>

<p align="center"><img src="https://raw.githubusercontent.com/Mkhimer69/Agent-Assistant/refs/heads/main/screenshots/email-assistant.png" width="640"></p>
<p align="center"><em>Email Assistant — v0.x</em></p>

</details>

## 🤝 Contributing

Issues and PRs are welcome — bug reports, theme ideas, and UX improvements especially.

## 📄 License

MIT — see [LICENSE](LICENSE).
