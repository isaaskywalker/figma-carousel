---
name: figma-carousel
description: Create or revise carousels from a completed user intake form and the user's own Figma templates, with photos, visual validation and recorded slide IDs. Use for template-based carousel requests.
---


# Figma Carousel


## Required intake before production


Before drafting copy, cloning or editing a template, read [intake-form.md](references/intake-form.md) and ask the user to complete it. Accept a completed `carousel-brief.local.md` or explicit answers in the conversation. Reuse an existing completed form for that run; ask only for missing or changed fields. Do not proceed with production while required fields remain unresolved. Read-only template inspection is allowed when the user requests help identifying their own values.


There are no default audience, language, tone, slide count, narrative structure, line limits, font family, font size, frame geometry, or visual effects. Never fill missing values from another user, a previous company template, a test example, or unpublished project history. An explicit choice to use the user's own template values counts as an answer; inspect those values for this run only. Do not interpret a blank or null as consent to preserve or remove effects.


Ask for explicit treatment of shadows, gradients, blur, overlays and other effects: preserve the user's template, remove from output copies, or apply user-supplied specifications. Preserve masters in every case. Only remove effects on copies when the user has chosen removal. Do not remove effects from an original file as part of sanitizing this skill package.


## Design and content direction

Follow current Pinterest and Korean Instagram aesthetics for carousel design and content presentation. After intake completion and before drafting, inspect recent accessible public references relevant to the current topic and audience. Record reference URLs, publication dates when visible, and access dates in the private run record. Do not label undated or inaccessible material as verified current; disclose the limitation and request user-provided references when needed.

Adapt typography hierarchy, spacing, photo mood, color relationships, narrative pacing and copy rhythm within the user-approved template and intake constraints. Explicit brand rules and user choices take priority; this direction does not authorize changing the template structure, font sizes or effects. Do not copy another creator's layout, wording or protected images verbatim. Aesthetic references are not factual evidence: verify substantive claims separately.

## Redistribution

The repository's skill, documents and forms, including modified versions, may not be reuploaded, resold or redistributed as part of another package without prior permission from the author. Downloading and installing for use, and sharing the original repository URL, are allowed. Keep private user forms, designs and run records out of shared packages.

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
