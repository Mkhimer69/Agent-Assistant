# 🤖 Agent Assistant

<p align="center">
  <img src="https://img.shields.io/badge/weekly%20users-100%2B-brightgreen?style=flat">
  <img src="https://img.shields.io/badge/version-1.0-orange?style=flat">
  <img src="https://img.shields.io/badge/engine-Google%20Apps%20Script-4285F4?logo=google&logoColor=white">
  <img src="https://img.shields.io/badge/backend-Google%20Sheets-34A853?style=flat">
  <img src="https://img.shields.io/badge/status-actively%20maintained-2ea44f?style=flat">
</p>

> A workforce support assistant for support agents — **interaction logging,
> email generation, chat responses, and daily productivity tools** in one
> Google Workspace-native interface. Fewer repetitive tasks, better
> documentation, faster workflows.

## 🧩 The Problem

Support agents juggle documentation, emails, and chat replies across separate
tools every interaction. That means repetitive typing, inconsistent
documentation, slower handle times, and knowledge scattered everywhere.

## ✅ The Solution

Agent Assistant combines the daily toolset into one interface — log the
interaction, draft the email, grab the chat response, run the timers —
with a lightweight Google Sheets backend doing all the heavy lifting.

## ✨ Key Features

| Module | What it does |
|---|---|
| 📝 **Comment Assistant** | Structured interaction logging · driver tier classification · resolution reasons · workflow tracking · ride-link docs · one-click clipboard export |
| 📧 **Email Assistant** | Rich-text editor · dynamic templates · driver/customer modes · smart canned responses · personalized greetings & closures |
| 💬 **Chat Assistant** | Slash-command snippets · search-as-you-type · shared response repository · full create/edit/delete template management |
| 🛠 **Productivity Tools** | Call & break timers · timezone lookup by area code · quick-copy templates · notifications |

## 🖼 Screenshots

**Comment Assistant** — logging, tracking & clipboard-ready documentation:
<p align="center"><img src="https://raw.githubusercontent.com/Mkhimer69/Agent-Assistant/refs/heads/main/screenshots/comment-assistant.png" width="640"></p>

**Email Assistant** — templated rich-text email generation:
<p align="center"><img src="https://raw.githubusercontent.com/Mkhimer69/Agent-Assistant/refs/heads/main/screenshots/email-assistant.png" width="640"></p>

**Chat Assistant** — slash-command responses with a searchable knowledge base:
<p align="center"><img src="https://raw.githubusercontent.com/Mkhimer69/Agent-Assistant/refs/heads/main/screenshots/chat-assistant.png" width="640"></p>

## 🏗 Architecture

```mermaid
flowchart LR
    A[Support Agents] --> B[Agent Assistant]
    B --> C[Comment Assistant]
    B --> D[Email Assistant]
    B --> E[Chat Assistant]
    B --> F[Productivity Tools]
    B --> G[Feedback System]
    B --> H[Google Apps Script]
    H --> S[(Google Sheets<br/>repository)]
```

## 💼 Business Impact

- Reduced repetitive manual work
- Standardized documentation and communication
- Accelerated email generation
- Improved response consistency
- Centralized operational tools → higher daily productivity

## 🛠 Technology

Google Apps Script · JavaScript · HTML5 · CSS3 · Google Sheets · Quill Editor · Ionicons

## ✨ Project Highlights

- Built and maintained by a single developer
- 100+ weekly active users
- Zero infrastructure — fully on Google Workspace
- Continuously enhanced through user feedback

## 🔮 Future Enhancements

Advanced analytics dashboard · expanded workflow automation · additional
reporting tools · template categories & tagging · usage statistics ·
enhanced knowledge base · mobile experience improvements

## 📜 Version History

| Version | Highlights |
|---|---|
| **v1.0** | Initial release — Comment, Email & Chat assistants plus productivity toolset on a Google Sheets backend |

## 📄 Disclaimer

This repository showcases the application's architecture, functionality, and
design for portfolio purposes. Company-specific configurations, proprietary
business logic, customer information, operational procedures, and sensitive
internal data have been intentionally excluded.

---

<div align="center">
<b>🤖 Agent Assistant</b><br><i>Every interaction tool. One interface.</i>
</div>
