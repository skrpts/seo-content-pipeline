---
type: skill
id: content-auditing
title: Content Audit
description: "Auditing existing content against SEO best practice across technical, on-page, and content-quality factors"
tags: [Production, Optimization, Content]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "3-5 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Content Audit

This skill audits an existing page against current SEO best practice and returns a prioritized, evidence-based list of improvements.

### Core Capability

Given the priority keyword cluster and the competitor set, this skill scores the page across title/meta, heading structure, keyword usage, content depth, linking, technical on-page factors, and freshness — flagging every gap with a specific, actionable fix rather than a vague suggestion.

### Method

1. **Category scoring:** Rate each audit category (Pass / Needs Improvement / Fail) with a one-to-two sentence justification grounded in the page and the keyword targets.
2. **Impact ranking:** Rank every recommendation by expected impact and effort, leading with high-impact, low-effort fixes.
3. **Handoff:** The audit feeds the internal-linking and content-brief stages downstream.

### Output Structure

A summary scorecard followed by a prioritized recommendation list. The audit is the evidence base for the internal-linking strategy and the final content brief.
