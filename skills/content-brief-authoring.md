---
type: skill
id: content-brief-authoring
title: SEO Content Brief
description: "Assembling a detailed, writer-ready SEO content brief from the keyword, audit, linking, and on-page findings"
tags: [Production, Content, Optimization]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "3-5 minutes"
  avg_tokens: 3000
  trigger: manual
---

## SEO Content Brief

This skill assembles the pipeline's headline deliverable: a detailed SEO content brief that a writer can act on without further guidance.

### Core Capability

Given the priority keyword cluster, the content-audit findings, the internal-linking strategy, and the on-page meta tags, this skill produces a single brief covering content overview, keyword strategy, heading structure, competitor analysis, on-page SEO requirements, and quality standards.

### Method

1. **Synthesis:** Fold every upstream artifact into a coherent brief rather than concatenating them.
2. **Actionability:** Specify target keywords, working title, word count, and heading outline concretely enough to hand straight to a writer.
3. **Standards:** State E-E-A-T, readability, and sourcing requirements so the resulting article can rank.

### Output Structure

A clean, structured brief following the content-brief-template format. This is the final content artifact the pipeline polishes and returns.
