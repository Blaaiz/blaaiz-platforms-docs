# ASD-STE100 Writing Rules — Full Reference

Condensed from the ASD-STE100 specification (Issue 8). Rules are grouped as in the spec. Where the aerospace-specific rule does not translate to software documentation, the software equivalent is given.

## Section 1 — Words

- **1.1 One word, one meaning.** Use each word with a single meaning and a single part of speech throughout the document. Example: use "close" only as a verb; write "near" for proximity.
- **1.2 Approved alternatives.** When a word is not plain, replace it with the common equivalent (see `word-substitutions.md`).
- **1.3 Technical names.** Product names, commands, API fields, error codes, units, and standards are always permitted. Spell them exactly as the system does, and be consistent. In software docs, format them as `code`.
- **1.4 Technical verbs.** Domain verbs with a precise meaning ("deploy", "migrate", "authenticate", "idempotent" as adjective) are permitted when they are the established term. Define them on first use if the audience may not know them.
- **1.5 Do not invent variants.** Do not use different forms of a technical name ("payout", "pay-out", "Payout transaction") — pick one canonical form.

## Section 2 — Noun phrases

- **2.1 Max 3 nouns in a cluster.** Break longer clusters with prepositions, or define the cluster once as a technical name and reuse it.
  - Bad: "virtual card funding failure notification email"
  - Good: "the email that notifies the user when funding of a virtual card fails"
  - Also good: define "the funding-failure email" once, then reuse it.
- **2.2 Hyphenate when it clarifies.** "third-party provider", "read-only replica".
- **2.3 Always use articles and demonstratives.** Never drop "the", "a", "this". Telegraph style is prohibited.

## Section 3 — Verbs

- **3.1 Approved forms only:** infinitive, imperative, simple present, simple past, simple future, and past participle used as an adjective ("the connected device").
- **3.2 Prohibited forms:** present perfect ("has failed"), past perfect ("had failed"), gerund as a verb ("failing to connect causes…"), and complex modals ("might have been").
  - "The endpoint has been deprecated" → "The endpoint is deprecated" (state) or "We deprecated the endpoint in v2" (event).
- **3.3 Active voice in procedures — always.** Passive is tolerated in descriptive text only when the actor is unknown or irrelevant, and never two passive sentences in a row.
- **3.4 One verb, one action.** Do not use "do/make/perform/carry out + noun" where a direct verb exists.
- **3.5 "-ing" words are allowed only as:** adjectives ("the running process"), headings/gerund titles ("Configuring webhooks" is acceptable as a heading style if used consistently), or after prepositions where unavoidable ("before starting the worker" → prefer "before you start the worker").

## Section 4 — Sentences

- **4.1 Length limits.** Procedural: max 20 words. Descriptive: max 25 words. Count words honestly; hyphenated compounds count as one.
- **4.2 One topic per sentence; one instruction per procedural sentence.**
- **4.3 Do not omit words to shorten sentences** (no telegraph style). Shorten by splitting, not by dropping articles or verbs.
- **4.4 Connect sentences logically.** Use "if", "when", "after", "before", "because" — the reader must never infer the relationship between two sentences.
- **4.5 Start warnings/conditions first.** Condition → instruction. Warning → step.

## Section 5 — Procedures

- **5.1 Imperative mood.** "Run the migration." Never "The migration should be run" or "You may now want to run the migration."
- **5.2 One step, one action.** If a step contains "and" joining two actions, split it into two steps. Exception: truly simultaneous actions ("Hold SHIFT and click…").
- **5.3 Number sequential steps.** Use bullets only for unordered lists.
- **5.4 State the goal of a procedure before the steps** in one short sentence.
- **5.5 State expected results** where the reader could be unsure: "The command prints `OK`."
- **5.6 Put preconditions before step 1** (access needed, environment, state of the system).

## Section 6 — Descriptive text

- **6.1 Paragraphs: max 6 sentences, one topic.** The first sentence states the topic.
- **6.2 Vary sentence length** for readability, within the 25-word limit.
- **6.3 Use present tense for behavior:** "The API returns 402 when the balance is insufficient."
- **6.4 Tables for reference data.** Parameters, status codes, limits, and enums belong in tables, not prose.

## Section 7 — Warnings, cautions, notes

- **Warning** = risk of harm/irreversible damage (data loss, money movement, production impact).
- **Caution** = risk of breaking something recoverable.
- **Note** = helpful context, no risk.
- Place them **before** the step or section they apply to. One risk per warning. Start with the command or condition: "**Warning:** This deletes the queue. Do not run it while workers are active."

## Section 8 — Punctuation and formatting (software-doc adaptation)

- Use numbered steps, not paragraph narration, for anything the reader does.
- Use `code` formatting for every literal the reader types, sees, or receives.
- Do not use "(s)" for optional plurals — pick singular or plural.
- Do not use "and/or" — write "one or both of A and B", or restructure.
- Do not use "etc." — either the list is complete, or say "for example" with a bounded list.
- Avoid "i.e." and "e.g." — write "that is" and "for example".
- Spell out an abbreviation on first use unless it is universally known to the audience (API, URL, ID are fine; "CJ" for ClearJunction is not).
