# Agent Capabilities

> A sanitized, high-level overview of what this agent ("My First Agent", built on the [Gumloop](https://gumloop.com) platform) can do.
>
> **No secrets, credentials, system prompts, MCP auth/config, or internal implementation code are included here** — only public-safe capability metadata (tool names + descriptions).

---

## 🔌 Connected integrations (servers)

| Server | Purpose |
|--------|---------|
| **GitHub** | Read/write repositories, files, issues, pull requests, branches, commits, projects, releases |
| **Firecrawl** | Web scraping / crawling / extraction |
| **Reducto** | Document parsing, extraction, editing, splitting |

> Tool access is discovered dynamically; only the capabilities each connected integration exposes are available.

---

## 🧰 Tool categories

The agent can use the following kinds of tools (categories only — no credentials):

- **Integration (MCP) tools** — discover and execute actions on connected servers (see full inventory below).
- **Web search** — find current information on the web.
- **Web fetch** — read the contents of a specific URL.
- **Image generation** — create images from text descriptions.
- **Sandbox** — an isolated Linux environment for shell commands, Python (pandas, numpy, matplotlib, …), and file read/write/search/import/export.
- **Interaction search** — recall context from previous conversations.
- **Triggers & schedules** — run automatically on external events or on a schedule.
- **Sub-agents** — delegate focused tasks to parallel agent instances.

---

## 🛰️ MCP tool inventory

The full list of tools exposed by each connected MCP server (names + descriptions only — **no auth, endpoints, secret IDs, or config**).

### GitHub

| Tool | Description |
|------|-------------|
| `add_collaborator` | Invite a user to collaborate on a repository |
| `add_comment_to_issue` | Add a comment to a specific issue |
| `add_comment_to_pull_request` | Add an issue comment on a pull request |
| `add_project_item` | Add an issue/PR as an item to a Project board |
| `create_branch` | Create a new branch from an existing branch |
| `create_gist` | Create a new GitHub gist |
| `create_issue` | Create a new issue |
| `create_label` | Create a new label |
| `create_or_update_file` | Create/update one or more files in a single commit |
| `create_project_field` | Create a new column/field in a Project board |
| `create_pull_request` | Create a new pull request |
| `create_repository` | Create a new repository |
| `delete_project_field` | Delete a column/field from a Project board |
| `delete_project_item` | Remove an item from a Project board |
| `get_comment` | Get a specific comment by ID |
| `get_commit` | Get details about a specific commit |
| `get_contents` | Get the contents of a file or directory |
| `get_issue` | Get a specific issue (with project field values) |
| `get_label` | Get info about a single label |
| `get_milestone` | Get details about a milestone |
| `get_organization_id` | Get the internal ID for an organization |
| `get_project` | Get details about a Project board |
| `get_pull_request` | Get a specific pull request |
| `get_rate_limit` | Retrieve current API rate limit status |
| `get_release` | Get details about a release |
| `get_repository_id` | Get the internal ID for a repository |
| `get_stargazers_count` | Get the number of stargazers |
| `get_tag` | Get details about a git tag |
| `get_user_id` | Get the internal ID for a user |
| `get_user_status` | Get a user's status |
| `list_branches` | List all branches |
| `list_collaborators` | List users with access |
| `list_comments` | List comments on an issue or PR |
| `list_commits` | List commits by branch |
| `list_deployments` | List deployments |
| `list_issues` | List issues |
| `list_labels` | List labels |
| `list_milestones` | List milestones |
| `list_project_fields` | List columns/fields in a Project board |
| `list_project_items` | List items in a Project board |
| `list_projects` | List Project boards |
| `list_pull_request_files` | List files changed in a PR |
| `list_pull_request_review_comments` | List inline review comments on a PR |
| `list_pull_requests` | List pull requests |
| `list_releases` | List releases |
| `list_repositories` | List repositories for a user/org |
| `list_stargazers` | List stargazers |
| `list_tags` | List git tags |
| `list_teams` | List teams in an organization |
| `list_vulnerability_alerts` | List Dependabot vulnerability alerts |
| `list_workflows` | List GitHub Actions workflows |
| `merge_pull_request` | Merge a pull request |
| `remove_collaborator` | Remove a collaborator |
| `request_pull_request_reviewers` | Request reviews on a PR |
| `search_code` | Search code snippets |
| `search_issues` | Search issues |
| `search_pull_requests` | Search pull requests |
| `search_repositories` | Search repositories |
| `set_user_status` | Set the authenticated user's status |
| `update_issue` | Update an issue |
| `update_project_field` | Update a column/field in a Project board |
| `update_project_item` | Update the position/order of a project item |
| `update_pull_request` | Update a pull request |

### Firecrawl

| Tool | Description |
|------|-------------|
| `scrape` | Scrape a single URL and extract content in various formats |
| `batch_scrape` | Scrape multiple URLs at once |
| `get_batch_scrape_status` | Get status/results of a batch scrape job |
| `crawl` | Crawl a website and extract content from multiple pages |
| `get_crawl_status` | Get status/results of a crawl job |
| `map` | Get all URLs from a website, ordered by relevance |
| `search` | Search the web and optionally scrape full page content |
| `deep_extract` | Autonomously navigate and extract data based on a prompt |
| `get_deep_extract_status` | Get status/results of a deep extract job |

### Reducto

| Tool | Description |
|------|-------------|
| `upload_document` | Upload a file to Reducto; returns a `reducto://` URL |
| `parse_document` | Parse a document into text, tables, and figures |
| `extract_data` | Extract structured JSON from a document using a schema |
| `edit_document` | Fill forms / modify a document via natural language |
| `split_document` | Split a document into logical sections |
| `download_document` | Download a file from a Reducto result URL |
| `get_job_status` | Get the status/result of a processing job |
| `list_jobs` | List processing jobs (paginated) |
| `cancel_job` | Cancel a running processing job |

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
- MCP authentication, endpoints, `secret_id`s, or connection configuration
- System prompt / agent instructions
- Raw skill implementations (scripts, references, assets)

---

*Generated as a sanitized capabilities summary. Last updated: 2026-06-21.*
