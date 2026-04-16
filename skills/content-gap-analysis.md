---
type: skill
id: content-gap-analysis
title: Content Gap Analysis
description: "Identifies missing topics, thin content, and keyword opportunities across an existing content library"
tags: [Production, Optimisation, Content]
context_params:
  target_keywords:
    label: "Target Keywords"
    description: "Keywords to target for content gap analysis"
    default: ""
    required: true
connections:
  - target: llm-service
    type: runs_on
---

## Capability

Analyses an existing content library against target keywords and competitor content to find gaps — topics not yet covered, pages with thin content that need expanding, and keyword clusters with no supporting articles. Produces a prioritised list of content opportunities.

## When to Use

- During content audits to find what's missing from your site
- When planning a content calendar to prioritise high-impact topics
- After keyword research to map clusters to existing or needed content

## Inputs

- Target keyword list or keyword clusters
- Existing content inventory (URLs, titles, and topics)
- Competitor content overview (optional — improves gap detection)

## Outputs

- **Missing topics** — keyword clusters with no matching content
- **Thin content** — existing pages that underperform and need expanding
- **Cannibalisation risks** — multiple pages competing for the same keyword
- **Priority recommendations** — which gaps to fill first based on search volume and difficulty
