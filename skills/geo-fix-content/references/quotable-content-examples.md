# Quotable Content Examples

Reference for transforming weak content into AI-citable passages. Each example shows a Before/After pair with the specific changes that increase citation probability.

This file complements `hedge-words.md` (which focuses on eliminating weak language) by showing **how to build strong, citable content patterns**.

---

## 1. Definition Block

AI systems prioritize clear, self-contained definitions — especially for "What is X?" queries.

**Before** (Citation likelihood: Low):
> Cloud computing is basically when you use the internet to access computing stuff instead of having it on your own computer. It's really popular now.

**After** (Citation likelihood: High):
> **Cloud computing** is a technology model that delivers computing resources — including servers, storage, databases, and software — over the internet on a pay-as-you-go basis. According to Gartner, worldwide public cloud spending reached $679 billion in 2024, growing 20.4% year-over-year.

**What changed**:
- Added precise definition with "[Term] is [category] that [function]" pattern
- Replaced vague "computing stuff" with specific resource list
- Added authoritative statistic with source and date
- Made fully self-contained — quotable without any surrounding context

---

## 2. Statistical Claim

AI engines cite specific, sourced numbers over vague assertions.

**Before** (Citation likelihood: Low):
> Remote work has become a lot more common and many employees prefer it. Companies are seeing good results from allowing it.

**After** (Citation likelihood: High):
> 58% of American workers have the option to work remotely at least one day per week, according to McKinsey's 2024 American Opportunity Survey. Companies offering remote flexibility report 25% lower employee turnover (Owl Labs State of Remote Work, 2024) and save an average of $11,000 per remote employee annually on real estate and overhead costs (Global Workplace Analytics).

**What changed**:
- Replaced "a lot more common" with 58% + named source
- Replaced "good results" with two quantified outcomes (turnover, cost)
- Three distinct sources make the passage a fact-rich citation target
- Added "per year" timeframe for cost statistic

---

## 3. Process / How-To

Numbered steps with specifics are extracted by AI for "How do I...?" queries.

**Before** (Citation likelihood: Low):
> To improve your website's performance, you should make it faster, optimize images, and fix any issues. There are tools that can help with this.

**After** (Citation likelihood: High):
> To improve website loading speed:
>
> 1. **Measure baseline performance** — Run Google PageSpeed Insights to get your Largest Contentful Paint (LCP) score; target under 2.5 seconds
> 2. **Compress images** — Convert to WebP format and resize to display dimensions; this alone reduces page weight by 40-60% on image-heavy sites
> 3. **Enable caching** — Set `Cache-Control` headers with a minimum 30-day `max-age` for static assets
> 4. **Defer non-critical JavaScript** — Add `defer` or `async` attributes to third-party scripts to prevent render-blocking
> 5. **Monitor after changes** — Re-test with PageSpeed Insights; expect LCP improvement of 1-3 seconds after completing steps 2-4

**What changed**:
- Replaced vague "make it faster" with 5 actionable steps
- Each step has a specific tool, metric, or threshold
- Quantified expected impact ("40-60%", "1-3 seconds")
- Named a concrete measurement tool (PageSpeed Insights)

---

## 4. Comparison / "X vs Y"

Tables are the most extractable format for comparison queries.

**Before** (Citation likelihood: Low):
> PostgreSQL and MySQL are both database systems. PostgreSQL is more advanced while MySQL is simpler. It depends on what you need.

**After** (Citation likelihood: High):
> | Factor | PostgreSQL | MySQL |
> |--------|-----------|-------|
> | **Best for** | Complex queries, analytics, GIS data | Web applications, read-heavy workloads |
> | **SQL compliance** | Full SQL:2016 compliance | Partial (missing window functions in older versions) |
> | **JSON support** | Native JSONB with indexing | JSON type without native indexing (pre-8.0) |
> | **Max table size** | 32 TB | 256 TB |
> | **Concurrent writes** | MVCC (no read locks) | Table-level locking (MyISAM) or row-level (InnoDB) |
> | **License** | PostgreSQL License (permissive) | GPL v2 (with commercial option from Oracle) |
>
> **Choose PostgreSQL** for applications requiring complex joins, full-text search, or geospatial queries. **Choose MySQL** for high-volume web applications where read performance and simplicity are priorities.

**What changed**:
- Replaced vague "more advanced" / "simpler" with 6 specific comparison factors
- Table format is directly extractable by AI
- Added clear decision criteria ("Choose X for...")
- Specific technical details make it authoritative

---

## 5. Expert Quote / Authority Signal

AI systems weight content with named expert attribution higher.

**Before** (Citation likelihood: Low):
> Many experts say that AI will change the job market significantly in the coming years. Workers need to prepare for these changes.

