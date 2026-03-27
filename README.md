# Claude Researcher Workspace

A Claude Code workspace built for deep, structured research on everyday life decisions —
products, services, finance, health, travel, and more.

It never answers from training data alone. It fetches real sources, reads full page content,
cross-references at least 3 independent sources, and returns structured answers with trade-offs.

## Commands

| Command | Description |
|---------|-------------|
| `/research <topic>` | Full structured research on any topic |
| `/compare <A> vs <B>` | Side-by-side comparison with verdict |
| `/decide <situation>` | Decision support with trade-offs and clear recommendation |

**Examples:**
```
/research which car should I buy for under R$80k for a family of 4
/compare Nubank vs Inter vs C6 Bank
/decide should I buy or rent an apartment in São Paulo
/research best internet provider in Florianópolis 2025
/compare iPhone 16 vs Samsung S25 for photography
/decide should I switch from CLT to PJ
```

## How it works

```
User question
     │
     ▼
/research | /compare | /decide  (slash commands)
     │
     ▼
researcher subagent (isolated context)
  • 3–5 WebSearch queries from different angles
  • WebFetch on 4–6 most relevant pages (reads full content, not snippets)
  • Cross-references sources, flags conflicts
     │
     ▼
Structured output
  • TL;DR — recommendation in 2 sentences
  • Why — top 3 reasons with data
  • Trade-offs — honest downsides
  • Alternatives — ranked options with key differences
  • Next steps — concrete actions
  • Sources — all URLs consulted
```

## Workspace structure

```
.
├── CLAUDE.md                            # Main config, imports rules
├── .claude/
│   ├── settings.json                    # Model, permissions, env vars
│   ├── rules/
│   │   └── research-workflow.md         # Detailed research workflow rules
│   ├── agents/
│   │   └── researcher.md                # Subagent: web fetcher + synthesizer
│   ├── commands/
│   │   ├── research.md                  # /research command
│   │   ├── compare.md                   # /compare command
│   │   └── decide.md                    # /decide command
│   └── skills/
│       └── research-methodology/
│           └── SKILL.md                 # Research methodology skill
```

### Key design decisions

**Subagent for research** — the `researcher` agent runs in an isolated context,
keeping the main conversation clean. It fetches pages, reads them fully, and returns
only the findings — not thousands of tokens of raw HTML.

**Slash commands** — `/research`, `/compare`, `/decide` are repeatable inner-loop
workflows. You run them many times a day, so they're commands (not just prompts).

**Skills** — the `research-methodology` skill provides auto-discoverable guidance
on source hierarchy, search strategy, and output structure.

**Rules with `<important>` tags** — the research workflow is wrapped in
`<important if="...">` tags so Claude doesn't skip it as the context grows.

## Setup

1. **Install Claude Code:**
   ```bash
   npm install -g @anthropic/claude-code
   ```

2. **Clone this repo:**
   ```bash
   git clone https://github.com/guhcostan/Claude-Researcher-Workspace.git
   cd Claude-Researcher-Workspace
   ```

3. **Open Claude Code:**
   ```bash
   claude
   ```

4. **Run a command:**
   ```
   /research which laptop should I buy for software development under $1500
   ```

## Requirements

- [Claude Code](https://claude.ai/code) with an active Anthropic account
- Internet access (WebSearch and WebFetch are used heavily)

## Customization

Edit `CLAUDE.md` to add your default region, language, or recurring research categories.

Edit `.claude/settings.json` to change the model or add MCP servers
(e.g., a Brave Search MCP for higher-quality search results).

## License

MIT
