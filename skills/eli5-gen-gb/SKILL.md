---
name: eli5-gen-gb
description: >-
  Use when the user types /eli5-gen-gb or wants a dead-simple picture explainer
  on Grok Bot using AI-generated images (GenerateImage), interleaved with short
  text. Prefer this when they want painted/illustrated panels instead of SVG code.
---

# eli5-gen-gb (Grok Bot · AI image comics)

Explain like the reader knows nothing about the topic.

Adapted from Anthropic community eli5 for **Grok Bot chat**: big pictures, few words — panels come from **Grok Bot `GenerateImage`**, not HTML artifacts and not hand-coded SVG (see sibling `eli5-svg-gb`).

## Visual rules (required)

1. **Multiple panels** (usually 3–4), or **one** single inline image if the user asks for a single panel.
2. **Generate each panel with `GenerateImage`** (or the host’s image tool). Flat, kid-friendly, few words in the scene.
3. **Interleave text and images** in chat: short sentence → inline image → short sentence → inline image → …
   Never dump all images in one gallery with no text between them unless the user asks for a single gallery.
4. **Never** send HTML (or other click-to-open) attachments as the explainer.

## Steps

1. Identify the topic (after `/eli5-gen-gb`, or what they asked to understand).
2. Break it into 3–4 kid-simple beats (or one beat if they want a single image).
3. Call `GenerateImage` once per beat with a concrete scene description (subjects, layout, colors, any on-image text).
4. Send alternating short text + inline image for each beat.
5. Keep prose tiny; pictures carry the idea.

## Fallback

If image generation is unavailable, fall back to short emoji + one sentence per beat, or suggest switching to `eli5-svg-gb` (code SVG). Still no HTML file attachment.

## Example beat structure

1. Hard / confusing thing  
2. Make it simple (analogy)  
3. Step-by-step big pictures  
4. “Oh I get it”
