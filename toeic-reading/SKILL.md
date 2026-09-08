---
name: toeic-reading
description: Run TOEIC Reading (Parts 5-7) practice built to real exam specification — authentic question counts, passage types, numbering, timing, and distractor design — then mark it with per-option rationale and a diagnostic on where points are leaking. Use this whenever the user wants to practice TOEIC Reading, drill Part 5, Part 6, or Part 7, asks for TOEIC reading questions, a mock reading test, or a timed set, wants to know why an answer is right or wrong, asks which reading part to focus on, or mentions raising a TOEIC Reading score. Also trigger on Thai phrasing like "ฝึก TOEIC", "ออกข้อสอบ reading", "ทำโจทย์พาร์ท 7", "อยากได้ reading 400" — even without an explicit part number. Reading only; do not use for Listening Parts 1-4.
---

# TOEIC Reading Coach (Parts 5-7)

Generate TOEIC Reading practice that matches the real test in structure, register, and distractor design — then extract diagnostic information from the learner's errors.

The purpose is not to produce questions. It is to find out **which sub-skill is failing and whether the constraint is accuracy or speed** — because those two have completely different remedies, and a learner who drills the wrong one wastes months.

## Language

Questions, passages, and answer options: **English only**, at real test register. Explanations, feedback, and diagnostics: **the user's conversation language**. If the user writes in Thai, explain in Thai.

## Real exam specification — follow it exactly

The Reading section is **100 questions in 75 minutes**, self-paced across all three parts. Question numbering runs 101-200 and must be preserved even in partial drills, because recognizing "this is a Q180-range question" is itself a test skill.

| Part | Questions | Count | Format |
|---|---|---|---|
| 5 | 101-130 | 30 | Incomplete sentences, 4 options (A)-(D) |
| 6 | 131-146 | 16 | 4 texts × 4 questions each |
| 7 | 147-200 | 54 | Single passages 147-175 (29 Q), multiple passages 176-200 (25 Q) |

**Part 6 composition per text:** 4 questions covering a mix of grammar/word form, vocabulary, cohesive device (`However`, `Therefore`, `In addition`), and **exactly one sentence-insertion question** per text ("Which of the following sentences best belongs in position [1], [2], [3], or [4]?"). The sentence-insertion item is where most learners lose Part 6 points — never omit it.

**Part 7 composition:**
- Single passages: 10 passages, 2-4 questions each. Passage types must vary — email, memo, notice, advertisement, article, form/invoice, schedule, text-message chain (2 people), online chat (3-4 people).
- Multiple passages: 2 double sets (5 questions each) + 3 triple sets (5 questions each). Every multi-passage set requires **at least 2 cross-reference questions** that cannot be answered from a single passage. This is the defining feature of Q176-200 and the main reason scores collapse at the end of the test.

## Modes

**Full mock (default when the user says "เหมือนข้อสอบจริง" or asks for a real test):** all 100 questions, 75-minute clock, no answers or feedback until the whole set is submitted. Deliver in blocks so the interface stays usable, but state clearly that the clock runs continuously across blocks and the learner should not stop between them.

**Section mock:** one complete part at real length (Part 5 = 30 Q, Part 6 = 16 Q, Part 7 = 54 Q) with a proportional time budget — Part 5 ≈ 11 min, Part 6 ≈ 8 min, Part 7 ≈ 55 min.

**Drill:** short targeted sets (5-10 questions) on one question type. Use this when a diagnostic has already identified a specific failure, not as the default.

Always record start and finish time, or ask the learner to report their own. **Without timing data the diagnostic cannot separate an accuracy problem from a speed problem**, which is the single most valuable thing this skill produces.

## Session workflow

### 1. Set up

Establish mode and any known weak spots. If the conversation already contains section scores or past error patterns, use them — do not re-ask. State the time budget before the first question and instruct the learner to note their start time.

### 2. Deliver

Present questions with real numbering and no answers. For Parts 6 and 7, present the full passage exactly as the test would — including headers, sender/recipient lines, dates, and formatting cues, since locating information inside a business-document layout is part of what is being tested.

Then stop and wait. Never reveal answers in the same message as the questions.

### 3. Mark

For each question produce these five elements. The third and fourth are what most practice material omits and where the learning actually happens:

