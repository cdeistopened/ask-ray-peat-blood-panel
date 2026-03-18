# Ask Ray Peat: Blood Panel Analyzer

A Claude Code skill that interprets blood work through Ray Peat's metabolic framework. Paste your labs, get a metabolic story — not a marker-by-marker checklist.

## What this does

**RECOMMEND mode** — Describe your symptoms, get Peat's recommended panel with reasoning.

**INTERPRET mode** — Paste your lab values, get the metabolic story your body is telling.

The skill connects markers through 18 metabolic threads discovered by mining 691 claims from Ray Peat's 503 transcripts and 228 wiki articles. Cholesterol isn't just "high" — it's a thyroid conversion failure. Ferritin isn't just "low" — it's an acute phase reactant Peat distrusted. The story is what matters.

## Knowledge base

- **38 marker profiles** — TSH, cholesterol, cortisol, estradiol, ferritin, albumin, CO2, free fatty acids, and 30 more
- **18 metabolic threads** — cross-marker causal chains (thyroid-cholesterol axis, estrogen-iron cycle, endotoxin-serotonin cascade, etc.)
- **4-tier reliability hierarchy** — which tests Peat trusted (albumin, CO2, transferrin sat) vs. distrusted (ferritin, HbA1c, saliva hormones)
- **Pulse-temperature protocol** — Peat's #1 diagnostic tools, detailed measurement and interpretation
- **Women's health timing** — cycle-phase effects on every hormone marker
- **Panel recommendations** — 10 symptom categories with Peat's reasoning

## Installation

Copy the `SKILL.md` and `knowledge/` directory into your Claude Code project:

```
your-project/
└── .claude/
    └── skills/
        └── blood-panel-analyzer/
            ├── SKILL.md
            └── knowledge/
                ├── metabolic-threads.md
                ├── reliability-hierarchy.md
                ├── pulse-temperature-protocol.md
                ├── womens-health-timing.md
                ├── panel-recommendations.md
                └── marker-profiles/
                    ├── tsh.md
                    ├── cholesterol-total.md
                    ├── ... (38 files)
                    └── co2-bicarbonate.md
```

No API keys required. No external dependencies. The skill reads from the pre-computed knowledge base at runtime.

## Usage

Just paste your lab results:

```
TSH: 4.2 mIU/L
Total Cholesterol: 248 mg/dL
Vitamin D: 28 ng/mL
Ferritin: 22 ng/mL
```

Or describe symptoms:

```
I'm always tired, cold hands, gaining weight, brain fog
```

## How it was built

14 agents across 3 waves mined Ray Peat's full corpus:
- **Wave 1:** 6 mining agents extracted 691 biomarker claims from 503 transcripts + 228 wiki articles
- **Wave 2:** 5 synthesis agents clustered claims into metabolic threads and wrote marker profiles
- **Wave 3:** 3 finishing agents wrote the skill, filled gaps, and integrated with the Ask Ray Peat plugin

Every claim in the knowledge base traces to a specific episode or article in Peat's corpus.

## Disclaimer

This skill presents Ray Peat's framework, which frequently contradicts mainstream medical advice. It is an educational tool, not medical advice. Always work with your healthcare provider.

## Part of Ask Ray Peat

This skill is also available as part of the full [Ask Ray Peat plugin](https://github.com/cdeistopened) — a 7-skill metabolic health coaching system built from Peat's complete works.

## License

MIT
