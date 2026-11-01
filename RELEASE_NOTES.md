# Release Notes

## v1.1.33
GH#1143 — remove 2 `default_from_previous` declarations. K-073 revoked the key, and the consumer wave has since bound every slot that carried it, so the fallback can no longer fire: the declaration was inert.

Measured before deleting rather than after: each of the 41 slots across the catalogue was resolved against **every** invocation, not just its carrier's own workflow, and all 41 were bound by every consumer. Nothing here changes behaviour — the fallback had no path to execution.

Removed: `content-brief-writer.internal_linking`, `internal-linking-strategist.content_audit`.

## v1.1.32
GH#1100 consumer wave batch 6 — declare the data flow these steps were resolving positionally. 5 binding(s) added.

Two slots take declared inputs: `segment-audience` ("Product or Campaign"), which only had keyword clusters available, and `check-input-gaps` ("Inputs Provided"), which reports what the user omitted. New required inputs `product_or_campaign` and `inputs_provided`.

**This flow now requires input it did not require before.** That is the fix: previously the user supplied nothing for these slots and the step silently received whatever the binding pointed at.

Two bindings do not take the positional predecessor. `create-content-brief` (slot "Topic") binds Keyword Research — position would have fed it meta tags. `analyse-content-gaps` (slot "Content Inventory") binds Content Audit — position would have fed it polished content.

## v1.1.31
GH#863 Wave 1 — fix the intent/output mismatch (K-045): the bundle shipped `content-brief-writer`, `content-audit-prompt`, and `internal-linking-strategist` prompts (the brief being the pipeline's real deliverable) and the docs said to run them, but the `execution:` block never invoked any of them — so the SEO content brief was never produced. Restored the intended bound graph: added a **Content Audit** step, an **Internal Linking Strategy** step, and a **SEO Content Brief** step (each with a backing skill so it is `from_step`-addressable), ordered them `headline-writing → content-audit → internal-linking → content-brief`, and rewired every cross-step input to an explicit `from_step` binding (`{{step.context.*}}`) instead of positional/mis-pointed `{{steps.<Title>.output}}` refs. The content-brief step is now the last content step before polish, assembling the brief from the keyword clusters, content-audit findings, internal-linking plan, and on-page meta tags. Also completed the tail: repinned `polish-language` 1.0.3→1.0.6 (the version that exposes the bindable `source` slot) and bound `language-polish`'s `source` ← the SEO Content Brief, so the `output_step` polishes the actual deliverable rather than its positional previous step. Manifest `contents.skills` 3→6, `total` 12→15.

## v1.1.30
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.29
GH#745 — declare per-step `output: {name, type}` on every execution step (keyword_clusters/list, audience_segments/list, meta_tags/text, brief/text, ideas/list, headlines/list, polished_content/text, voice_guide/text, gap_analysis/text, input_gaps/decision). Lights up the #744 rich flow-map with named, typed outputs. **Also corrects the input-gap-check step to its intended `validation` type** — its `step_type` was mis-indented (outside the parallel item) and dropped at parse time, so the step previously ran untyped; it is now a validation gate. Content + structural fix (GH#748); no bindings changes.

## v1.1.28
GH#645 Row 3 final — re-pin 7 prompt-deps to the new v1.0.2/v1.0.3 versions that now expose `nodes[].content` via /api/shared/<slug>/<v>/metadata (per GH#651 endpoint extension + d1Execute dual-mode fix). Engine validator's dep-aware loop-body `{{loop.item}}` interpolation check + binding from_step resolution now pass through deps for this consumer. No content changes; identity + dep-version repin only.

## v1.1.27
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 15 inline shared-content files and declare 15 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.26
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.25
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.24
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.23
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.22
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
