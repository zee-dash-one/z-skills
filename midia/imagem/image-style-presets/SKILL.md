---
name: Image style presets
description: >-
  Use when choosing or applying image styles: advertising, anime/manga,
  realistic, comics/HQ, or kids illustration before generating.
---
# Image style presets

Use when the user asks for a visual style (or you need to pick one) before generating: advertising, anime/manga, realistic, comics/HQ, or kids/infantil.

Only the Image operator generates. Pick the tool with [Image visual routing](sand-workflow:image-visual-routing), then apply the matching preset below in the prompt and UI settings.

Public style skills surveyed (none installable as Leonardo/TensorArt connectors):

- [baoyu-comic](https://github.com/JimLiu/baoyu-skills) — manga, realistic, ligne-claire, webtoon, shoujo presets
- [canghe-skills](https://github.com/whitespur/canghe-skills) — manga/anime templates
- [advertising-skills](https://github.com/realkimbarrett/advertising-skills) — ad strategy/copy, not image models
- PicsArt plugin skills (ads, brand packs) — optional install later

## Presets

### Advertising / publicidade

- Look: product or offer hero, clean negative space for headline, high contrast, commercial lighting
- Prompt anchors: `advertising photography, product hero, studio lighting, clean background, commercial campaign still`
- Prefer: Leonardo or Krea for polish; TensorArt product/photo models if named
- Avoid: clutter, unreadable fake logos, real celebrity faces

### Anime / manga

- Look: clear line art, expressive eyes, cel or soft anime shading
- Prompt anchors: `anime style, manga illustration, clean lineart, cel shading, expressive eyes`
- Prefer: TensorArt Anime Lab / anime models; Leonardo anime style if available
- Avoid: photoreal skin pores, western comic crosshatching unless asked

### Realistic / fotorealista

- Look: natural light, credible materials, photographic DOF
- Prompt anchors: `photorealistic, natural lighting, detailed materials, 85mm lens look`
- Prefer: Leonardo photo/cinematic or TensorArt photoreal checkpoints
- Avoid: cartoon outlines, neon anime glow

### Comics / arte de quadrinhos

- Look: inked outlines, flat or screentone fills, panel-ready silhouette
- Prompt anchors: `comic book art, bold ink outlines, flat color, dramatic composition, graphic novel panel`
- Prefer: Leonardo Dynamic/comic styles or TensorArt illustration models; for multi-page educational comics, borrow layout ideas from baoyu-comic (art × tone) but still generate via Image tools
- Avoid: muddy soft paint, tiny unreadable speech balloons unless lettering is requested

### Kids / infantil

- Look: rounded shapes, soft pastel or bright primary palette, friendly faces (stylized, not real children)
- Prompt anchors: `children's book illustration, soft shapes, pastel colors, friendly, simple background`
- Prefer: any still tool; keep composition simple and high readability
- Avoid: horror, gore, hyper-real minors, scary contrast

## How to apply

1. Confirm style with the user if ambiguous.
2. Merge preset anchors into the brief without dropping their subject specifics.
3. Set aspect for the channel (e.g. 16:9 thumb, 1:1 feed, 9:16 story).
4. Generate with the routed tool, deliver file + prompt + style label.

## Hard limits

- No real-person portraits
- Game sprites → SpriteCook only
- Video assembly → Video agent; Image may supply stills
