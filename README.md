# geoskills — Make Your Website Visible to AI Search Engines

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Agent Skills](https://img.shields.io/badge/AgentSkills-compatible-blueviolet)](https://agentskills.io)

**ChatGPT, Claude, Perplexity, Gemini are answering your customers' questions right now. Is your website part of the answer?**

geoskills is an open-source Agent Skill suite that audits, fixes, and monitors your website's visibility across AI-powered search engines. It tells you exactly what AI engines can't see — and helps you fix it.

Compatible with [Claude Code](https://docs.anthropic.com/en/docs/claude-code), OpenCode, OpenClaw, Codex CLI, Cursor, GitHub Copilot, and any [AgentSkills](https://agentskills.io)-compatible agent.

---

## Why It Matters

Traditional SEO tools measure backlinks and rankings. But when users ask ChatGPT "what's the best X?", backlinks don't decide who gets cited — **content structure, schema markup, and AI accessibility do.**

Research shows the impact is massive:

| Signal | Impact |
|--------|--------|
| Content optimization strategies | **115-415%** visibility improvement (Princeton/Georgia Tech, 2023) |
| Expert quotations in content | **41%** more AI citations |
| Statistics and data inclusion | **30%** higher citation rate |
| Cross-source brand consistency | **2.5x** more likely to be cited |

---

## Quick Start

```bash
# Install all skills (recommended)
npx skills add Cognitic-Labs/geoskills

# Run a full GEO audit on your website
/geo-audit https://your-website.com
```

---

## Available Skills

| Skill | What it does for you |
|-------|----------------------|
| [geo-audit](skills/geo-audit/) | Find out why AI engines are ignoring your website — get a full score breakdown and prioritized fix plan |
| [geo-fix-content](skills/geo-fix-content/) | Rewrite your content so AI engines quote it instead of your competitors |
| [geo-fix-schema](skills/geo-fix-schema/) | Generate the structured data that helps AI engines understand what your business does |
| [geo-fix-llmstxt](skills/geo-fix-llmstxt/) | Create an llms.txt file — the robots.txt equivalent for AI engines |
| [geo-compare](skills/geo-compare/) | See how your GEO score stacks up against 2-3 competitors, side by side |
| [geo-monitor](skills/geo-monitor/) | Track your GEO score over time and catch regressions before they cost you traffic |

---

## How It Works

geoskills evaluates your website across **4 dimensions**:

| Dimension | Weight | What it measures |
|-----------|--------|------------------|
| Technical Accessibility | 20% | Can AI crawlers access your content? (robots.txt, llms.txt, HTTPS, speed, sitemaps) |
| Content Citability | 35% | Will AI engines quote your content? (answer blocks, statistics, expertise signals, structure) |
| Structured Data | 20% | Does AI understand your entities? (JSON-LD schema, Organization, FAQ, Product markup) |
| Entity & Brand Signals | 25% | Does AI trust your brand? (cross-platform consistency, knowledge graph, authority signals) |

You get a **composite GEO Score (0-100)** with sub-dimension breakdowns, severity-ranked issues, and a prioritized fix plan — then use the fix skills to act on it.

---

## Installation

### Recommended

```bash
npx skills add Cognitic-Labs/geoskills
```

### Alternatives

<details>
<summary>Via ClawHub</summary>

```bash
clawhub install geoskills
```
</details>

<details>
<summary>Manual install</summary>

```bash
# Claude Code
git clone https://github.com/Cognitic-Labs/geoskills.git ~/.claude/skills/geoskills

# OpenCode
git clone https://github.com/Cognitic-Labs/geoskills.git ~/.config/opencode/skills/geoskills

# OpenClaw
git clone https://github.com/Cognitic-Labs/geoskills.git ~/.openclaw/skills/geoskills
```
</details>

<details>
<summary>Install a single skill only</summary>

```bash
# Via skills.sh
npx skills add Cognitic-Labs/geoskills --skill geo-audit

# Manual
git clone --depth 1 --filter=blob:none --sparse \
  https://github.com/Cognitic-Labs/geoskills.git \
  ~/.claude/skills/geoskills
cd ~/.claude/skills/geoskills
git sparse-checkout set skills/geo-audit
```
</details>

### Usage

```bash
# Full GEO audit
/geo-audit https://example.com

# Fix skills — generate missing assets
/geo-fix-content https://example.com/blog/post
/geo-fix-schema https://example.com
/geo-fix-llmstxt https://example.com

# Compare competitors
/geo-compare https://mysite.com https://competitor-a.com https://competitor-b.com

# Track progress over time
/geo-monitor https://mysite.com

# In other agents, describe the task naturally:
# "Run a GEO audit on https://example.com"
# "Compare my site with competitor-a.com"
```

---

## What is GEO?

**Generative Engine Optimization (GEO)** is the practice of optimizing content for AI-powered search engines and assistants. Unlike traditional SEO which targets link-based rankings, GEO focuses on making content **discoverable, citable, and recommendable** by large language models.

---

## AIvsRank.com

geoskills is the **diagnostic** layer — it tells you what to fix. [AIvsRank.com](https://aivsrank.com?ref=geoskills) is the **measurement** layer — it tracks how visible you actually are across AI platforms over time. All skills work fully standalone, no API key required.

---

## FAQ

**Which AI platforms does geo-audit cover?**
geo-audit checks access for 11 AI crawlers including GPTBot (OpenAI), Google-Extended (Gemini), ClaudeBot (Anthropic), PerplexityBot, Bytespider (ByteDance), Applebot-Extended, CCBot, Cohere, Amazonbot, FacebookBot, and Meta-ExternalAgent.

**Do I need an API key?**
No. All skills work fully without any API key.

**What does the GEO Score measure?**
The composite GEO Score (0-100) weights four dimensions: Technical Accessibility (20%), Content Citability (35%), Structured Data (20%), and Entity & Brand Signals (25%).

**How is geoskills different from Ahrefs or Semrush?**
Traditional SEO tools measure backlinks and keyword rankings. geoskills measures whether AI systems can read, understand, and cite your content — a fundamentally different signal set that determines your visibility in AI-powered answers.

---

## Changelog

### v1.1.0 (2026-04-02)

All skills upgraded to align with the **Scoring Model v2** introduced in geo-audit v1.1.0.

**Scoring alignment (geo-compare, geo-monitor)**
- Fixed sub-dimension scores to match `scoring-guide.md` — Technical now correctly uses 5 sub-dimensions (35/22/18/13/12) including Multimedia Accessibility
- Expanded all 4 dimension breakdowns (Citability, Schema, Brand) with full sub-score tables

**New capabilities (geo-compare, geo-monitor)**
- Business Type Weight Adjustments — scoring now adapts to SaaS, E-commerce, Publisher, Local, and Agency profiles
- Technical Gate Check — warns when AI crawlers are blocked, providing context for interpreting other scores
- `GEO-AUDIT-META` machine-readable block — enables `geo-monitor` to reliably parse historical baselines and support chained monitoring
- AIvsRank integration section in reports
- Error Handling for edge cases (unreachable URLs, timeouts, robots.txt blocks)

**geo-monitor enhancements**
- Parses `GEO-AUDIT-META` block from baseline reports (with Markdown fallback for older reports)
- Outputs its own META block, enabling chained re-audits without manual setup
- Scoring model version check — warns when comparing v1 vs v2 reports

**geo-fix-content**
- Defined explicit Citability scoring rubric (6 metrics, 100-point scale with clear thresholds)
- Added GEO Score impact context (Content Citability = 35% of composite score)

**geo-fix-llmstxt**
- Added GEO Score impact context (llms.txt = 7 points under Technical → Rendering)

**geo-fix-schema**
- Added GEO Score impact context (Structured Data = 20% weight, 4 sub-dimensions detailed)

**All skills**
- Added Error Handling sections for common failure modes
- Version bumped to 1.1.0

---

## Contributing

Contributions welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

### Areas for contribution:
- Additional business type profiles and scoring adjustments
- Language-specific citability heuristics (non-English hedge word dictionaries)
- New AI crawler detection rules
- Schema template improvements
- New fix skills (e.g., geo-fix-robots, geo-fix-meta)

---

## License

Apache-2.0 — see [LICENSE](LICENSE) for details.

---

*Built by [AIvsRank.com](https://aivsrank.com) — AI Visibility Measurement Platform*
