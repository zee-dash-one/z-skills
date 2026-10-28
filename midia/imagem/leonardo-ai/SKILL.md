---
name: Leonardo AI
description: >-
  Use when generating still images on Leonardo.ai in the signed-in box browser
  (app.leonardo.ai). Not for game sprites.
---
# Leonardo AI (browser)

Use when generating stills on Leonardo. Only the Image operator generates images.

Source inspiration: [calesthio/generative-media-skills leonardo-image](https://github.com/calesthio/generative-media-skills) and the Leonardo web app. Prefer the signed-in browser session at https://app.leonardo.ai/generate — there is no official Leonardo connector in the Cursor catalog for this account.

## Before generating

Lock a short brief:

- Subject, setting, style, composition
- Aspect ratio / size (1:1, 16:9, 2:3, custom)
- Count (default 1 on free plan)
- Text on image, if any
- What to avoid

No real-person portraits. Default to one private preview. If tokens look low, say so before spending more.

## Browser flow

1. Open https://app.leonardo.ai/generate (or `/generate?model=auto-preset`).
2. If Sign In appears, stop and hand the box to the user for auth.
3. Set Image tab, model (Auto unless the user named one), style, aspect, count.
4. Paste the English-leaning prompt (keep a Portuguese summary for the user if they write in pt-BR).
5. Generate, wait for results, download the best frame to `/workspace/` with a clear name.
6. Report file path, prompt used, model/style/size, and remaining tokens if visible.

Do not invent click paths. If the UI changed, stop and report.

## Style tips on Leonardo

- General marketing / dynamic stills: Style Dynamic or Cinematic + Auto model
- Anime / manga: pick an anime-oriented model or style if listed; put line quality and eyes in the prompt
- Realistic photo: photoreal / cinematic keywords; avoid cartoon tags
- Comics / HQ: ink outlines, panel-ready framing, flat or cel shading in the prompt
- Kids / infantil: soft shapes, bright pastel palette, simple backgrounds

For game sprites, do **not** use Leonardo — use SpriteCook.

## Deliver

File under `/workspace/` plus prompt and settings. Offer one revision pass if the user asks.
