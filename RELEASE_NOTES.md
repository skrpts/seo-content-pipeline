# Release Notes

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
