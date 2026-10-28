---
name: reforco-localizacao-en
description: >-
  Second, mandatory step of every pt-BR to English localization: independent
  native-English editorial review of a COMPLETED English article produced by
  localizar-ptbr-en. Classifies issues A/B/C, fixes real errors and unnatural
  English, verifies nothing important changed, and saves a separate reinforced
  version. Never runs together with the localization or on an unfinished draft.
---
# English Editorial Reinforcement: Second-Pass Review

## Purpose

Review and improve an existing, completed English-language article that has already been translated and localized from Brazilian Portuguese by localizar-ptbr-en. The input is not untranslated Portuguese and not a working translation draft. It is a finished first-pass English artifact that needs an independent, native-level editorial quality check.

Work in American English throughout the editorial process. Read, diagnose, rewrite, and evaluate English as an experienced US editor would. Do not mentally translate each English sentence back into Portuguese to decide whether it sounds natural. This skill does not revisit the pt-BR original: the translation and localization from Portuguese belong entirely to Stage 1, and this stage works only on the English text.

The goal is a polished, natural, publication-ready English article without altering what happened or how certain the author is about it.

## 1. Mandatory two-stage contract

1. **Stage 1, localizar-ptbr-en (translation and localization):** the first skill reads the pt-BR original, completes all its localization steps, including its own factual audit against the Portuguese, and saves a full, self-contained English article.
2. **Stage 2, reforco-localizacao-en (this skill: analysis and adjustments in English):** only after Stage 1 has finished, open the saved English article and independently analyze and edit it, working only in English, without reopening or re-reviewing the pt-BR original. Save the reinforced version as a separate artifact.

Never run both stages simultaneously. Never review an incomplete, streaming, or unsaved Stage 1 draft. Never treat this skill as a replacement for the localization skill.

**Required inputs:**

- The complete, finalized Stage 1 English text, including headings, body, and references.
- The facts, invariants, and open ambiguities reported by Stage 1, if any.
- Any author-approved facts, terminology, constraints, or editorial decisions relevant to the article.

The pt-BR original is not an input to this stage. Do not open it, compare against it, or re-review it. If the finalized English input is missing, stop and request completion of Stage 1. Flag factual uncertainty rather than inventing a resolution.

## 2. Context first, always

No sentence, heading, metaphor, technical term, or paragraph may be edited in isolation. The unit of editing may be a phrase; the unit of understanding is the whole article.

Before editing, read the entire English article once without making changes. Establish:

- The main narrative question and the author's intended conclusion.
- The sequence of events, decisions, risks, tests, failures, and future plans.
- What the reader already knows at each point.
- The role of each section and its relationship to the surrounding sections.
- Recurring imagery, terminology, pronouns, and cross-references.
- The intended audience, publication channel, level of technical detail, and authorial voice.

Before changing a specific passage, inspect its entire paragraph, neighboring paragraphs, section heading, full section, and any relevant earlier or later passages. Check whether a seemingly awkward expression is intentional, context-dependent, or technically precise.

> A sentence that sounds good by itself can be wrong in its story. Context determines meaning; meaning determines editorial choices.

## 3. Independent native-English reading

Evaluate the English article on its own, as an English-language editor, never against the Portuguese source. Ask:

- Would a fluent US author naturally write this in this genre?
- Is any phrasing grammatical but clearly translated or stiff?
- Do verbs, prepositions, articles, pronouns, and idioms fit the context?
- Are titles idiomatic and faithful to the episodes they introduce?
- Do metaphors work for an American reader without overexplaining?
- Does the article read as continuous long-form prose rather than disconnected social-media posts?
- Do transitions, paragraph lengths, pacing, and the ending work together?
- Are technical claims phrased with appropriate precision and uncertainty?

Do not confuse unusual authorial voice with error. A distinctive but coherent expression may be worth preserving.

## 4. Mandatory issue classification

Classify each detected problem before changing it.

### Class A: objective or meaning-critical errors (MUST FIX)

- Grammar, agreement, syntax, spelling, punctuation, or typographical errors.
- Broken referents, pronouns, parallelism, or sentence logic.
- Incorrect or misleading technical terminology.
- Statements that contradict established context or change cause and effect.
- A heading that turns a possible risk into an event that actually occurred.
- Inconsistent implementation status: planned vs implemented, tested vs untested, hypothetical vs confirmed.
- Clear factual drift or internal contradiction detectable within the article or against the facts reported by Stage 1 and the author.
- Accidentally duplicated or omitted words and malformed edits.

