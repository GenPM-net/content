# @core/content

[![genpm](https://api.genpm.net/v1/badge/@core/content.svg)](https://genpm.net/p/@core/content) ![license](https://img.shields.io/badge/license-MIT-blue)

> Headless CMS core: typed collections and singletons with drafts, revisions, scheduling, locales and preview

A [GenPM](https://genpm.net) module: **source code + AI rules + MCP config**, injected into your project instead of hidden in `node_modules`. The code lands in `src/lib/content`, pinned to a verified commit, and you own it.

## Install

```bash
genpm add @core/content
```

No genpm yet? `curl -fsSL https://genpm.net/install.sh | sh` (macOS/Linux), `irm https://genpm.net/install.ps1 | iex` (Windows), or one-off with `npx @genpm-net/cli add @core/content`.

Or let your AI agent do it: run `genpm mcp setup` once, then ask *"add @core/content with genpm"* in Claude Code, Cursor, VS Code, Windsurf, Codex or Gemini CLI. It shows you a dry-run plan before writing anything.

## What it does

Content model of the CMS: collections (pages, posts, FAQs) and singletons (home, footer, settings) defined with zod,
stored in Postgres with drafts separate from published data, revisions, scheduled publishing (@core/jobs), locales
with fallback and signed preview. Implements `ContentSource`, sitemap/search sources and `AdminResource`
(@core/contracts). No UI: @core/admin renders the editor from `contentAdminResource()`.

## At a glance

- **GenPM dependencies** (installed with it): [@core/db](https://genpm.net/p/@core/db), [@core/jobs](https://genpm.net/p/@core/jobs), [@core/contracts](https://genpm.net/p/@core/contracts)
- **npm dependencies** (proposed, never installed without asking): `zod`
- **Environment variables** (added to `.env.example`): `CONTENT_PREVIEW_SECRET`, `CONTENT_DEFAULT_LOCALE`
- **AI rules**: [`AGENTS.md`](AGENTS.md), loaded by your agent only when it works in `src/lib/content`

## Security

GenPM installs a 40-character commit SHA (never a branch), verifies an Ed25519-signed manifest, never runs install scripts and scans AI rules for prompt injection. Details: [genpm.net/docs/security](https://genpm.net/docs/security).

## License

MIT — see [LICENSE](LICENSE). Browse the full catalog at [genpm.net](https://genpm.net).
