---
name: TensorArt
description: >-
  Use when generating images on TensorArt (tensor.art) via the signed-in box
  browser. Optional API path if an Access Key is configured later. Not for game
  sprites.
---
# TensorArt (browser)

Use when generating images (or browsing TensorArt tools) on TensorArt / Tusi. Only the Image operator generates images.

Official API skill reference: [Tensor-Art/tensorart-skills](https://github.com/Tensor-Art/tensorart-skills) (`tensorart-generate`). This skill uses the **signed-in browser** at https://tensor.art because we already have a session and no Access Key wired into this box yet.

## Before generating

Brief:

- Subject, style tags, composition
- Aspect / size
- Whether Forge, Models, Anime Lab, or a named community model is preferred
- Reference image, if any

No real-person portraits. Prefer English prompts for the model; show the user a pt-BR summary when they write in Portuguese.

## Browser flow

1. Open https://tensor.art (Create / Forge / Anime Lab / Models as the brief needs).
2. If Sign In appears, stop and hand the box to the user for auth.
3. Pick the closest tool or model for the style (anime models for anime, photoreal checkpoints for realistic, etc.).
4. Fill prompt, size, and count (default 1).
5. Run generation, wait for finish, download the best result to `/workspace/`.
6. Report file path, tool/model, prompt, and any visible credit cost.

Do not invent click paths. If the UI changed, stop and report.

## Optional API path (later)

If the user provides a TensorArt Access Key from https://tensor.art/settings/access-key and asks for API generation, follow the official `tensorart-generate` flow: list tools → choose → create task → poll → download. Never echo or commit the key. Until that key exists on the box, stay on the browser path.

## Style tips on TensorArt

- Anime / manga: Anime Lab or anime-tagged models; emphasize linework and eyes
- Realistic: photoreal / SDXL photo models; natural lighting keywords
- Advertising / product: clean studio light, product-centered framing
- Comics / HQ: ink, screentone, panel framing in the prompt
- Kids / infantil: soft, bright, simple shapes

For game sprites, use SpriteCook instead.

## Deliver

File under `/workspace/` plus prompt and settings.
