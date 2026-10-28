---
name: Video Shorts routing
description: >-
  Use when generating YouTube/IG Shorts (9:16) video clips. Only the Video
  operator generates. Defaults PixVerse image-to-video; Veo 3.1 only as fallback
  or when explicitly requested. No spoken narration.
---
# Video Shorts routing

Only the **Video** operator generates video clips. Other agents orchestrate and forward — they never generate video.

## Scope (for now)

- **YouTube / Instagram Shorts only** — vertical **9:16**.
- No **16:9** long-form until the user explicitly asks.

## Engine

1. **Default:** [PixVerse video](sand-workflow:pixverse-video) at `https://app.pixverse.ai/creation/video`.
   - Prefer **image-to-video**, mode **Image & Text**.
2. **Fallback:** [Google AI Studio Veo](sand-workflow:google-ai-studio-veo) (**Veo 3.1**) only if PixVerse is blocked / credits fail, **or** the user explicitly asks for Veo.

## Still-first

1. Image operator delivers a **9:16** still first (or reuse an existing handover still).
2. Video prompt = **motion and camera only** — do not invent a new subject.
3. Match aspect to the still (**9:16**).

## PixVerse Shorts defaults

Override the generic PixVerse skill defaults (540P / 16:9 / 5s):

| Control | Shorts default |
|---|---|
| Aspect | **9:16** |
| Duration | **8s** |
| Resolution | **720P** |
| Model | **PixVerse V6** |
| Quantity | **1** |

## Veo Shorts fallback defaults

| Control | Shorts default |
|---|---|
| Aspect | **9:16** |
| Duration | **8s** |
| Resolution | **720p** |
| Model | **Veo 3.1** |

## Voice exclusivity

- Video does **not** generate spoken narration.
- **Áudio** (ElevenLabs) owns TTS.
- The clip may keep ambient/SFX if the UI has Audio ON; never invent spoken voiceover.

## Pipeline

Writer roteiro → Image still 9:16 → Video clip(s) + Áudio narração → human (or later editor) assembles.

## Delivery (per Shorts job)

1. Storyboard (shots)
2. On-screen text cues
3. Generated clip file/link per shot

## Stop conditions

Stop and report on login / 2FA / payment / insufficient credits. Do not subscribe, paste API keys, or invent credentials.

## Out of scope

Final copy (Writer), stills (Image), TTS narration (Áudio), publishing.
