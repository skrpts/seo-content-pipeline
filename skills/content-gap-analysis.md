---
type: skill
id: content-gap-analysis
title: Content Gap Analysis
description: "Identifies missing, thin, or underperforming content relative to competitors and target keyword coverage"
tags: [Production, Tested, Competitive, Content, Optimisation]
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

Analyses the gap between a site's existing content and the content needed to compete effectively for target keywords and topics. Compares content coverage against competitors, identifies missing subtopics, evaluates content depth, and produces a prioritised roadmap of content opportunities.

## When to Use

- Planning a quarterly or annual content calendar
- Entering a new topic area and assessing the content investment required
- Diagnosing why a site is losing rankings to competitors
- Identifying quick-win content opportunities with low competition
- Evaluating whether to create new content or improve existing pages

## Process

1. **Content Inventory Assessment** — Map the user's existing content against their target keyword clusters. Identify which clusters have strong coverage, thin coverage, or no coverage at all. Flag pages that target the same keyword (cannibalisation risk).

2. **Competitor Content Mapping** — Analyse competitor sites to identify topics and keywords they rank for that the user does not. Map competitor content depth (word count, heading structure, content format) to understand the quality bar for each topic.

3. **Topic Coverage Scoring** — Score each topic cluster on a coverage scale:
   - **Full coverage:** Strong, thorough content that ranks well
   - **Partial coverage:** Content exists but is thin, outdated, or poorly optimised
   - **No coverage:** No content targets this topic or keyword cluster
   - **Cannibalised:** Multiple pages compete for the same keywords

4. **Opportunity Prioritisation** — Rank content gaps by opportunity size, considering:
   - Search volume of the uncovered keywords
   - Ranking difficulty relative to the site's authority
   - Business value of the topic (proximity to conversion)
   - Effort required to create or improve the content
   - Competitor vulnerability (weak competitor content = easier win)

5. **Action Recommendations** — For each gap, recommend one of:
   - **Create:** Write new content from scratch
   - **Expand:** Add depth to existing thin content
   - **Consolidate:** Merge cannibalised pages into a single authoritative piece
   - **Update:** Refresh outdated content with current information
   - **Redirect:** Retire underperforming pages and redirect to stronger alternatives

## Inputs

- User's existing content inventory (URLs or page titles and topics)
- Target keyword clusters from the keyword research stage
- Competitor URLs (2-5 competitors recommended)
- Business priorities or conversion-critical topics (optional)

## Outputs

- Content gap matrix showing coverage by topic cluster
- Competitor content comparison with depth and quality assessment
- Prioritised list of content opportunities with recommended action
- Keyword cannibalisation report with resolution recommendations
- Estimated content investment required (number of pieces, approximate word counts)

## Constraints

- Do not recommend creating content for keywords with no realistic ranking potential given the site's authority
- Always check for cannibalisation before recommending new content — the fix might be consolidation, not creation
- Prioritise business value alongside search volume — a low-volume, high-intent keyword near conversion can be more valuable than a high-volume informational keyword
- Consider content format gaps, not just topic gaps — competitors might rank with videos, tools, or calculators rather than articles
