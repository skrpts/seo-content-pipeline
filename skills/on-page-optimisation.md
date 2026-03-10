---
type: skill
id: on-page-optimisation
title: On-Page Optimisation
description: "Analyses and optimises on-page SEO elements including meta tags, headings, content structure, and technical factors"
tags: [Production, Tested]
connections:
  - target: claude-service
    type: runs_on
  - target: seo-ranking-factors-reference
    type: references
metadata:
  estimated_duration: "5-7 minutes"
  avg_tokens: 2500
---

## Capability

Evaluates web page content against current SEO best practices and produces specific, actionable optimisation recommendations. Covers meta elements, heading hierarchy, keyword placement, content structure, readability, and technical on-page factors.

## When to Use

- Optimising a new piece of content before publication
- Improving the SEO performance of an existing underperforming page
- Auditing a batch of pages for on-page SEO compliance
- Preparing content for a targeted keyword push
- Reviewing content after a Google algorithm update

## Process

1. **Target Keyword Alignment** — Verify that the primary keyword appears in critical on-page elements: title tag, H1, first paragraph, at least one subheading, and the meta description. Check that secondary keywords are naturally distributed throughout the content without keyword stuffing.

2. **Meta Element Audit** — Evaluate the title tag (50-60 characters, keyword-front-loaded, compelling for clicks), meta description (120-155 characters, includes primary keyword, has a clear call to action), and URL slug (short, keyword-rich, hyphen-separated).

3. **Heading Structure Review** — Verify proper heading hierarchy (single H1, logical H2/H3 nesting). Check that headings are descriptive, keyword-relevant, and structured to match likely search intent patterns. Identify opportunities for question-based headings that target featured snippets.

4. **Content Quality Assessment** — Evaluate content depth relative to top-ranking competitors, readability score, paragraph length, use of lists and tables, inclusion of original data or insights, and overall E-E-A-T signals (experience, expertise, authoritativeness, trustworthiness).

5. **Internal Linking Check** — Identify opportunities to add internal links to related content, verify that anchor text is descriptive and keyword-relevant, and flag any orphaned pages within the content cluster.

6. **Technical On-Page Factors** — Check for image alt text, schema markup opportunities, mobile-friendliness considerations, and page speed impact factors (image sizes, render-blocking elements).

## Inputs

- Page content (full text or URL)
- Target primary keyword and secondary keywords
- Competitor URLs ranking for the same keyword (optional)
- Current page performance data — impressions, clicks, position (optional)

## Outputs

- On-page SEO score (percentage against best practice checklist)
- Prioritised list of optimisation recommendations with expected impact (high/medium/low)
- Optimised meta title and description suggestions
- Heading structure recommendations
- Internal linking opportunities
- Technical on-page improvement list

## Constraints

- Never recommend keyword stuffing — keyword density above 2-3% is counterproductive
- Prioritise user experience alongside SEO factors — readability and engagement matter more than mechanical keyword placement
- Base recommendations on current Google guidelines, not outdated tactics
- Flag any recommendations that might conflict with brand voice or existing style guides
