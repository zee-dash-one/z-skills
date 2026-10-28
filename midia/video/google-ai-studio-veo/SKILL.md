---
name: Google AI Studio Veo
description: >-
  Use when generating a short AI video with Veo — prefer Google Flow Veo 3.1
  Fast as fallback; AI Studio Veo 3.1 when unlocked. Prefer Image-agent stills
  when fidelity matters.
---
# Site playbook: Google AI Studio / Veo

Use the box browser (no connector). Session persists after Google sign-in. A denied Google sign-in on this computer is device trust — do not retry or ask for a token in chat.

Only the Video agent generates video.

## Image first

When fidelity matters, start from a still the Image agent made or from an upload, if the page shows an image input. Prompt then describes motion and camera. If the live page has no image input, say so and use text-only rather than pretending an upload landed.

## Engines (try in order for Shorts)

1. **PixVerse** first ([PixVerse video](sand-workflow:pixverse-video)) — default Shorts path.
2. **Google Flow · Veo 3.1 Fast** — preferred Veo fallback when PixVerse lacks credits. URL: `https://flow.google.com` (labs.google/flow may redirect). Free Flow credits may apply; approve only free-credit generations; stop on payment/upgrade.
3. **AI Studio · Veo 3.1** at `https://aistudio.google.com/prompts/new_video` — often locked behind Google AI Ultra or paid API key. Stop at upgrade wall; do not subscribe or paste a key.

## Flow · Veo 3.1 Fast (Shorts)

| Control | Notes |
|---|---|
| URL | `https://flow.google.com` |
| Model | **Veo 3.1 Fast** (also may show Omni 1.1 Flash, Veo 3.1 Lite, Veo 3.1 Quality) |
| Aspect | 16:9 or **9:16** (pick 9:16 for Shorts) |
| Duration | No dedicated control observed — ask “~8 second” in the prompt |
| Download | Prefer **720p**; 1080p/4K may require upgrade |
| Image | Upload via “Enviar mídia” / attach as first frame; accept image-rights notice if shown |
| Cost | May ask to approve N free credits (e.g. 20). Approve free only; stop if payment |

### Flow dispatch snippet

```
Open https://flow.google.com (signed-in Google session).
If sign-in, 2FA, captcha, or payment/upgrade wall blocks generation, STOP and report the URL.
Set video model to Veo 3.1 Fast. Aspect 9:16. Count 1.
Upload the task still as first frame (accept image-rights if asked). Prompt = motion only + “~8 second” + keep text sharp.
If Flow asks to approve free credits, approve. If it asks to pay or upgrade, STOP.
Generate, wait (queue OK), download 720p to the path the task names.
Do not click Upgrade for 1080p/4K unless asked.
```

## AI Studio controls (when unlocked)

| Control | Notes |
|---|---|
| Prompt | “Describe your video”. Run stays disabled until a prompt is entered. |
| Model | Veo 3.1 when that is what the page shows. |
| Aspect | 16:9 or 9:16. Match the still. |
| Duration | 4s, 6s, or 8s. |
| Resolution | 720p, 1080p, or 4K. 24 fps. |
| Run | Do not click unless the task says to generate and the page is not blocked on plan or API key. |

## AI Studio dispatch snippet

```
Open https://aistudio.google.com/prompts/new_video.
If sign-in, 2FA, captcha, payment, or “Upgrade to unlock Veo” appears, STOP and report the URL. Prefer Flow Veo 3.1 Fast instead of upgrading.
If unlocked: upload still if available; set 9:16, 8s, 720p; paste motion prompt; Run only if enabled and task says generate.
```
