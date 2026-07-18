---
type: skill
id: internal-linking
title: Internal Linking Strategy
description: "Designing an internal linking architecture for a content cluster to distribute authority and improve navigation"
tags: [Production, Optimization, Content]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "2-3 minutes"
  avg_tokens: 2000
  trigger: manual
---

## Internal Linking Strategy

This skill designs a hub-and-spoke internal linking architecture for a content cluster, maximizing topical authority and distributing link equity effectively.

### Core Capability

Given the priority keyword cluster and the content-audit findings, this skill maps pillar-to-spoke and cross-spoke links, recommends varied anchor text, surfaces orphaned pages, and sequences the changes by SEO impact.

### Method

1. **Architecture mapping:** Identify the pillar page and its supporting pages, then map the ideal linking relationships between them.
2. **Placement and anchors:** For each recommended link, specify source, target, placement, and varied anchor text.
3. **Authority flow:** Flag orphaned pages and pages that hoard authority, then recommend how to redistribute link equity.

### Output Structure

A description of the hub-and-spoke structure, a table of recommended links, an orphaned-page list, and priority actions ranked by impact. The linking plan feeds the final content brief.
