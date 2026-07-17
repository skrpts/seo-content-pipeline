---
type: workflow
id: seo-content-pipeline
title: SEO Content Pipeline
description: "End-to-end SEO content strategy from keyword research through on-page optimization"
tags: [Production, Tested, Optimization, Content]
connections:
  - target: keyword-research
    type: uses
  - target: on-page-optimisation
    type: uses
  - target: language-polish
    type: uses
  - target: llm-service
    type: runs_on
  - target: seo-ranking-factors-reference
    type: references
  - target: seo-content-playbook
    type: references
  - target: audience-segmentation
    type: uses
  - target: content-briefing
    type: uses
  - target: content-ideation
    type: uses
  - target: headline-writing
    type: uses
  - target: brand-voice-guide
    type: uses
  - target: input-gap-check
    type: uses
  - target: content-gap-analysis
    type: uses
metadata:
  estimated_duration: "25-40 minutes"
  trigger: manual
output_step: "language-polish"
composite_steps:
  - "keyword-research"
  - "on-page-optimisation"
  - "content-briefing"
  - "content-ideation"
  - "headline-writing"
  - "content-gap-analysis"
  - "language-polish"
execution:
  - skill: "keyword-research"
    step_type: "synthesis"
    prompt: "keyword-cluster-generator"
    output: { name: "keyword_clusters", type: "list" }
  - skill: "audience-segmentation"
    step_type: "synthesis"
    prompt: "segment-audience"
    output: { name: "audience_segments", type: "list" }
    context:
      market_context: "No additional market context"
  - skill: "on-page-optimisation"
    step_type: "review"
    prompt: "meta-tag-generator"
    output: { name: "meta_tags", type: "text" }
  - skill: "content-briefing"
    prompt: "create-content-brief"
    step_type: "generation"
    output: { name: "brief", type: "text" }
    context:
      target_audience: "General professional audience"
  - skill: "content-ideation"
    prompt: "generate-content-ideas"
    step_type: "generation"
    output: { name: "ideas", type: "list" }
    context:
      content_context: "No additional context"
    bindings:
      source_content:
        from_step: "Content Briefing"
        field: output
  - skill: "headline-writing"
    prompt: "write-headlines"
    step_type: "generation"
    output: { name: "headlines", type: "list" }
  - skill: "language-polish"
    prompt: "polish-language"
    step_type: "content"
    output: { name: "polished_content", type: "text" }
    context:
      voice_profile: "Neutral professional tone"
      grammar_strictness: "Professional"
  - parallel:
    - id: "brand-voice-guide"
      step_type: "local.template"
      output: { name: "voice_guide", type: "text" }
    - skill: "content-gap-analysis"
      prompt: "analyse-content-gaps"
      step_type: "synthesis"
      output: { name: "gap_analysis", type: "text" }
      context:
        target_keywords: "Not specified"
    - skill: "input-gap-check"
      prompt: "check-input-gaps"
      step_type: "validation"
      output: { name: "input_gaps", type: "decision" }
---

## Overview

This workflow produces a complete SEO content strategy from initial keyword research through to on-page optimization recommendations. It combines keyword clustering, content gap analysis, brief generation, and technical on-page checks into a single pipeline that outputs publication-ready content plans.

## Pipeline Stages

### Stage 1: Keyword Research & Clustering

**Input:** Seed topic or keyword, target market, competitor URLs (optional)

Invoke the **keyword-research** skill to identify relevant keywords, then pass results to the **keyword-cluster-generator** prompt to group keywords into topical clusters with search intent classification.

**Output:** Keyword clusters grouped by topic and intent (informational, navigational, commercial, transactional), with estimated search volume tiers and difficulty ratings.

**Gate:** At least 3 viable keyword clusters must be identified before proceeding.

### Stage 2: Content Gap Analysis

**Input:** Keyword clusters from Stage 1, existing content inventory (URLs or titles), competitor content

Invoke the **content-gap-analysis** skill to identify topics and keywords where your content is missing, thin, or outperformed by competitors.