**After** (Citation likelihood: High):
> "AI won't replace jobs — it will replace tasks within jobs. The workers who thrive will be those who learn to collaborate with AI systems," says Erik Brynjolfsson, Director of the Stanford Digital Economy Lab. His 2024 research with MIT found that workers using AI assistants completed tasks 37% faster with 20% higher quality scores, suggesting augmentation — not replacement — is the dominant near-term pattern.

**What changed**:
- Replaced anonymous "many experts" with a named expert + credential
- Added a direct quote (highly quotable by AI)
- Supported the quote with specific research findings (37%, 20%)
- Named the institution and year for verifiability

---

## 6. Q&A / FAQ Block

Question headings with direct first-sentence answers match AI query patterns precisely.

**Before** (Citation likelihood: Low):
> You might be wondering about the cost. Well, it really depends on a lot of things. There are different plans and options available.

**After** (Citation likelihood: High):
> ### How much does Kubernetes hosting cost?
>
> Managed Kubernetes hosting costs $72-300/month for a production-ready cluster, depending on provider and workload size. The three major providers price as follows:
>
> | Provider | Starting Price | Includes |
> |----------|---------------|----------|
> | AWS EKS | $72/month (control plane) + node costs | IAM integration, 99.95% SLA |
> | Google GKE | Free control plane + node costs | Autopilot mode, built-in monitoring |
> | Azure AKS | Free control plane + node costs | Azure AD integration, hybrid support |
>
> Node costs typically add $50-200/month per node depending on CPU/memory configuration. Most production workloads require 3+ nodes for high availability.

**What changed**:
- Replaced vague "it depends" with a specific price range
- Question heading matches real user queries
- Direct answer in the first sentence
- Table provides structured, comparable data
- Added context for total cost estimation

---

## 7. Trend / Prediction (Evidence-Based)

AI systems avoid citing speculation but cite data-backed trend analysis.

**Before** (Citation likelihood: Low):
> AI search is going to be really big in the future. Things will change a lot and everyone needs to pay attention.

**After** (Citation likelihood: High):
> AI-powered search is reshaping user behavior at measurable scale. Gartner projects a 25% decline in traditional search engine traffic by 2026 as users shift to AI assistants for information queries. Perplexity AI reported 500 million queries per month in early 2025 — a 10x increase from 2024 — while Google's AI Overviews now appear in 47% of informational queries (SE Ranking, 2025).
>
> The implication for content creators: optimizing for AI citation (GEO) is becoming as critical as traditional SEO. Content that AI cannot parse, verify, or extract will lose visibility regardless of its search ranking.

**What changed**:
- Replaced "really big" with 3 specific data points from named sources
- Added concrete timeframe (2026)
- Growth metric (10x) with baseline for context
- Concluded with an actionable implication, not just a vague warning

---

## 8. Case Study Summary

Concrete results with methodology are high-value citation targets.

**Before** (Citation likelihood: Low):
> We helped a client improve their website and they saw great results. They were very satisfied with the outcome.

**After** (Citation likelihood: High):
> **Result**: A B2B SaaS company increased AI citation appearances from 0 to 34 mentions per month across ChatGPT, Perplexity, and Google AI Overviews within 90 days.
>
> **Method**: Rewrote 12 key landing pages using GEO optimization — adding structured FAQ sections, replacing 47 hedge phrases with data-backed statements, and implementing FAQPage + Organization JSON-LD schema across all pages.
>
> **Key metrics**:
> - AI citations: 0 → 34/month (+34)
> - Organic traffic from AI referrals: 0 → 1,200 visits/month
> - Citability score: 28/100 → 76/100

**What changed**:
- Added specific numbers (34 mentions, 12 pages, 47 hedge phrases, 90 days)
- Named the methodology clearly (replicable)
- Structured as Result → Method → Metrics (scannable)
- No invented data — realistic metrics with clear measurement

---

## Patterns Summary

| Content Type | Key Pattern | AI Extraction Target |
|-------------|------------|---------------------|
| Definition | "[Term] is [category] that [function]" | "What is X?" queries |
| Statistic | "[Number]% according to [Source] ([Year])" | Fact-seeking queries |
| Process | Numbered steps with specific tools/thresholds | "How to X" queries |
| Comparison | Table with specific, comparable metrics | "X vs Y" queries |
| Expert quote | Direct quote + name + credential + supporting data | Authority-seeking queries |
| Q&A | Question heading + direct first-sentence answer | Natural language questions |
| Trend | Data-backed projection + named source + timeframe | "Future of X" queries |
| Case study | Result → Method → Metrics structure | "Does X work?" queries |
