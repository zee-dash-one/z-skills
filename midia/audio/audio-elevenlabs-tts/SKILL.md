---
name: Audio ElevenLabs TTS
description: >-
  Use when generating short narrations (≤3 min) with ElevenLabs TTS via the
  Áudio operator, including multi-account round-robin across hilderney and
  zapfcoorp.
---
# Áudio — ElevenLabs TTS

Use when generating narration/voiceover (≤3 min, pt-BR) via the Áudio operator or when documenting how that operator must call ElevenLabs.

## Exclusivity

Only the **Áudio** bot generates audio. Other bots (Sebastian, Writer, Image, Video, Marketing, etc.) orchestrate and hand off a script — they never call ElevenLabs TTS themselves.

## Inputs

- Spoken script from **Writer** (or a short approved draft)
- Language: pt-BR unless the user asks otherwise
- Max duration: about **3 minutes** of speech

## Accounts (round-robin)

Two connected MCP accounts; alternate every generation to spread credits:

| Label | Namespace |
| --- | --- |
| `hilderney` | `user-Elevenlabs--hilderney` |
| `zapfcoorp` | `user-Elevenlabs--zapfcoorp` |

Before each TTS call:

1. Read the last-used account from agent memory (fact starting with `ElevenLabs last account:`).
2. Pick the other one (if none recorded, start with `hilderney`).
3. Call all ElevenLabs tools for that job on that namespace only.
4. After a successful generation, update memory: `ElevenLabs last account: <label>`.
5. If the chosen account fails with auth/quota/rate-limit, retry once on the other account and note which one was used.

Never invent namespaces; confirm with GetMcpServerStatus if labels change.

## Steps

1. Choose account (round-robin above).
2. List a usable voice with `creative_list_voices` (prefer premade voices if library/professional voices fail with Creator-tier errors).
3. Call `creative_generate_speech` with:
   - `model_id`: `eleven_multilingual_v2` (default)
   - `voice_id` from the list (never invent IDs); default premade until user picks: Adam `pNInz6obpgDQGcFmaJgB`
   - `generations_count`: 1 for smoke/cheap tests; up to 4 when the user wants options
   - `prompt`: the exact spoken text
4. If no speech view appears, poll `creative_get_flow_run_status` with `flow_id` + `session_ids` until `all_completed` or `has_failures`.
5. Deliver the ElevenLabs flow URL (and media URL when available) to the requester, and say which account (`hilderney` / `zapfcoorp`) was used. Do not ask Sebastian to regenerate.

## Voice notes

- Premade voices (e.g. Adam) work on lower tiers and speak Portuguese via multilingual models.
- Professional library voices often require Creator plan — if the API returns a tier error, fall back to premade and tell the user.

## Out of scope

Writing final copy, generating images, or producing video — those belong to Writer, Image, and Video.