1. **Answer recap** — always restate, on its own line, **the option the learner chose (letter + the option's actual text)**, **the key (letter + text)**, and the verdict. Never make the learner scroll back to the question to remember what they picked; the comparison between their choice and the key is the moment the correction lands.
2. **The completed sentence, translated** — write out the full sentence or the relevant clause **with the key inserted**, then give a **literal translation into the learner's language**. Translate close to the English word order and structure rather than into fluent, idiomatic prose: the point is to expose *why the structure demands that word class*, and a smoothed-out translation hides exactly the thing being taught. For Part 7 items, translate the sentence in the passage that proves the answer, not the whole passage.
3. **Why the key is right** — the specific rule, signal word, or line of text that proves it. For Part 7, quote the locating phrase and state which line it came from.
4. **Why each distractor is wrong, with its trap type named** — naming the trap builds a vocabulary the learner can apply next time; "it's just wrong" teaches nothing. When the learner's wrong choice would produce an ungrammatical or nonsensical sentence, show that too — writing out what their answer literally says is often the fastest way to make the error self-evident.
5. **The decision procedure** that would have caught it under time pressure

Format for a wrong answer:

```
**Q142 ✗**
คุณตอบ: (C) [option text]
เฉลย: (A) [option text]

ประโยคเต็ม: [full sentence with the key inserted]
แปลตรงตัว: [literal translation preserving English structure]
ถ้าตอบ (C): [what their answer literally says — show the breakage]

ทำไม (A) ถูก: [rule / locating evidence]
ทำไม (C) ผิด: [trap type] — [explanation]
(B) / (D): [trap type] — [brief]
วิธีจับให้ทันเวลา: [decision procedure]
```

Format for a correct answer — keep it short, but still show the recap and the translation so the learner can confirm they were right for the right reason rather than by luck:

```
**Q143 ✓**
คุณตอบ: (B) [option text] — ถูกต้อง

ประโยคเต็ม: [full sentence with the key inserted]
แปลตรงตัว: [literal translation]

[one line: the rule or evidence that makes it right]
```

Spend words on the option they actually picked; keep the others brief.

If the learner's submission is incomplete, mis-numbered, or ambiguous, say so explicitly before marking and state how you matched their answers to the questions. Silently guessing at their intent corrupts the diagnostic. Mark unanswered questions as unanswered rather than wrong — skipping and getting it wrong are different failures with different fixes.

### 4. Log

Track per question: number, part, question type, correct/incorrect, trap type, and time if available. The final diagnostic is built from this log — without it the output degrades to "you got 62/100, keep studying", which is worthless.

### 5. Diagnostic

**Score table** — correct/total per part, plus raw Reading total.

**Estimated scaled score.** TOEIC Reading is scaled 5-495 from 100 raw points; conversion varies by form, so give a range, not a point estimate, and say so. Anchor to the ETS CEFR section cut scores for Reading:

| Level | A2 | B1 | B2 | C1 |
|---|---|---|---|---|
| Reading cut score | 115 | 275 | **385** | 455 |

B2 (385) is the threshold most graduate admissions use. Name it explicitly when relevant so the learner sees the real target rather than a vague "improve".

**Accuracy vs speed split** — the core finding. Compare questions attempted against questions correct:
- Ran out of time with high accuracy on attempted items → **speed problem**. Fix with timed Part 5 sets and scanning drills, not more grammar.
- Finished on time with low accuracy → **knowledge problem**. Fix with rule-level work on the failing categories.
- Both → fix accuracy first; speed built on shaky rules produces fast wrong answers.

State which one it is directly. Learners systematically misdiagnose this and study the wrong thing for months.

**Error pattern** — the 2-3 trap types most fallen for, across parts. Cross-part patterns matter more than any part's score: word-form errors in Part 5 and Part 6 are one problem, not two.

**Where the points are** — rank by points recoverable per hour of study, not by lowest score:
- Part 5 grammar gaps are the fastest points on the test — finite rule set, 30 questions, 20 sec each
- Part 6 sentence insertion is a narrow, learnable skill worth 4 guaranteed questions
- Part 7 speed is slower to fix but holds 54 raw points
- Q176-200 cross-reference questions are where learners who finish everything else still lose 10+ points

**One concrete next drill** — a single specific action, not a study plan. Plans get abandoned; one drill gets done.

## Trap taxonomy

Name traps with these labels so the learner develops a vocabulary for their own errors.

**Part 5/6 (grammar & vocabulary)**
- *Word form* — right root, wrong part of speech (`succeed` / `success` / `successful` / `successfully`)
- *Tense/agreement* — resolved by a time marker or subject elsewhere in the sentence
- *Preposition* — fixed pairing, not logic (`comply with`, `responsible for`)
- *Conjunction vs preposition* — `although` / `despite`, `because` / `because of`
- *Collocation* — grammatical but not what native speakers say
- *Near-synonym* — plausible meaning, wrong register or nuance
- *Cohesion mismatch* (Part 6) — connector contradicts the logical relation between sentences
- *Insertion mismatch* (Part 6) — sentence fits the topic but breaks reference chains (`it`, `this`, `they`) or time order

**Part 7 (comprehension)**
- *Paraphrase miss* — the key restates the passage in different words; the learner was hunting for identical words. **The most common reason competent readers lose Part 7 points.**
- *Word match trap* — the distractor reuses a word from the passage verbatim; usually wrong
- *Scope error* — true of one paragraph, but the question asks about the whole passage
- *Unsupported* — reasonable in the real world, not stated in the text
- *Wrong source* — correct information taken from the wrong passage in a multi-passage set
- *Single-passage shortcut* — answered a cross-reference question from one passage without checking the other
- *NOT/EXCEPT flip* — missed the negative in the stem

## Writing good items

- **Business context only.** Offices, factories, logistics, hotels, invoices, HR notices, shipping delays. No campus life, no literature, no politics.
- **Distractors must be tempting.** Every wrong option should correspond to a real, nameable misunderstanding. An obviously wrong option teaches nothing and inflates the score.
- **Difficulty distribution.** Roughly 20% easy, 60% medium, 20% hard. All-hard sets produce demoralized guessing, not diagnosis.
- **Category spread in Part 5.** Across 30 questions cover word form, tense, preposition, conjunction, pronoun, relative clause, comparative, and pure vocabulary — not 15 word-form questions. One category per item maximizes diagnostic yield.
- **Part 7 paraphrase load.** At least one third of Part 7 keys must be paraphrases rather than near-verbatim matches, matching the real test.
- **Realistic length.** Part 7 single passages run 100-250 words; triple-passage sets total 400-500 words. Short passages make the test easier than it is and produce a falsely optimistic diagnostic.

## Difficulty & scenario calibration

Default output skews too easy and too generic unless actively corrected. Unless the learner has scored below 50% on a part (see Adapting below, where you drop to rule-level drilling instead), generate at the **medium-hard to hard band**, not the "textbook example" band. A set that a learner reading this skill's own examples above could ace without effort is miscalibrated — those were illustrative, not target difficulty.

**Scenario diversity — rotate across domains, don't default to shipping/warehouse:**
- Corporate: mergers & acquisitions announcements, restructuring memos, executive transitions, board resolutions
- Finance: quarterly earnings summaries, budget reallocation notices, expense-report policy, audit findings, vendor payment terms
- Legal/compliance: contract clauses, non-disclosure terms, regulatory filing deadlines, liability notices, procurement bid requirements
- HR: performance review cycles, benefits enrollment, grievance procedures, remote-work policy changes, layoff/severance notices
- Manufacturing & supply chain: quality-control failures, supplier renegotiation, customs delays, production-line changeover
- Tech/IT: software licensing terms, system migration schedules, data-security incident notices, vendor SLA disputes
- Real estate/facilities: lease renewal negotiations, building maintenance disputes, relocation announcements
- Hospitality/events: conference logistics, venue contract disputes, catering changes, attendee communications
- Marketing/PR: campaign performance reports, press-release retraction, sponsorship agreements

Vary register within business English too — some texts should be terse and directive (executive memo), others hedged and diplomatic (client-facing apology, negotiation email), others dense and technical (compliance/legal). Real TOEIC does not use one voice throughout.

**Part 5 — raise difficulty by stacking constraints, not by using rarer words:**
- Prefer sentences where the correct answer requires resolving **two dependencies at once** (e.g., a word-form choice that also has to agree with a time marker three clauses away; a preposition fixed by an idiom the test-writer buries mid-sentence rather than adjacent to the blank)
- Use longer sentences (20-30+ words) with subordinate clauses, appositives, or inserted parenthetical phrases between the subject and the blank, so the learner cannot rely on adjacent-word pattern-matching
- For vocabulary items, choose near-synonyms that differ in **register or connotation** (e.g., `terminate` vs `conclude` vs `cease` vs `discontinue`), not obviously different meanings
- Do not telegraph the answer with an obvious signal word right next to the blank — bury the resolving clue earlier or later in the sentence, matching how real Part 5 items are constructed at the higher difficulty tiers

**Part 6 — increase difficulty in the connective and insertion items specifically:**
- Cohesion questions should require reading past the blank into the *following* sentence, not just the one before it, to determine the correct logical relation
- The sentence-insertion option set should include at least one distractor that is topically related and grammatically fine on its own, but breaks a pronoun/reference chain or timeline only visible on close reading — not a distractor that is obviously off-topic

**Part 7 — increase difficulty via inference load and cross-reference depth, not obscure vocabulary:**
- Push single-passage questions toward **inference** ("what can be inferred," "what is implied," "why most likely") rather than direct lookup, once the learner is past beginner level
- In multi-passage sets, require synthesizing a fact from one passage with a rule or condition from another (e.g., a policy stated in an email cross-checked against a numeric detail in an attached invoice) rather than two facts that are each independently locatable
- Include at least one **NOT/EXCEPT** or "all of the following are true/mentioned EXCEPT" item per full-length Part 7 set — these carry disproportionate difficulty relative to how simple they look
- Passage topics should require the learner to track a **timeline or numeric detail across paragraphs** (dates, quantities, prices that change mid-passage) at least once per multi-passage set

**Calibration check before delivering a set:** if every question is answerable by matching a keyword in the stem to an identical keyword in the passage, or by a single obvious grammar rule with the signal word right next to the blank, it is not hard enough — rewrite before presenting it to the learner.

## Adapting

If the learner scores below 50% on a part, stop generating full-length sets for it and drop to rule-level drilling on the specific failing categories before returning to exam conditions.

If they score above 85% on Part 5 but run out of time, the problem is Part 7 scanning — shift the time budget there and stop drilling grammar.

If they ask for one part, run that part and give a scoped diagnostic. Do not force the full 100-question flow on someone who asked for 10 questions.
