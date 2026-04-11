---
type: prompt
id: keyword-cluster-generator
title: Keyword Cluster Generator
description: "Generates keyword clusters from a seed topic with search intent classification"
tags: [Production, Automation, Optimisation]
inputs:
  seed_topic_or_keyword:
    label: "Seed Topic or Keyword"
    description: "A starting topic or keyword to generate ideas from"
    example: "remote team management"
    required: true
    type: text
  target_market:
    label: "Target Market"
    description: "The target market segment"
    example: "Mid-market B2B companies (100-1000 employees)"
    required: true
    type: text
  competitor_urls:
    label: "Competitor URLs"
    description: "Websites or profiles of competitors to research"
    example: "https://notion.so, https://coda.io"
    required: true
    type: text
connections:
  - target: keyword-research
    type: derived_from
  - target: content-brief-writer
    type: uses
metadata:
  estimated_duration: "2-3 minutes"
  avg_tokens: 2500
---

You are an SEO keyword strategist. Your task is to generate thorough keyword clusters from the seed topic provided below.

**Seed Topic:** {{input.seed_topic_or_keyword}}
**Target Market:** {{input.target_market}}
**Domain Authority Level:** Infer from the target market context (new / growing / established).
**Geographic Focus:** Derive from the target market description.
**Competitor URLs (if available):** {{input.competitor_urls}}

## Instructions

Analyse the seed topic and produce keyword clusters following this structure:

### For each cluster, provide:

1. **Cluster Name** — A descriptive label for the topic group
2. **Pillar Keyword** — The primary, highest-volume keyword in the cluster
3. **Supporting Keywords** — 8-15 related keywords including:
   - Long-tail variations (3-5 word phrases)
   - Question-based queries (how, what, why, when, where)
   - Comparison and evaluation terms (best, vs, review, alternative)
   - Action-oriented terms (buy, download, sign up, learn)
4. **Search Intent** — Classify the cluster's dominant intent:
   - **Informational** — User seeks knowledge or answers
   - **Navigational** — User seeks a specific page or brand
   - **Commercial** — User is researching before a decision
   - **Transactional** — User is ready to take action
5. **Volume Tier** — Estimate as High / Medium / Low based on topic competitiveness
6. **Difficulty Rating** — Easy / Moderate / Hard / Very Hard based on SERP competitiveness
7. **Content Format Recommendation** — What format would best serve this cluster (guide, listicle, comparison, tutorial, landing page, FAQ)

## Output Requirements

- Generate a minimum of 5 keyword clusters and a maximum of 10
- Include at least one cluster per intent type where relevant
- Prioritise clusters by opportunity score (balance of volume, difficulty, and business relevance)
- Flag any clusters where keyword cannibalisation risk exists if targeting multiple keywords from the same cluster
- For each cluster, note whether it represents a "pillar page" opportunity or a "supporting content" opportunity within a hub-and-spoke content model
- Use British English spelling for all output

## Format

Present each cluster as a structured block with clear headings. After all clusters, provide a summary table ranking them by priority with a one-line rationale for each ranking decision.
