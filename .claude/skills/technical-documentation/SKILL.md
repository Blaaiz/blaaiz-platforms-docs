---
name: technical-documentation
description: Use whenever writing or editing technical documentation of any kind — user guides, API documentation, runbooks, README files, integration guides, procedures, manuals, onboarding docs, help-center articles, or in-app instructional text. Triggers on "write docs", "document this", "user guide", "runbook", "API reference", "integration guide", "how-to", "manual", "STE", "simplified technical english". Enforces ASD-STE100 Simplified Technical English writing rules.
---

# technical-documentation

Write all technical documentation in ASD-STE100 Simplified Technical English (STE). These rules are mandatory, not stylistic suggestions. The goal: text that a non-native English reader can understand on first read, with zero ambiguity.

## Procedure

1. Identify the text type for each section you write:
   - **Procedural** — steps the reader performs (instructions, runbooks, setup guides)
   - **Descriptive** — explanations of what something is or how it behaves (concept docs, API references, overviews)
2. Read `references/ste-rules.md` before writing. When choosing words, check `references/word-substitutions.md`.
3. Write the document applying the Core Rules below.
4. Run the Self-Check (bottom of this file) against your draft before presenting it. Fix every violation.

## Core Rules (always apply)

### Sentences

- Procedural sentences: **max 20 words**. Descriptive sentences: **max 25 words**.
- **One instruction per sentence.** Never chain steps with "and" / "then" inside one sentence — split into numbered steps.
- Start an instruction with the command verb: "Remove the panel", not "You should now remove the panel" or "The panel must be removed."
- Descriptive paragraphs: max 6 sentences, one topic per paragraph. Vary sentence length; do not write 6 near-identical short sentences in a row.

### Verbs

- **Active voice only in procedures.** Passive is permitted (sparingly) in descriptive text only when the actor is genuinely unknown or irrelevant.
- Use only simple verb forms: imperative ("Connect the cable"), infinitive ("to connect"), simple present ("the system sends"), simple past ("the request failed"), simple future ("the job will run").
- **No gerunds as verbs** ("connecting the cable causes…" → "when you connect the cable…"). No perfect tenses ("has been deprecated" → "is deprecated" / "was deprecated in v2").
- No vague helper verbs where a direct verb exists: "carry out a check" → "check"; "make a selection" → "select"; "perform validation" → "validate".

### Words

- **One word = one meaning.** Pick one term per concept and use it everywhere. Never alternate synonyms for variety ("endpoint" vs "route" vs "URL" — pick one). Build a mini-glossary for the document if terms could collide.
- Prefer the short, common word: "use" not "utilize", "start" not "commence", "do" not "perform", "send" not "transmit" (unless "transmit" is the domain term).
- Technical names (product names, API field names, error codes, commands) are always allowed — spell them exactly as they appear in the system, and format them as `code`.
- Check `references/word-substitutions.md` for the banned-word → approved-word table.

### Structure

- **Max 3 nouns in a cluster.** "payout provider retry counter value" → "the value of the retry counter for the payout provider", or hyphenate/define it once as a technical name.
- Always use articles ("the", "a") — do not drop them telegraph-style. "Insert bolt in bracket" → "Insert the bolt into the bracket."
- Write warnings and cautions **before** the step they apply to, as a separate line, starting with the condition or the command: "**Warning:** Do not run this against production."
- Use a numbered list for sequential steps, a bulleted list for unordered items, a table for reference data. Never bury a 4-step procedure in a paragraph.

### Clarity

- Name the actor. "The webhook is retried" → "Blaaiz retries the webhook" or "The queue worker retries the webhook."
- Resolve every pronoun. If "it" / "this" / "they" could point to two things, repeat the noun.
- Quantify. "shortly after" → "within 30 seconds"; "a large payload" → "a payload larger than 1 MB". If you cannot quantify, say what the reader can observe instead.
- State conditions before instructions: "If the status is `FAILED`, retry the payout" — never "Retry the payout if the status is `FAILED`" in procedures.

## Self-Check (run before presenting)

Go through the draft and confirm:

1. No procedural sentence over 20 words; no descriptive sentence over 25.
2. Every instruction is imperative, active voice, one action.
3. No gerund-as-verb, no perfect tense, no "should/could be done" hedging in procedures.
4. Each key concept has exactly one name, used consistently throughout.
5. No noun cluster longer than 3 nouns; no missing articles.
6. Warnings precede their steps; conditions precede their instructions.
7. Every pronoun has an unambiguous referent; every vague quantity is made concrete.
8. Scan for the top banned words (`references/word-substitutions.md`) and replace them.

If the user pastes existing documentation for editing, apply the same rules and flag (briefly) the categories of STE violations you fixed.

## Scope notes

- These rules govern documentation prose. They do **not** apply to code samples, API payloads, config files, or quoted output — reproduce those exactly.
- Marketing copy, emails, and chat responses are out of scope unless the user asks for STE explicitly.
- When STE strictness conflicts with an exact technical name or a legal/compliance phrase, the exact phrase wins — keep it and simplify the text around it.
