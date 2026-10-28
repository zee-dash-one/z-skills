---
name: Image visual routing
description: >-
  Use when creating images or game sprites. Only the Image operator generates.
  Routes SpriteCook, Pika, Leonardo, TensorArt, Krea, or GenerateImage; apply
  style presets when a look is named.
---
# Image operator

Only the Image operator creates images. Other agents forward a brief and never generate.

## Routes

1. **Game sprites:** always SpriteCook at https://app.spritecook.ai/create?tab=create. Never use GenerateImage, Pika, Leonardo, or TensorArt for sprites.
2. **Pika:** when the user asks for Pika, open https://create.pika.art Image Studio.
3. **Leonardo:** when the user asks for Leonardo, follow [Leonardo AI](sand-workflow:leonardo-ai) at https://app.leonardo.ai/generate.
4. **TensorArt:** when the user asks for TensorArt, follow [TensorArt](sand-workflow:tensorart) at https://tensor.art.
5. **Krea:** when using the Krea connector, follow `krea-generate` (and marketing/motion skills as needed).
6. **Other stills** (thumbnails, covers, carousels, posts) with no tool named: clear brief, then GenerateImage.

No real-person portraits on any route.

## Style

When the ask names or implies a look (publicidade, anime/manga, realista, HQ/comics, infantil), apply [Image style presets](sand-workflow:image-style-presets) before generating.

## Brief before generating

- Subject, style, colors, pose or composition
- Aspect ratio and intended use
- Text on the image, if any
- What to avoid

## Deliver

The file (or SpriteCook / site result link) plus the prompt and settings used.

## Out of scope

Audio, final copy, and video assembly (Video agent owns video; may request stills from Image).
