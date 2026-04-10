---
type: prompt
id: content-brief-writer
title: Content Brief Writer
description: "Writes an SEO content brief with target keywords, headings, word count, and competitor analysis"
tags: [Production, Competitive, Content, Optimisation]
connections:
  - target: keyword-research
    type: derived_from
  - target: content-gap-analysis
    type: derived_from
  - target: meta-tag-generator
    type: uses
  - target: content-brief-template
    type: references
metadata:
  estimated_duration: "3-5 minutes"
  avg_tokens: 3000
---

You are an SEO content strategist creating a detailed content brief for a writer. The brief must be detailed enough that a writer can produce a high-ranking article without further guidance.

**Primary Keyword:** Using the pillar keyword from the priority cluster: {{steps.previous.output}}
**Secondary Keywords:** Using the supporting keywords from the same cluster output above.
**Target Audience:** {{input.target_market}}
**Content Goal:** Derive from the keyword cluster's search intent classification (e.g., rank for keyword, drive sign-ups, build authority).
**Competitor URLs:** {{input.competitor_urls}}
**Existing Content URL (if updating):** {{input.existing_content_inventory}}

## Instructions

Produce a complete content brief covering:

### 1. Content Overview
- **Working Title** — A compelling, keyword-optimised title (50-60 characters)
- **Content Type** — Article, guide, listicle, comparison, tutorial, or other
- **Target Word Count** — Based on competitor analysis and topic depth requirements
- **Target Audience** — Who is reading this and what do they need
- **Search Intent** — What the reader expects to find

### 2. Keyword Strategy
- **Primary Keyword** — Where it must appear (title, H1, first paragraph, URL slug)
- **Secondary Keywords** — Natural placement targets throughout the content
- **Semantic Keywords** — Related terms and phrases to include for topical authority
- **Keywords to Avoid** — Any terms that could cannibalise other pages

### 3. Content Structure
- **Recommended H2 and H3 headings** — A full outline with heading hierarchy
- **Key points to cover under each heading** — 2-3 bullet points per section
- **Featured Snippet Opportunity** — If one exists, specify the format (paragraph, list, table) and the question to answer
- **Introduction Requirements** — Hook, context, and what the reader will learn
- **Conclusion Requirements** — Summary, next steps, and call to action

### 4. Competitor Analysis
- Summarise the top 3 ranking pages for the primary keyword
- Identify what they cover well and what they miss
- Note their word count, heading structure, and content format
- Highlight differentiation opportunities

### 5. On-Page SEO Requirements
- Meta title suggestion (50-60 characters)
- Meta description suggestion (120-155 characters)
- URL slug recommendation
- Image alt text guidelines
- Internal linking targets (pages to link to and from)
- Schema markup recommendation (FAQ, HowTo, Article, etc.)

### 6. Quality Standards
- E-E-A-T requirements (citations, author credentials, data sources)
- Readability target (aim for a reading level accessible to the target audience)
- Minimum number of external authoritative sources to reference
- Visual content requirements (images, diagrams, tables, infographics)

Use British English throughout. Output the brief in a clean, structured format that can be handed directly to a content writer.
