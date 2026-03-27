# Claude Researcher Workspace

A Claude Code workspace configured for deep, structured research on everyday life decisions — products, services, finance, health, travel, and more.

## What it does

Drop a research question into Claude Code inside this directory and get a structured answer with sources, trade-offs, and next steps. No fluff, no hallucinations — it fetches real content from the web and cross-references at least 3 independent sources before forming a conclusion.

**Examples of questions it handles well:**
- "Which car should I buy for under $20k for a family of 4?"
- "What's the best internet provider in São Paulo in 2025?"
- "Should I invest in CDB or Tesouro Direto right now?"
- "What are the best neighborhoods to live in Lisbon for a remote worker?"
- "Compare iPhone 16 vs Samsung S25 for photography"

## How it works

The `CLAUDE.md` file in this repo configures Claude Code with a research-specific workflow:

1. **Clarifies scope** before searching (budget, use case, constraints)
2. **Searches broadly** across forums, reviews, expert comparisons, and recent data
3. **Reads deeply** using WebFetch — not just search snippets
4. **Cross-references** at least 3 independent sources
5. **Outputs a structured answer**:
   - **TL;DR** — the recommendation in 2 sentences
   - **Why** — top 3 reasons
   - **Trade-offs** — what you give up
   - **Alternatives** — 2nd and 3rd best options
   - **Next steps** — concrete actions
   - **Sources** — all sources consulted

## Setup

1. **Install Claude Code** (if you haven't):
   ```bash
   npm install -g @anthropic/claude-code
   ```

2. **Clone this repo:**
   ```bash
   git clone https://github.com/guhcostan/Claude-Researcher-Workspace.git
   cd Claude-Researcher-Workspace
   ```

3. **Open Claude Code in this directory:**
   ```bash
   claude
   ```

4. **Ask anything:**
   ```
   > Which laptop should I buy for software development under $1500?
   ```

## Requirements

- [Claude Code](https://claude.ai/code) with an active Anthropic account
- Claude Code needs access to `WebSearch` and `WebFetch` tools (enabled by default)

## Why a dedicated workspace?

Claude Code picks up the `CLAUDE.md` file automatically when you open it in a directory. This file acts as a system prompt that shapes how Claude approaches every question — enforcing structured research methodology, source cross-referencing, and consistent output format.

Without it, you'd need to repeat instructions every session. With it, you just ask.

## Customization

Edit `CLAUDE.md` to:
- Add your country/region context so searches are localized by default
- Add recurring research categories specific to your life
- Adjust the output format to your preference
- Add tools if you have MCP servers configured (e.g. a Brave Search MCP for better results)

## License

MIT
