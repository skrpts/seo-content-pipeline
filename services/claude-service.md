---
type: service
id: claude-service
title: Claude Service
description: "How this skrpt uses Anthropic Claude for SEO research, content analysis, and optimisation recommendations"
tags: [Production, Tested]
connections: []
metadata:
  provider: "anthropic"
  model: "claude-sonnet"
  estimated_duration: "N/A"
---

## Claude Service — SEO Content Pipeline

This skrpt uses Anthropic Claude as its primary AI service for all keyword research, content analysis, and on-page optimisation tasks.

### Usage Pattern

Claude is invoked at each stage of the pipeline:

1. **Keyword Research & Clustering** — Claude generates keyword lists from seed topics, classifies search intent, estimates relative volume and difficulty tiers, and groups keywords into topical clusters. This requires broad knowledge of search behaviour, keyword semantics, and SEO terminology.

2. **Content Gap Analysis** — Claude compares existing content inventories against competitor coverage and target keyword clusters. This requires analytical reasoning, the ability to identify missing topics, and strategic thinking about content prioritisation.

3. **Content Brief Generation** — Claude produces detailed content briefs including heading structures, keyword placement guidelines, competitor analysis summaries, and quality standards. This requires structured output generation and deep understanding of SEO content best practices.

4. **Content Auditing** — Claude evaluates existing pages against on-page SEO criteria, scores each factor, and produces prioritised improvement recommendations. This requires systematic evaluation against a multi-factor checklist.

5. **Meta Tag Generation** — Claude crafts optimised meta titles and descriptions in multiple variants, balancing keyword relevance with click-through appeal. This requires copywriting skill within strict character limits.

6. **Internal Linking Strategy** — Claude designs linking architectures for content clusters, recommending specific link placements, anchor text variations, and authority flow optimisation. This requires understanding of information architecture and link equity distribution.

### Configuration

- **Temperature:** 0.3 for analytical tasks (keyword research, auditing, gap analysis), 0.6 for creative tasks (meta tags, content briefs)
- **Max tokens:** 3000 per invocation, 4000 for content briefs and audit reports
- **Context window:** Pipeline stages are sequential. Each stage receives the outputs of preceding stages to maintain consistency.

### Web Search Integration

This skrpt benefits significantly from web search capabilities when available. Claude can use web search to:
- Verify current SERP landscapes for target keywords
- Analyse competitor page content and structure
- Check current search volume and difficulty estimates against real data
- Identify recent algorithm updates that might affect recommendations

When web search is unavailable, Claude relies on its training data and the context provided by the user. Recommendations should note when they would benefit from real-time SERP verification.

### Requirements

- An active Anthropic API key or Claude CLI access
- Sufficient token quota for the full pipeline (approximately 15,000-20,000 tokens per complete run)
- Optional: web search access for real-time competitive data