Never downgrade a Class A issue to a stylistic preference. Correct every Class A issue that can be safely resolved. If resolving it requires facts not available, flag it as a blocking ambiguity rather than guessing.

### Class B: noticeably unnatural or editorially weak English (FIX WHEN SAFE)

- Literal calques and expressions a native writer would rarely choose.
- Unidiomatic or repetitive headings.
- Stilted phrases, awkward collocations, and needless wordiness.
- Metaphors that are understandable but culturally forced.
- Abrupt transitions, distracting repetition, or an overly list-like ending.
- Excessive qualification or overly categorical phrasing unsupported by context.

Make targeted edits when a clearly better, natural alternative preserves facts, tone, emphasis, and context. If improvement would require extensive restructuring or uncertain interpretation, record the issue and return it to Stage 1 for re-localization instead of rewriting the whole article here.

### Class C: valid stylistic choices (LEAVE ALONE)

- Two equally natural expressions with different editorial flavor.
- Unusual but coherent imagery that suits the author's voice.
- Acceptable sentence length or rhythm that does not impair comprehension.
- Differences in taste, emphasis, or register that do not damage the article.

Do not edit Class C issues. Conservatism protects good writing; it does not excuse missed errors.

### Mandatory correction of non-idiomatic English

This skill reviews an article that has **already been translated and localized into American English**. Its purpose is to improve the finished English prose, not to translate the source again.

Do not preserve a sentence merely because it is grammatically correct.

When a sentence is noticeably non-idiomatic, unnecessarily literal, syntactically awkward, or uses imprecise technical terminology, treat it as an editorial defect rather than a stylistic preference.

Correct such defects whenever a clearly more natural alternative preserves the original meaning, factual claims, narrative context, and author's voice.

Review every sentence in the context of its paragraph, section, and the complete article. Never optimize an isolated sentence at the expense of narrative continuity.

Do not rewrite sentences that already sound natural. Do not introduce new facts, technical assumptions, stronger claims, or unnecessary stylistic embellishments.

**The goal is not minimal editing at all costs. The goal is the smallest set of edits necessary to produce genuinely natural, publication-quality American English.**

## 5. Preserve the author's story and voice

Keep unchanged unless correcting a documented error:

- Events, people, numbers, dates, tools, commands, architecture, and technical decisions.
- Test outcomes, observed behavior, known limitations, and uncertainty.
- Chronology and causal relationships.
- The difference between risks and actual incidents.
- The difference between present capabilities and future intentions.
- The author's point of view, personality, restraint, humor, and level of formality.
- The article's main episodes, central argument, and substantive explanations.

Do not introduce new anecdotes, claims, motivations, emotional reactions, or security guarantees. Do not silently resolve an ambiguous technical fact by selecting a more specific English word.

For technical prose, prefer established terminology when the underlying fact supports it: context window, non-root user, hostname, rollback, acceptance criteria, name resolution, prompt injection. Do not change a generic local communication file to Unix domain socket unless the Stage 1 text or approved project records establish that detail.

## 6. Headings, metaphors, and narrative continuity

Review every heading against the entire section and the article's larger narrative. A clever heading is unacceptable if it implies something that never happened.

Check for:

- Literal translations that sound awkward in English.
- Two adjacent headings repeating the same image or phrase without purpose.
- Metaphors that contradict one another or overstay their welcome.
- A heading whose promise the section does not fulfill.
- A conclusion that merely inventories facts instead of completing the narrative.

Change headings only when the improvement is clear and contextually safe. Preserve meaningful symbolic connections; do not manufacture drama or clickbait.

## 7. Technical accuracy and calibrated claims

Inspect technical statements for both terminology and strength of claim. Distinguish:

- Configured restriction from experimentally verified protection.
- A successful limited test from a comprehensive security guarantee.
- A mock-model rehearsal from a real model interaction.
- A planned capability from an implemented feature.
- A root cause supported by evidence from a possible explanation.

Prefer exact, readable language over vague or absolute assurances. Do not claim that a service is unreachable under all conditions merely because a specific test passed.

Where a fact in the English text or the Stage 1 report is ambiguous (e.g., package vs configuration vs setup), do not guess. Preserve a truthful level of generality and flag the ambiguity for the author.

