---
name: PixVerse video
description: >-
  Use when generating or iterating AI video on PixVerse via the box browser.
  Prefer image-to-video from an Image-agent still or an uploaded image when the
  tool allows and fidelity matters.
---
# Site playbook: PixVerse

Use the box browser (no connector). Session persists after sign-in. Never invent credentials; follow the `sign-in` skill at a login wall.

Only the Video agent generates video. Other agents do not.

## Image first

When fidelity matters and the tool accepts an image, start from a still the Image agent already made, or from an uploaded image. Do not invent a new look in text-only mode if a still exists.

1. Ask Image (or use the file already handed over) for the still that matches the shot.
2. On PixVerse, stay on mode **Image & Text** and upload that file with the image-plus control left of the prompt.
3. Prompt describes motion and camera, not a new subject.
4. Fall back to text-only only when there is no still and the shot does not need visual continuity.

## When to use

Generate or iterate AI video clips on PixVerse. Not for publishing; stop when the clip is in the library or credits block Create.

## Fastest path

Open `https://app.pixverse.ai/creation/video` directly. Mode switches do **not** change the URL.

If redirected to login, stop and hand sign-in to the parent. Do not guess credentials.

## Creation panel

| Control | Notes |
|---|---|
| Modes | **Image & Text** (default; use this for a still + prompt), Reference, Template, Transition, Modify, Motion Control, Extend, Speech |
| Prompt | Max 5000 chars. No negative-prompt field observed. |
| Image upload | Square image-plus control immediately left of the prompt. |
| Resolution | 360P, 540P, 720P, 1080P. |
| Aspect | 16:9, 4:3, 1:1, 3:4, 9:16, 21:9, 3:2, 2:3. Match the still. |
| Duration | 1–15s (Seedance 2.5: 4–30s). |
| Model | PixVerse V6 default. Others only if the task names them. |
| Create | Shows credit cost. If balance is lower, stop. Do not Subscribe unless asked. |

Defaults: **540P**, **16:9**, **5s**, Audio ON, Multi-Shot ON, **PixVerse V6**, quantity 1.

## Library

New clips land in Created. Hover may show Share; confirm download on the live UI. Never Delete, Dislike, or Post unless asked.

## Dispatch snippet

```
Open https://app.pixverse.ai/creation/video.
If a sign-in wall appears, STOP and report the URL. Do not type credentials.
Prefer image-to-video: if the task includes an image file path, upload it with the image-plus control left of the prompt and use mode Image & Text. Prompt should describe motion, not a new subject. Match aspect ratio to the still.
Set resolution, duration, and model from the task (defaults: 540P, 16:9, 5s, PixVerse V6).
Paste the prompt (max 5000).
Read credit cost vs balance. If balance < cost, STOP. Do not click Subscribe.
Only click Create if the task says to generate AND credits are enough. Wait for the clip in Created.
Never Delete, Dislike, or Post unless asked.
If a sign-in, captcha, or payment wall appears, stop and report the URL.
```
