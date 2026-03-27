# /compare

Side-by-side comparison of two or more products, services, or options.
Fetches real data for each option and produces a structured comparison table.

## Usage

```
/compare <option A> vs <option B>
/compare iPhone 16 vs Samsung S25
/compare Nubank vs Inter vs C6 Bank
/compare morar em Lisboa vs Barcelona para trabalho remoto
```

## What happens

1. Identify the comparison dimensions relevant to the category
   (e.g., for phones: price, camera, battery, ecosystem, repairability)
2. Dispatch `researcher` subagent to fetch data on each option in parallel.
3. Output a comparison table + final verdict.

---

**Comparison: [A] vs [B]**

| Dimension | [A] | [B] |
|-----------|-----|-----|
| Price | | |
| [dimension 2] | | |
| [dimension 3] | | |
| [dimension 4] | | |
| [dimension 5] | | |

**Verdict**: [which is better and for whom]

**Choose [A] if**: [specific use case]
**Choose [B] if**: [specific use case]

**Sources**: [list with URLs]

---

Add context about the user's use case if provided — tailor the dimensions accordingly.
