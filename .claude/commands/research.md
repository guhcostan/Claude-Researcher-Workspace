# /research

Deep research on any topic. Dispatches the researcher subagent to fetch and read
multiple real sources, then synthesizes a structured answer.

## Usage

```
/research <topic>
/research which laptop should I buy for software development under $1500
/research best neighborhoods in São Paulo for families in 2025
/research tesouro direto vs CDB vs LCI — which is better right now
```

## What happens

1. If the topic is broad, ask 2–3 targeted clarifying questions before starting.
2. Dispatch the `researcher` subagent to fetch real data from 4–6 sources.
3. Synthesize findings into the standard output format:

---

**TL;DR**: [recommendation in 2 sentences]

**Why**:
- [reason 1 + data]
- [reason 2 + data]
- [reason 3 + data]

**Trade-offs**: [what you give up with this choice]

**Alternatives**:
- [option 2]: [key difference]
- [option 3]: [key difference]

**Next steps**:
1. [concrete action]
2. [concrete action]

**Sources**: [list with URLs]

---

Never fabricate data. If information wasn't found in the fetched sources, say so.
