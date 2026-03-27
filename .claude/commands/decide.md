# /decide

Structured decision support. Use when facing a choice with real trade-offs —
finances, major purchases, life decisions, career moves.

## Usage

```
/decide <situation>
/decide should I buy or rent an apartment in São Paulo
/decide should I switch from CLT to PJ
/decide is it worth buying a new car or keeping the old one
/decide which city should I move to for remote work — Florianópolis, Curitiba, or Lisboa
```

## What happens

1. Extract the key decision criteria from the user's situation.
2. Use `mcp__sequential-thinking__sequentialthinking` to reason through the decision.
3. Dispatch `researcher` subagent to fetch relevant data (costs, benchmarks, experiences).
4. Output a structured decision analysis.

---

**Decision: [question]**

**Context understood**: [restate the user's situation to confirm]

**Key factors**:
| Factor | Weight | [Option A] | [Option B] |
|--------|--------|------------|------------|
| [factor 1] | high | | |
| [factor 2] | medium | | |
| [factor 3] | low | | |

**Recommendation**: [clear recommendation]

**Why**: [2–3 sentences with the core reasoning]

**The case against**: [strongest argument for the other option — be honest]

**What would change this**: [conditions under which the recommendation flips]

**Next steps**:
1. [concrete action]
2. [concrete action]

**Sources**: [list with URLs]

---

Be direct. Give a clear recommendation even for hard decisions.
If the decision has legal, medical, or financial implications requiring a professional, say so.
