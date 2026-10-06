---
name: figma-carousel
description: Create and revise Korean carousels by duplicating the user's Figma templates, applying configurable fonts and relevant photos, validating rendered layout, and retaining slide IDs for targeted edits. Use for template-based carousel requests.
---

# Figma Carousel

Use connected Figma tools to create editable copies of the user's templates. This skill does not supply credentials, a connector, a scheduler, or social publishing.

## Resolve configuration

Read `carousel.local.json` from the user's project, not the installed skill folder. Resolve missing values from the conversation and inspect the live Figma file. Ask only for required ambiguous inputs. Explicit user instructions override configuration, which overrides the defaults below.

- `file_key`, `page_id`: target source file/page.
- `templates.cover`, `templates.body[]`, `templates.end`: source frame name and optional ID. Names are arbitrary; `[Template] Cover`, `Context1`–`Context4`, and `End` are examples only. One body master can be cloned for several slides. Verify IDs belong to the intended source page. If names are duplicated, resolve the correct frame before writing.
- `output_page_id`: optional destination. If absent, create a clearly named output page or isolated section.
- `image_layer_name`: exact photo slot name, default `image`.
- `layer_names`: optional `cover_title`, `body_title`, and `body` discovery hints. Null means infer from hierarchy and inspect; do not guess between ambiguous candidates.
- `typography.font_policy`: `preserve_template`. Each role (`cover_title`, `body_title`, `body`) may override `font_family`, `font_style`, `min_font_size`, and `max_lines`. `cover_title.exact_lines` defaults to true. `body.emphasis_style` may specify the new emphasis weight. Null font/style preserves the original runs; null minimum uses the original size as the lower bound. Preserve other labels and mixed styles unless explicitly overridden.
- `layout.body_fixed_width`: true by default. Read actual geometry from the template; do not impose another template's dimensions.
- `account_handle` and attribution are distinct; preserve existing credits unless instructed otherwise.

Validate positive sizes and line limits before mutation. Defaults without configuration: cover exactly 2 rendered lines, body title at most 1, body at most 5. Preserve existing fonts and use existing sizes as minima. No particular font, template name, frame size or account is required.

## Editorial rules

Default audience: Korean women in their 20s and 30s who are jobseekers or working professionals. Use polite Korean with a friendly, professional tone; avoid stereotypes. Default six-slide structure: hook cover → problem → two information slides → practical action → call to action. Respect a different audience, structure, or slide count specified by the user.

Shorten overflowing copy before reducing size; never go below the configured minimum. Maximum line count does not guarantee text fits its box. Preserve essential meaning, redistributing copy if needed. Verify numerical/current claims with reliable primary sources; record the source separately, omit unsupported claims, and do not manufacture evidence.

## Figma and fonts

Discover current read/write tools. Load the integration's `figma-use` instructions before calling `use_figma` and obey its API contract. For inspection/planning, stay read-only. For creation, use supported copy/paste or native cloning and edit only copies. Never rebuild or overwrite masters.

Inspect all existing text-run fonts and load them before operations on text-containing nodes. Verify configured replacement family/style names against available fonts, then load them before replacement. A locally installed font may be missing remotely. Figma supports personal uploads under account Settings → Account → Your uploaded fonts; follow current official guidance and applicable confirmations. Use licensed files or official distributions, then verify remote loading succeeds. Do not silently substitute another family. If unavailable, preserve the draft and explain the missing font.

## Build and recover

1. Inspect source frames, text roles/runs, image layers, geometry, overlays and stacking. Do not confuse reference examples with masters.
2. Draft slide titles, body, emphasis phrases and photo briefs. Resolve fonts before beginning mutation.
3. Create `runs/<run-id>/manifest.json` with draft status. Clone masters into the destination and immediately save every returned frame/descendant ID before further edits. On ambiguous failure, inspect the canvas and reconcile recorded IDs before retrying, avoiding duplicate copies.
4. Map source-to-copy nodes by hierarchy and roles. Replace copy text only after font loading; apply emphasis to new text ranges rather than reusing old offsets. Keep body width fixed and preserve template geometry.
5. Insert relevant photos in the configured copied photo slots. Preserve gradients, clipping and profile images. If a cover lacks a slot, resolve whether/where to add one from user intent; do not silently modify its structure.
6. Inspect every slide screenshot at readable size, plus actual font sizes and dimensions. Verify rendered line counts, no clipping/overlap/missing glyphs, image crops and text contrast. Newline count alone is not evidence of rendered lines. Shorten and recheck affected slides; after three failed repair passes, preserve the draft and report the issue.
7. Save records and deliver Figma links, previews when available, and precise incomplete items. Do not claim unobserved exports, image insertion or checks succeeded.

## Photos

Use relevant real photographs unless the user requests generated artwork. Prefer user-provided assets or reusable stock with checked terms. Save source page, creator, usage basis and required credits; image search alone does not establish permission.

Use only the connector's documented insertion route. Do not invent `createImageAsync`, fetch or encoded-data support. When `upload_assets` exists, pass copied image node IDs in upload order and the destination page ID. POST every one-use URL as documented before requesting more URLs. Use batch commit only if its commit URL can be called exactly once. Verify placement IDs. Never retain upload URLs or credentials in public records.

If photo insertion is unsupported, continue independent copy work, save selected photo sources/briefs, mark photos pending and explain the limitation. Do not substitute blank rectangles or claim completion.

## Run records and partial revisions

Keep records outside the installed skill at `runs/<run-id>/`; update after successful mutation batches, using an atomic file replacement when feasible. Never publish private records or credentials.

Manifest: `schema_version`, `run_id`, `topic`, timezone-aware timestamps, source file/page, destination page/section, status (`draft`, `partial`, `complete`), applied rules, ordered slides and validation. Each slide stores number, role, source frame ID, output frame ID/URL, copied layer IDs by role, created IDs, copy, photo status and validation. Record observed sizes/line counts and unresolved issues; unknown checks remain unknown.

Sources: separate `claims` and `photos` arrays, each with slide number. Claims include claim text, source URL/publisher, publication/event date if known and verification date. Photos include source page, creator, usage basis, required credit and durable local asset path if available.

For targeted revision, verify recorded output IDs still exist and modify only requested slides. If stale, rediscover inside that run's destination, never fall back to masters. Update records and recheck only affected slides. A template-rule change does not authorize rewriting all prior outputs.
