---
type: prompt
id: analyse-content-gaps
title: "Analyse Content Gaps"
description: "Identifies missing topics, thin content, and keyword opportunities in an existing content library"
tags: [Production, Optimisation, Content]
connections:
  - target: content-gap-analysis
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

## Purpose

Drives the content gap analysis skill.

## Prompt

You are an SEO content strategist. Analyse the content library and keyword data below to identify gaps and opportunities.

### Content Inventory

{{steps.previous.output}}

### Target Keywords

{{input.target_keywords}}

### Instructions

1. **Missing topics** — keyword clusters with no matching content at all
2. **Thin content** — existing pages that underperform and need expanding (too short, too shallow, outdated)
3. **Cannibalisation risks** — multiple pages competing for the same keyword or topic
4. **Competitor gaps** — topics your competitors cover that you don't

### Output Format

| Gap Type | Topic/Keyword | Current State | Priority | Recommended Action |
|----------|--------------|--------------|----------|-------------------|
| Missing | [keyword cluster] | No content | High/Medium/Low | [create new page] |
| Thin | [existing URL/title] | [word count, age] | High/Medium/Low | [expand, rewrite, merge] |
| Cannibalisation | [competing pages] | [which pages] | High/Medium/Low | [merge, redirect, differentiate] |

### Priority Ranking

After the gap table, rank the top 5 content opportunities by expected impact (search volume × difficulty × business relevance).

## Formatting Rules

- Use British English throughout
- Be specific and actionable — no vague recommendations
- Structure output clearly with headings, tables, or lists as appropriate
