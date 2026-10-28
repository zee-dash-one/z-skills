---
name: Writer Groq routing
description: >-
  Use when writing copy, drafts, titles, threads, or transcripts via Groq,
  OpenRouter free, or SambaNova (Writer operator or any bot following the same
  routing).
---
# Writer via Groq + OpenRouter free + SambaNova

Use when generating marketing/copy text through Groq, OpenRouter free, or SambaNova instead of the base model.

## Auth
- Groq: env `GROQ_API_KEY` · `https://api.groq.com/openai/v1`
- OpenRouter: env `OPENROUTER_API_KEY` · `https://openrouter.ai/api/v1`
- SambaNova: env `SAMBANOVA_API_KEY` · `https://api.sambanova.ai/v1`
- Never print keys.
- Chat: `POST /chat/completions` · Transcription (Groq only): `POST /audio/transcriptions`
- Note: SambaNova Cloud is OpenAI-compatible and currently pay-as-you-go (no standing free tier as of mid-2026); keep it as redundancy when Groq/OpenRouter free hit limits.

## Primary routing — Groq (this account)
| Job | Model |
|---|---|
| Drafts, variations, titles, hashtags | `openai/gpt-oss-20b` |
| Final LinkedIn / X copy | `openai/gpt-oss-120b` |
| Long threads | `qwen/qwen3.8-27b` |
| Audio transcription | `whisper-large-v3` |

## OpenRouter free (first free fallback)
| Job | Model |
|---|---|
| Drafts / titles / hashtags | `google/gemma-4-31b-it:free` |
| Final LinkedIn / X | `nvidia/nemotron-3-super-120b-a12b:free` |
| Long threads | `qwen/qwen3.8-27b:free` |
| Very long brief | `nvidia/nemotron-3.5-lightning:free` or `nvidia/nemotron-3-ultra-550b-a55b:free` |
| Auto-pick | `openrouter/free` |

OpenRouter headers: `HTTP-Referer` + `X-Title: Writer`.

## SambaNova (redundancy / paid safety net)
IDs from live `/v1/models` (no `:free` suffix):

| Job | Model |
|---|---|
| Drafts / titles / hashtags | `gemma-4-31B-it` |
| Final LinkedIn / X | `gpt-oss-120b` |
| Long threads | `MiniMax-M2.7` (or `Meta-Llama-3.3-70B-Instruct`) |
| Very long brief | `MiniMax-M3` (1M context) |
| Heavy rewrite / reasoning | `DeepSeek-V3.1` |

## Call patterns
Groq:
```bash
curl -sS https://api.groq.com/openai/v1/chat/completions \
  -H "Authorization: Bearer $GROQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model":"<MODEL>","messages":[{"role":"system","content":"<BRIEF>"},{"role":"user","content":"<TASK>"}],"temperature":0.7,"max_tokens":8192}'
```
OpenRouter: same shape at `https://openrouter.ai/api/v1/chat/completions` with `OPENROUTER_API_KEY` + Referer/Title headers.
SambaNova: same shape at `https://api.sambanova.ai/v1/chat/completions` with `SAMBANOVA_API_KEY`.

Use generous `max_tokens` on reasoning models (`gpt-oss-*`, DeepSeek). Prefer cheapest sufficient model. Never invent Repertório/cases — only rewrite from briefs.

## Fallback order
1. Groq (routed)
2. OpenRouter free (mapped twin)
3. SambaNova (mapped twin)
4. Gemini (`GEMINI_API_KEY`) if configured
5. Base model

On HTTP 429 / provider error: retry once with backoff, then next step. On SambaNova `402`, skip to next (credits/payment required).

## Delivery
Polished text only (no publish). Hand off to Áudio / Video / Image. pt-BR unless brief says otherwise. Footer when asked: model id + provider.
LinkedIn/Instagram post text (and captions) must pass the [humanizar-posts-ptbr](sand-workflow:humanizar-posts-ptbr) step as the final pass before delivery; deliver the humanized text plus the short list of tells removed.
