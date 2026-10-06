---
name: figma-carousel
description: Create or revise carousels from a completed user intake form and the user's own Figma templates, with photos, visual validation and recorded slide IDs. Use for template-based carousel requests.
---

# Figma Carousel

## Required intake before production

Before drafting copy, cloning or editing a template, read [intake-form.md](references/intake-form.md) and ask the user to complete it. Accept a completed `carousel-brief.local.md` or explicit answers in the conversation. Reuse an existing completed form for that run; ask only for missing or changed fields. Do not proceed with production while required fields remain unresolved. Read-only template inspection is allowed when the user requests help identifying their own values.

There are no default audience, language, tone, slide count, narrative structure, line limits, font family, font size, frame geometry, or visual effects. Never fill missing values from another user, a previous company template, a test example, or unpublished project history. An explicit choice to use the user's own template values counts as an answer; inspect those values for this run only. Do not interpret a blank or null as consent to preserve or remove effects.

Ask for explicit treatment of shadows, gradients, blur, overlays and other effects: preserve the user's template, remove from output copies, or apply user-supplied specifications. Preserve masters in every case. Only remove effects on copies when the user has chosen removal. Do not remove effects from an original file as part of sanitizing this skill package.

## Configuration

Read optional `carousel.local.json` from the user's project, not the installed skill directory. The completed intake governs this run; clarify conflicts with saved configuration. Blank configuration fields are unresolved, not defaults.

Resolve the source file/page, named source frames or IDs, destination, text roles and photo slots from the form. Names are arbitrary and IDs must be verified against the live file. A body master may be reused if the requested structure permits. If a name maps to several frames or layers, resolve the ambiguity before mutation.

For each text role, use the user-selected font family/style, size/minimum, line limit and exact/maximum rule, or their explicitly selected template values. Preserve unrelated labels only according to the form. Keep account identity and template attribution distinct. For layouts and effects, apply only the chosen policy and values. Do not publish measurements or effects obtained from a private template.

## Connection and fonts

Discover the available Figma tools and read current integration instructions before calling them. In particular, load `figma-use` guidance before `use_figma`. This skill does not supply a connector, credentials, scheduling or social publishing.

Inspect and load all current text-run fonts before operations on text-containing nodes. Verify and load configured replacement styles before applying them. Local font installation does not guarantee remote availability. When a required font is missing, follow current official Figma instructions for personal font upload using licensed files and applicable confirmations, then check remote loading again. Never silently substitute another font.

## Production after intake completion

1. Verify the user's source frames, text roles, photo slots, hierarchy, geometry and effects against the completed form.
2. Draft the requested slide structure, titles, body, emphasis and photo briefs. Verify numerical/current claims against reliable primary sources and record sources separately; omit unsupported claims.
3. Create a private local run record with draft status. Clone source frames using supported copy/paste or native cloning into a clear destination. Edit only copies. Save every returned output frame/descendant ID immediately after successful batches. After ambiguous failures, inspect the destination and reconcile records before retrying.
4. Replace text after font loading. Style emphasis using the new text ranges. Apply the user's layout and effects policies. Shorten overflowing copy first and respect the user's minimum size and rendered line constraints.
5. Apply photos through the connector's documented insertion route to the configured copied slots. Preserve profile images and unrelated content. Resolve a missing photo slot with the user's form rather than assuming a new layout.
6. Inspect every slide screenshot at readable resolution and check actual sizes and bounds against the completed form. Verify rendered line counts, clipping, overlap, glyphs, crops, contrast and effects. Newline count alone does not establish rendered lines. After three unsuccessful repair passes, preserve the draft and report unresolved issues.
7. Deliver verified Figma output links and private run records. Report incomplete portions accurately; do not claim unobserved insertion, export or validation.

## Photos

Follow the user's selected source and image type. For external photos, verify usage terms and record source page, creator and required credit. Search results alone do not establish permission. Do not send private source materials to third parties or publish them without authorization.

Do not invent unsupported Figma image methods. If `upload_assets` is available, pass copied photo node IDs in order and the destination page ID, POST every one-use URL as documented before requesting more URLs, and verify placement IDs. Use batch commit only when its commit URL can be called exactly once. Never publish or retain short-lived upload URLs in shared records. If insertion is unsupported, mark photos pending and report the limitation.

## Private records and revisions

Store the completed form, actual configuration and `runs/<run-id>/` outside the installed skill. Update the manifest after successful mutation batches. Do not commit private forms, template data, metrics, screenshots, effects, fonts, photos or records to this repository.

The manifest records run ID/topic/time, source and destination IDs, status (`draft`, `partial`, `complete`), user-selected rules, ordered slides, output URLs and layer IDs, copy, photo status, validation evidence and unresolved items. Unknown checks remain unknown. Keep claim and photo sources in a separate `sources.json`, associated with slide numbers and verification dates.

For partial revision, reuse the completed run form and verify saved output IDs. Modify only the requested slides, update records and recheck affected outputs. If IDs are stale, rediscover inside that run's destination; never edit masters as a fallback.
