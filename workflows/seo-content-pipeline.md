---
type: workflow
id: seo-content-pipeline
title: SEO Content Pipeline
description: "End-to-end SEO content strategy from keyword research through on-page optimisation"
tags: [Production, Tested]
connections:
  - target: keyword-research
    type: uses
  - target: on-page-optimisation
    type: uses
  - target: content-gap-analysis
    type: uses
  - target: keyword-cluster-generator
    type: uses
  - target: content-brief-writer
    type: uses
  - target: meta-tag-generator
    type: uses
  - target: content-audit-prompt
    type: uses
  - target: internal-linking-strategist
    type: uses
  - target: claude-service
    type: runs_on
  - target: seo-ranking-factors-reference
    type: references
  - target: seo-content-playbook
    type: references
metadata:
  estimated_duration: "25-40 minutes"
  trigger: manual
---

## Overview

This workflow produces a complete SEO content strategy from initial keyword research through to on-page optimisation recommendations. It combines keyword clustering, content gap analysis, brief generation, and technical on-page checks into a single pipeline that outputs publication-ready content plans.

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

Invoke the **content-audit-prompt** to analyse existing content for SEO improvements — keyword usage, heading structure, content depth, and technical issues.

**Output:** Prioritised list of improvements with expected impact.

**Note:** This stage runs in parallel with Stage 3 when auditing existing content alongside planning new content.

### Stage 5: On-Page Optimisation

**Input:** Draft content or existing page content, target keywords from Stage 1

Invoke the **on-page-optimisation** skill followed by the **meta-tag-generator** prompt to produce optimised meta titles, descriptions, and on-page elements.

Then invoke the **internal-linking-strategist** prompt to recommend internal linking structure across the content cluster.

**Output:** Optimised meta tags, on-page recommendations, and internal linking plan.

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
