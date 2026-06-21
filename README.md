# c-code

> An extracted/unpacked TypeScript source tree of the **Claude Code** CLI (Anthropic's agentic coding assistant for the terminal).

This repository currently ships the source as a single archive, **`mytest.zip`** (~10 MB compressed, ~34 MB unpacked). Unzipping it produces a `mytest/` directory containing **1,900+ source files** (`.ts` / `.tsx` / `.js`) that make up the application.

> ⚠️ **Note:** This is the internal source of a proprietary product (see `https://claude.com/claude-code`). It is provided here for reference/inspection only. Respect the original software's license and terms when using it.

---

## 📦 What's inside

| Item | Value |
|------|-------|
| Archive | `mytest.zip` |
| Unpacked root | `mytest/` |
| Total source files | ~1,902 |
| TypeScript (`.ts`) | 1,332 |
| React/Ink (`.tsx`) | 552 |
| JavaScript (`.js`) | 18 |
| Unpacked size | ~34 MB |

### Tech stack (inferred from imports)

- **Runtime / bundler:** [Bun](https://bun.sh) (`import { feature } from 'bun:bundle'`)
- **Terminal UI:** [Ink](https://github.com/vadimdemedes/ink) (React for the CLI)
- **AI SDK:** `@anthropic-ai/sdk`
- **Tool protocol:** `@modelcontextprotocol/sdk` (MCP)
- **Validation:** `zod`
- **Utilities:** `lodash-es`, `strip-ansi`, and others

---

## 🗂️ Repository layout

After `unzip mytest.zip`, the key directories under `mytest/` are:

```
mytest/
├── QueryEngine.ts        # Core agent loop / query orchestration
├── Tool.ts               # Tool type system & registration
├── Task.ts               # Task abstraction
├── query.ts              # Streaming query implementation
├── commands.ts           # Slash-command registry
├── main.tsx              # Main application bundle (entry UI)
├── setup.ts              # First-run setup
│
├── entrypoints/          # CLI / MCP / SDK entrypoints (cli.tsx, mcp.ts, sdk/)
├── tools/                # 40+ built-in tools (Bash, FileEdit, WebSearch, MCP, Skill, Task, ...)
├── commands/             # 100+ slash commands (/init, /commit, /review, /mcp, /model, ...)
├── components/           # Ink/React UI components (dialogs, status lines, diffs)
├── services/             # API, MCP, OAuth, analytics, memory, voice, LSP, plugins
├── bridge/               # Remote "Claude Code Remote" session bridge & transport
├── cli/                  # CLI handlers, transports (SSE / WebSocket / Hybrid)
├── buddy/                # Companion sprite / notifications
├── skills/               # Skill loading & execution
├── plugins/              # Plugin system
├── hooks/                # React hooks (permissions, tool use, etc.)
├── constants/            # Product config, prompts, system prompt sections
├── state/                # App state management
├── schemas/              # Zod schemas
├── migrations/           # Data/settings migrations
├── memdir/               # Memory directory handling
├── coordinator/          # Multi-agent coordination
├── remote/ • server/     # Remote & local server logic
├── keybindings/ • vim/   # Input handling
├── voice/                # Voice input (STT) support
└── utils/                # Shared utilities
```

### Built-in tools (`mytest/tools/`)

`AgentTool`, `AskUserQuestionTool`, `BashTool`, `PowerShellTool`, `FileReadTool`,
`FileWriteTool`, `FileEditTool`, `NotebookEditTool`, `GlobTool`, `GrepTool`,
`LSPTool`, `REPLTool`, `WebFetchTool`, `WebSearchTool`, `MCPTool`, `McpAuthTool`,
`ListMcpResourcesTool`, `ReadMcpResourceTool`, `SkillTool`, `ToolSearchTool`,
`TodoWriteTool`, `Task*Tool` (Create/Get/List/Output/Stop/Update),
`Team*Tool`, `ScheduleCronTool`, `RemoteTriggerTool`, `SendMessageTool`,
`EnterPlanModeTool` / `ExitPlanModeTool`, `EnterWorktreeTool` / `ExitWorktreeTool`,
`SleepTool`, `ConfigTool`, `BriefTool`, and more.

### Slash commands (`mytest/commands/`)

Over 100 commands, including:
`/init`, `/commit`, `/commit-push-pr`, `/review`, `/security-review`, `/mcp`,
`/model`, `/config`, `/login`, `/logout`, `/memory`, `/compact`, `/context`,
`/agents`, `/plugin`, `/skills`, `/doctor`, `/cost`, `/status`, `/resume`,
`/rewind`, `/share`, `/install-github-app`, `/install-slack-app`, and many others.

---

## 🚀 Getting started

```bash
# Clone and unpack the source
git clone https://github.com/0xgetz/c-code.git
cd c-code
unzip mytest.zip          # → creates mytest/

# Explore
cd mytest
ls
```

There is no `package.json`, `tsconfig.json`, or build configuration included in
the archive, so this tree is intended for **reading and inspection**, not for a
direct build. To compile or run it you would need to supply the original
project's build setup (Bun, dependencies, and config).

---

## 📄 License

No license file is included in this repository. The contents appear to be the
proprietary source of Claude Code by Anthropic — treat it as **all rights
reserved** unless the original owner states otherwise.
