# Agent Capabilities

> A sanitized, high-level overview of what this agent ("My First Agent", built on the [Gumloop](https://gumloop.com) platform) can do.
>
> **No secrets, credentials, system prompts, or internal implementation code are included here** — only public-safe metadata.

---

## 🔌 Connected integrations (servers)

| Server | Purpose |
|--------|---------|
| **GitHub** | Read/write repositories, files, issues, pull requests, branches, commits, projects, releases |
| **Firecrawl** | Web scraping / crawling |
| **Reducto** | Document parsing / extraction |

> Tool access is discovered dynamically; only the capabilities each connected integration exposes are available.

---

## 🧰 Tool categories

The agent can use the following kinds of tools (categories only — no credentials):

- **Integration tools** — discover and execute actions on connected servers (e.g. GitHub).
- **Web search** — find current information on the web.
- **Web fetch** — read the contents of a specific URL.
- **Image generation** — create images from text descriptions.
- **Sandbox** — an isolated Linux environment for:
  - running shell commands
  - executing Python (pandas, numpy, matplotlib, etc.)
  - reading / writing / searching files
  - importing and exporting files
- **Interaction search** — recall context from previous conversations.
- **Triggers & schedules** — run automatically on external events or on a schedule.
- **Sub-agents** — delegate focused tasks to parallel agent instances.

---

## 🧩 Skills (name + description only)

| Skill | Description |
|-------|-------------|
| **skill-creator** | Creates and improves agent skills using Gumloop sandbox helpers and SKILL.md conventions. |
| **gumloop-sdk** | Calls integration (MCP) tools from sandbox Python or the CLI via the pre-installed Gumloop SDK. |
| **gumcp-client** | Deprecated — superseded by `gumloop-sdk` for new integration scripts. |
| **trigger-builder** | Creates custom polling triggers that monitor integrations for changes. |
| **spreadsheet-output** | Formatting rules for generating CSV and XLSX files that render cleanly in the spreadsheet viewer. |
| **script-connected-html-output** | Rules for HTML outputs that fetch live data from integrations via data scripts. |

> Only skill **names and descriptions** are listed. The underlying skill code, scripts, and assets are internal and not published.

---

## 🔒 What is intentionally excluded

For security and confidentiality, the following are **never** exported:

- API keys, access tokens, OAuth credentials, or any environment secrets
- System prompt / agent instructions
- Internal MCP configuration
- Raw skill implementations (scripts, references, assets)

---

*Generated as a sanitized capabilities summary. Last updated: 2026-06-21.*
