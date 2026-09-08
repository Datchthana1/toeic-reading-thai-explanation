# toeic-reading

A Claude Skill for TOEIC Reading (Parts 5–7) practice, built to the real exam specification.

Most TOEIC practice material tells you which answer is correct. This skill is built around a different premise: knowing the key is worth little compared to knowing **why the distractor you picked was attractive**, and whether your score is capped by knowledge or by pace. Those two failure modes have completely different remedies, and learners routinely misdiagnose which one they have.

## What it does

- Generates TOEIC Reading items at real exam specification — authentic question counts, numbering (101–200), passage types, lengths, and difficulty distribution
- Marks each answer with the option you chose, the key, the rule or line of text that proves it, and **why each distractor is wrong, with its trap type named**
- Produces an end-of-session diagnostic that separates **accuracy problems from speed problems** and ranks study targets by points recoverable per hour

## Exam specification implemented

| Part | Questions | Count | Format |
|---|---|---|---|
| 5 | 101–130 | 30 | Incomplete sentences, four options |
| 6 | 131–146 | 16 | Four texts, four questions each, one sentence-insertion item per text |
| 7 | 147–200 | 54 | Single passages (147–175) plus double and triple passage sets (176–200) |

Full section: 100 questions, 75 minutes.

## Modes

| Mode | Scope | Use it when |
|---|---|---|
| Full mock | 100 questions, 75-minute clock | Establishing a baseline or simulating test day |
| Section mock | One complete part at real length | Isolating a single part under real time pressure |
| Drill | 5–10 questions on one question type | A diagnostic has already named the failing skill |

## Trap taxonomy

The skill labels errors rather than merely marking them, so you build a vocabulary for your own mistakes.

**Parts 5 and 6** — word form, tense/agreement, preposition, conjunction vs preposition, collocation, near-synonym, cohesion mismatch, insertion mismatch

**Part 7** — paraphrase miss, word match trap, scope error, unsupported, wrong source, single-passage shortcut, NOT/EXCEPT flip

## Installation

**Claude.ai / Claude Desktop** — package the skill folder and install it from the file card:

```bash
cd skills && zip -r toeic-reading.skill toeic-reading/
```

Upload the resulting `.skill` file in a conversation and choose **Save skill**.

**Claude Code** — place the skill folder in your skills directory:

```bash
cp -r skills/toeic-reading ~/.claude/skills/
```

## Usage

Once installed, the skill triggers on requests such as:

- "ฝึก TOEIC Reading หน่อย"
- "Give me a Part 5 section mock"
- "ออกข้อสอบพาร์ท 7 มา 10 ข้อ"
- "Which reading part should I focus on?"

Report your elapsed time along with your answers. Without timing data the diagnostic cannot distinguish a speed problem from a knowledge problem, which is the most useful thing it produces.

## Scoring reference

TOEIC Reading is scaled 5–495. ETS CEFR section cut scores for Reading:

| Level | A2 | B1 | B2 | C1 |
|---|---|---|---|---|
| Cut score | 115 | 275 | 385 | 455 |

B2 (385) is the threshold most graduate programs require.

## Scope

Reading only. Parts 1–4 are audio and cannot be meaningfully practised in a text interface; use official audio materials for those.

## License

MIT
