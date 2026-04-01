# geo-audit

**Diagnose why AI can't find, cite, or recommend your website.**

geo-audit is an Agent Skill that runs a comprehensive Generative Engine Optimization (GEO) audit. It follows the open [AgentSkills](https://agentskills.io) standard and works with Claude Code, OpenCode, OpenClaw, Codex CLI, Cursor, GitHub Copilot, and other compatible agents. It tells you exactly what's blocking ChatGPT, Claude, Perplexity, Gemini, and Google AI Overviews from discovering and citing your content — and gives you a prioritized fix plan.

---

## 3-Layer GEO Model

geo-audit evaluates your site across 4 dimensions organized in 3 layers:

```
┌─────────────────────────────────────────────┐
│              SIGNAL LAYER (25%)             │
│         Entity & Brand Signals              │
│   Wikipedia · LinkedIn · Reddit · Reviews   │
├─────────────────────────────────────────────┤
│             CONTENT LAYER (35%)             │
│           Content Citability                │
│  Answer Blocks · Stats · Structure · E-E-A-T│
├─────────────────────────────────────────────┤
│              DATA LAYER (40%)               │
│   Technical Access (20%) + Schema (20%)     │
│  AI Crawlers · SSR · llms.txt · JSON-LD     │
└─────────────────────────────────────────────┘
```

**Composite formula**: `GEO = Technical×0.20 + Citability×0.35 + Schema×0.20 + Brand×0.25`

---

## What Gets Analyzed

### 1. Technical Accessibility (20%)
- AI crawler access (GPTBot, ClaudeBot, Google-Extended + 8 more)
- robots.txt and X-Robots-Tag headers
- Server-side rendering vs client-side rendering
- llms.txt presence and completeness
- HTTPS, response time, compression
- Sitemap, meta tags, Open Graph, canonical URLs
- Multimedia accessibility (image alt text, key info in text, video transcripts)

### 2. Content Citability (35%)
- Answer block quality (Q+A patterns, definitions, FAQ)
- Self-containment (passages understandable in isolation)
- Statistical density (numbers, sources, data recency)
- Structural clarity (headings, lists, tables, paragraph length)
- Expertise signals (author bylines, expert quotes, dates)
- AI query alignment (conversational coverage, long-tail intent, query-answer directness)

### 3. Structured Data (20%)
- Organization/LocalBusiness schema with sameAs
- Article/BlogPosting with author and dates
- Speakable property for AI voice assistants
- FAQPage, HowTo, BreadcrumbList schemas
- JSON-LD format and syntax validation
- Auto-generated fix templates for missing schemas

### 4. Entity & Brand (25%)
- Wikipedia/Wikidata entity presence
- LinkedIn, Crunchbase, industry directory listings
- Reddit discussions, YouTube presence
- Cross-source brand name and description consistency

---

## Sample Output

```
GEO Audit: example.com
   Business type: SaaS (detected)
   Pages to analyze: 8

Running 4 parallel analyses...
   Technical Accessibility: 72/100 (3 issues)
   Content Citability: 58/100 (5 issues)
   Structured Data: 45/100 (4 issues)
   Entity & Brand: 81/100 (2 issues)

GEO Score: 62/100 (Grade C: Developing)

Full report: GEO-AUDIT-example-com-2026-03-12.md
```

The full report includes:
- Score breakdown with sub-dimensions
- Prioritized issue list (Critical → Low)
- Specific fix instructions for each issue
- Ready-to-use JSON-LD templates
- Top 5 quick wins with expected point gains
- 30-day improvement roadmap

---

## Score Grades

| Grade | Range | Meaning |
|-------|-------|---------|
| **A** | 85-100 | AI-optimized. Likely cited by major AI engines. |
| **B** | 70-84 | Solid foundation. Targeted fixes push to A-tier. |
| **C** | 50-69 | Significant gaps. Structured 30-day plan needed. |
| **D** | 30-49 | Major issues. Prioritize critical fixes first. |
| **F** | 0-29 | Fundamental problems blocking AI discovery. |

---

## Research Foundation

This tool's scoring methodology synthesizes findings from 101+ sources including:

- **Aggarwal et al. (2023)** — "GEO: Generative Engine Optimization" (Princeton/Georgia Tech)
- **BrightEdge (2024-2025)** — AI citation correlation studies
- **Google Search Central** — Schema.org implementation and rich results
- **Zyppy/SparkToro** — Zero-click search and AI answer source analysis
- Backlinko, Ahrefs, Semrush, Moz, and 90+ industry publications

Full research data available in the `raw/` directory.

---

## Related Skills

| Skill | Description |
|-------|-------------|
| [geo-fix-content](../geo-fix-content/) | Rewrite content for better AI citability — use after audit identifies low Citability scores |
| [geo-fix-schema](../geo-fix-schema/) | Generate JSON-LD structured data — use after audit identifies missing schemas |
| [geo-fix-llmstxt](../geo-fix-llmstxt/) | Generate llms.txt file — use after audit flags missing llms.txt |
| [geo-compare](../geo-compare/) | Compare GEO scores against competitors |
| [geo-monitor](../geo-monitor/) | Track GEO score changes over time |
