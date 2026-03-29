---
type: skill
id: keyword-research
title: Keyword Research
description: "Identifies and evaluates keywords for SEO targeting based on relevance, volume, difficulty, and search intent"
tags: [Production, Tested, analysis:content, optimisation:seo]
connections:
  - target: llm-service
    type: runs_on
  - target: seo-ranking-factors-reference
    type: references
metadata:
  estimated_duration: "5-8 minutes"
  avg_tokens: 3000
---

## Capability

Performs thorough keyword research for a given topic, niche, or business domain. Analyses keywords across four dimensions: relevance to the target audience, estimated search volume tier, ranking difficulty, and search intent classification.

## When to Use

- Starting a new content strategy from scratch
- Expanding into a new topic area or market segment
- Refreshing an existing keyword strategy with new opportunities
- Preparing keyword targets for a content calendar
- Identifying long-tail opportunities in a competitive niche

## Process

1. **Seed Expansion** — Take the provided seed keyword or topic and generate a complete list of related keywords, including synonyms, long-tail variations, question-based queries, and related subtopics. Consider how real users would search for this information at different stages of awareness.

2. **Intent Classification** — Classify each keyword by search intent:
   - **Informational:** User wants to learn something ("how to", "what is", "guide to")
   - **Navigational:** User wants to find a specific page or brand
   - **Commercial:** User is researching before a purchase ("best", "vs", "review")
   - **Transactional:** User is ready to act ("buy", "sign up", "download")

3. **Volume & Difficulty Estimation** — Estimate relative search volume (high/medium/low) and ranking difficulty (easy/moderate/hard/very hard) based on the competitiveness of the SERP landscape for each keyword. Consider domain authority requirements, content quality expectations, and existing competition.

4. **Opportunity Scoring** — Score each keyword on an opportunity scale that balances volume against difficulty and relevance. Prioritise keywords where the content can realistically rank within 6-12 months.

5. **Clustering Preparation** — Group related keywords loosely by topic to prepare for formal clustering in the next pipeline stage.

## Inputs

- Seed keyword or topic description
- Target audience or market segment
- Current domain authority level (new site / growing / established)
- Competitor URLs (optional, for gap identification)
- Geographic target (optional)

## Outputs

- Keyword list with intent classification, volume tier, and difficulty rating
- Opportunity scores for prioritisation
- Initial topic groupings for clustering
- Recommended primary and secondary keywords per topic group

## Constraints

- Do not fabricate specific search volume numbers — use tier-based estimates (high/medium/low) unless the user provides actual data from a keyword tool
- Always consider search intent — a high-volume keyword with mismatched intent is worthless
- Prioritise keywords that match the user's realistic ranking ability based on their domain authority level
- Include at least 5 question-based keywords per topic area, as these drive featured snippet opportunities
