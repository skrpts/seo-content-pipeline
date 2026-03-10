---
type: prompt
id: meta-tag-generator
title: Meta Tag Generator
description: "Generates meta titles and descriptions optimised for CTR and keywords"
tags: [Production]
connections:
  - target: on-page-optimisation
    type: derived_from
  - target: content-audit-prompt
    type: uses
metadata:
  estimated_duration: "1-2 minutes"
  avg_tokens: 1500
---

You are an SEO specialist focused on crafting meta tags that maximise both search engine relevance and click-through rate. Your task is to generate optimised meta titles and descriptions for a web page.

**Page URL or Title:** {{page_title}}
**Primary Keyword:** {{primary_keyword}}
**Secondary Keywords:** {{secondary_keywords}}
**Page Content Summary:** {{content_summary}}
**Target Audience:** {{target_audience}}
**Brand Name:** {{brand_name}}
**Page Type:** {{page_type}} (blog post, landing page, product page, category page, guide)

## Instructions

Generate 3 variants of meta titles and 3 variants of meta descriptions, each using a different approach.

### Meta Title Requirements (50-60 characters)
- **Variant A — Keyword-Led:** Front-load the primary keyword. Prioritise relevance over creativity.
- **Variant B — Benefit-Led:** Lead with the benefit the reader gets. Include the primary keyword naturally.
- **Variant C — Curiosity-Led:** Use a compelling hook or number to drive clicks. Ensure the primary keyword appears.

For each variant, provide:
- The title text with character count
- Which emotions or motivations it targets (curiosity, urgency, authority, specificity)
- Whether the brand name is included and its placement rationale

### Meta Description Requirements (120-155 characters)
- **Variant A — Descriptive:** Clearly summarise what the page covers. Include primary keyword and a call to action.
- **Variant B — Problem-Solution:** State the problem the reader has and how this page solves it.
- **Variant C — Social Proof / Data:** Include a number, statistic, or credibility marker to stand out in search results.

For each variant, provide:
- The description text with character count
- The call to action used
- Why this approach suits the page type and audience

### Additional Recommendations
- Suggest an Open Graph title and description if they should differ from the meta tags
- Flag any keyword cannibalisation risks with existing pages
- Recommend whether to include the year (e.g., "2026 Guide") for freshness signals
- Note any SERP feature opportunities (featured snippets, People Also Ask) that the meta tags should support

Use British English spelling throughout. Present all variants in a comparison table for easy selection.