**Output:** Gap report listing missing topics, underperforming pages, and competitor content advantages.

### Stage 3: Content Brief Generation

**Input:** Priority keyword cluster, gap analysis results, competitor URLs

Invoke the **content-brief-writer** prompt to produce a detailed SEO content brief including target keywords, heading structure, word count recommendation, and competitor analysis.

**Output:** Complete content brief ready to hand to a writer, using the **content-brief-template** asset format.

### Stage 4: Content Audit (Existing Content)

**Input:** URL or content of an existing page, target keywords

Invoke the **content-audit-prompt** to analyze existing content for SEO improvements — keyword usage, heading structure, content depth, and technical issues.

**Output:** Prioritized list of improvements with expected impact.

**Note:** This stage runs in parallel with Stage 3 when auditing existing content alongside planning new content.

### Stage 5: On-Page Optimization

**Input:** Draft content or existing page content, target keywords from Stage 1

Invoke the **on-page-optimisation** skill followed by the **meta-tag-generator** prompt to produce optimized meta titles, descriptions, and on-page elements.

Then invoke the **internal-linking-strategist** prompt to recommend internal linking structure across the content cluster.

**Output:** Optimized meta tags, on-page recommendations, and internal linking plan.

## Error Handling

- If seed keywords return no viable clusters, broaden the topic or try related terms before abandoning the analysis
- If content gap analysis finds no gaps, shift focus to content improvement and consolidation rather than new content creation
- If competitor data is unavailable, proceed with keyword-driven analysis only and flag the gap in the output
- If existing content audit reveals fundamental structural issues, recommend a content rewrite rather than incremental fixes
- If internal linking opportunities are limited, recommend creating supporting content to build cluster depth

## Outputs

The complete pipeline produces:
1. Keyword cluster map with intent classification
2. Content gap report
3. Content briefs for new pieces
4. Audit reports for existing content
5. Meta tag recommendations
6. Internal linking strategy

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.seed_topic_or_keyword}}` | Yes | Seed topic or keyword | `growth, onboarding, retention` |
| `{{input.target_market}}` | Yes | target market | `Paste the relevant brief, notes, source material, or dataset here.` |
| `{{input.competitor_urls}}` | Yes | competitor URLs | `https://example.com/reference` |
| `{{input.existing_content_inventory}}` | No | existing content inventory | `Paste the relevant brief, notes, source material, or dataset here.` |

## Outputs

| Name | Description |
|------|-------------|
| Keyword clusters grouped by topic and intent , | Keyword clusters grouped by topic and intent , with estimated search volume tiers and difficulty ratings |
| Gap report listing missing topics, underperforming pages, and competitor content advantages | Gap report listing missing topics, underperforming pages, and competitor content advantages |
| Complete content brief ready to hand to a writer, using the content-brief-template asset format | Complete content brief ready to hand to a writer, using the content-brief-template asset format |
| Prioritized list of improvements | Prioritized list of improvements with expected impact |
| Optimized meta tags, on-page recommendations, and internal linking plan | Optimized meta tags, on-page recommendations, and internal linking plan |

## Setup

Before running this workflow:

1. No external services required — paste your content directly and provide any supporting context as inputs or source nodes.
2. Review the included documents, assets, or source nodes and customize them to match your team, brand, or domain conventions where needed.
3. No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Most stages work with any capable model; stronger models usually improve synthesis, judgement, and writing quality.
- Extraction, classification, and formatting steps generally run well on smaller or faster models.
- Because there are no vendor-specific integrations here, provider choice is mostly a trade-off between speed, quality, and cost.

## Example Input

To test this workflow immediately after import:

```
Seed Topic Or Keyword: "growth, onboarding, retention"
Target Market: "Paste the relevant brief, notes, source material, or dataset here."
Competitor Urls: "https://example.com/reference"
Existing Content Inventory: "Paste the relevant brief, notes, source material, or dataset here."
```