## 8. Long-form editorial standards

Preserve developed paragraphs, technical depth, narrative flow, and an appropriate professional register. Do not convert an article into short, punchy social-media fragments. Avoid formulaic transitions, overexplaining familiar concepts, repeated slogans, and unnecessary rhetorical flourishes.

Improve local pacing by adjusting punctuation, clauses, sentence order, or nearby transitions. Reorganize an entire section only if Stage 1 is explicitly re-invoked or the author authorizes a broader rewrite.

## 9. Required end-to-end workflow

1. **Validate the handoff.** Confirm that Stage 1 is complete and the entire English artifact is available. Do not start otherwise.
2. **Read the full English article cold.** Understand its story and audience without consulting the Portuguese original.
3. **Build a concise internal context map.** Identify episodes, causal links, technical invariants, implementation status, and recurring imagery.
4. **Audit every sentence and heading.** Inspect neighboring paragraphs and global dependencies; classify issues A, B, or C.
5. **Correct all resolvable Class A issues.** Escalate unresolved factual ambiguities instead of guessing.
6. **Apply safe, localized Class B improvements.** Leave Class C alone. Do not rewrite unaffected paragraphs.
7. **Re-read the complete revised English article.** Check transitions, narrative continuity, terminology, punctuation, and new errors introduced by edits.
8. **Verify the changed passages in English.** Compare every changed passage with its Stage 1 version and with the facts reported by Stage 1 and the author. Confirm that edits did not change events, causality, certainty, or implementation status. Do not reopen the pt-BR original.
9. **Run a final mechanical and editorial sweep.** Catch doubled punctuation, typos, agreement errors, awkward collocations, inconsistent names, and heading repetition.
10. **Apply the release gate and save a separate final artifact.** Never overwrite the Stage 1 output unless explicitly requested.

> **Important:** this stage is analysis and adjustment of English, not a second translation pass. If a passage looks like a possible interpretation error of the Portuguese, do not check or fix it against the original here: flag it and return the affected passage or article to Stage 1.

## 10. Release gate

The reinforced article may be marked editorially ready only when:

- All known, resolvable Class A errors are corrected.
- No unresolved meaning-critical ambiguity is hidden.
- No new factual claims, technical details, or unsupported guarantees were introduced.
- Changed passages preserve the meaning of their Stage 1 versions.
- No major unnatural-English problems remain that require Stage 1 re-localization.
- The full article has passed a second end-to-end English read.
- The final version is saved separately from Stage 1.

If there are too many Class B issues to correct locally, or a recurring pattern of translation artifacts throughout the article, fail the gate and send the article back to localizar-ptbr-en with specific examples. Do not call an incomplete rescue edit publication-ready.

A numerical score may support diagnosis but cannot override a failed release gate. Never invent a quality score or claim independent validation that did not occur.

## 11. Output contract

Deliver:

1. The complete reinforced English article, preserving its full length, headings, and references unless authorized changes are needed.
2. Word count.
3. A short change log organized by Class A and Class B, with representative before/after examples.
4. Any unresolved factual or technical questions and any issues returned to Stage 1.
5. A clear status: **Ready for author review**, **Blocked pending factual clarification**, or **Return to Stage 1**.

Do not claim that the article has been published, uploaded, scheduled, or approved by the author unless that action actually occurred. Do not expose internal reasoning or exhaustive sentence-by-sentence notes unless requested.

## 12. Relationship to other skills

- **localizar-ptbr-en** owns translation and localization from pt-BR to en-US, including every comparison with the Portuguese original, and must finish before this skill starts.
- **reforco-localizacao-en** owns second-pass analysis and native-English editing of that completed English artifact, in English only, without revisiting the pt-BR original.
- **artigo-longo-narrativo** may define the original article's narrative architecture, but this skill must not silently redesign it.
- **humanizar-posts-ptbr** must not be applied as a Portuguese stylistic rule set to English prose.

**Priority when rules conflict:**

1. Factual truth and established context.
2. Explicit author constraints.
3. Intended meaning and voice.
4. Narrative continuity.
5. Native-English naturalness.
6. Subjective style preferences.

## Final rule

This article has already been localized into English. Do not translate it again. Read the whole story as an English-language editor, correct every real error, improve only what genuinely needs improvement, and verify that nothing important changed.
