# Bloom's Taxonomy: Computing in Python I

**Drill routine and mastery roadmap**
**Course:** GTx — Computing in Python I: Fundamentals and Procedural Programming
**Window:** 19 September → 31 October 2026
**Taxonomy:** Revised (Anderson & Krathwohl, 2001), with the AI-versus-human layer applied

---

## Quick Reference

Mastery of this course does not look like finishing seven chapters. It looks like being
handed a requirement in plain English, writing code that satisfies it with nothing open,
predicting what that code will print before running it, and defending why you structured it
the way you did.

Bloom's is the right lens here for one specific reason. Your record shows four attempts at
Python foundations since May, and every one of them reached **Level 2, Understanding**, then
stopped. L01 Variables was logged as "Done (deep)." The Learning Notebook holds written
explanations of falsy values, short-circuit evaluation and loops. That is real Level 2 work,
produced three separate times. What has never been produced is a Level 6 artifact.

**The pattern is not a motivation problem. It is a taxonomy problem.** Each attempt built a
better Level 1–2 apparatus — notes, guides, explanations, plans — and never crossed into the
levels where something has to run.

A note on numbering: levels 1 through 3 are identical in both the original and revised
taxonomies, so the "Bloom's Level 3" bar you set in the Python Foundations plan still means
the same thing here. The revised version is used because Creating sits at the top, which is
where this course has to land, and because it carries the AI layer below.

### The AI boundary, and why it is the whole game

Claude can perform Levels 1 through 4 for you instantly and convincingly. It can recall
syntax, explain concepts, apply patterns, and analyze your code. Those levels are no longer
proof of anything on their own.

| Level | Claude can | You must |
|---|---|---|
| 1 Remembering | Recite any syntax rule on demand | Choose what is worth holding without lookup |
| 2 Understanding | Explain, paraphrase, summarize | Build the model that survives the explainer leaving |
| 3 Applying | Write the working code | Write it under a closed-book constraint |
| 4 Analyzing | Find your bug, diagram your logic | Decide which bugs reveal a real gap |
| 5 Evaluating | Critique against stated criteria | Defend a choice when criteria conflict |
| 6 Creating | Generate a program from a prompt | Own it, ship it, explain it cold |

**Operating rule for this window:** Claude is allowed at Levels 1, 2 and 4. Claude is
forbidden at Level 3 and Level 6 until your attempt exists in a file. This is the single
constraint that separates this attempt from the previous three.

---

## Topic Decomposition

The seven chapters resolve into four components plus one cross-cutting method.

| Component | Chapters | The core question |
|---|---|---|
| **A · Execution model** | 1 Computing, 2 Programming | How does text become behavior? |
| **B · Procedure and sequence** | 4 Procedural Programming | Why does order determine result? |
| **C · State and types** | 5 Variables | What is stored, under what name, as what kind of thing? |
| **D · Operators** | 6 Logical, 7 Mathematical | How is a new value computed from existing ones? |
| **Spine · Debugging** | 3 Debugging | Not a topic. The feedback loop that runs across all four. |

Treating Chapter 3 as a method rather than a unit matters. Debugging is where Levels 2 and 4
actually get tested, and it is the only chapter whose content you will use every single
session regardless of which other chapter you are in.

---

# The Six Levels

## Level 1 — Remembering

**What this means here:** Reproducing syntax, operator symbols, type names and error
categories from memory, with no editor and no reference open.

**Key verbs:** State · List · Label · Reproduce · Identify

**Learning objectives**
- **List** the six comparison operators and the three logical operators using correct Python syntax.
- **State** the difference in output between `/`, `//` and `%` for a given pair of integers.
- **Label** any error message as syntax, runtime or semantic within five seconds of reading it.
- **Reproduce** the `input()` to cast to compute to `print()` skeleton from a blank file.

**Study questions**
- What are the four built-in types this course uses, and what does each literal look like?
- Which operator returns the remainder, and which returns the floor?
- What does `input()` always return, regardless of what the user typed?
- What are the three error categories, and which one produces no error message at all?

**Drill / assessment:** Cold Recall, 5 minutes, written. Blank page, no editor.

**AI boundary:** Claude may quiz you. Claude may not answer for you. If you reach for the
answer instead of the gap, the drill produced nothing.

---

## Level 2 — Understanding

**What this means here:** Predicting what a program will do before it runs, and restating
why in your own words.

**Key verbs:** Predict · Trace · Explain · Distinguish · Translate

**Learning objectives**
- **Trace** a ten-line program line by line, recording every variable's value at each step, before executing it.
- **Predict** the printed output of a program containing mixed integer and float arithmetic, and account for any type change.
- **Explain** to a non-programmer why `"5" + "3"` and `5 + 3` produce different results.
- **Distinguish** a runtime error from a semantic error using the program's behavior alone.

**Study questions**
- Why does `int(input())` fail when the user types `4.5`, and what does that reveal about casting?
- What is actually stored when you write `x = y`, and what happens to `x` if `y` changes afterward?
- Why does `and` stop evaluating once it hits a false value, and when would that matter?
- Why is a semantic error more dangerous than a syntax error?

**Drill / assessment:** Trace Table and Predict-Then-Run. Both written before execution.

**AI boundary:** Claude may check your trace after you have written it. Not before.

---

## Level 3 — Applying

**What this means here:** Turning a requirement stated in plain English into working code,
closed-book, from an empty file.

**Key verbs:** Construct · Compute · Solve · Write · Transfer

**Learning objectives**
- **Write**, with nothing open, a program that reads three campaign figures and prints open rate and click-through rate to one decimal.
- **Compute** a benchmark flag using logical operators without using an `if` statement.
- **Construct** a program that handles integer division correctly when the denominator may be zero.
- **Transfer** a formula you use in a spreadsheet into working Python without consulting the formula.

**Study questions**
- Given a requirement for cost per acquisition, what inputs must the program take and in what type?
- How do you round to one decimal place for display without corrupting the stored value?
- How do you express "opened and not unsubscribed" as a single boolean expression?

**Drill / assessment:** Blank Page Build, timed, 20–25 minutes, everything closed.

**AI boundary:** **Closed.** No Claude, no search, no notes until your attempt exists in a
file and has been run. This is the level all three previous attempts skipped.

---

## Level 4 — Analyzing

**What this means here:** Taking apart working or broken code to find where the behavior and
your model of it diverge.

**Key verbs:** Diagram · Differentiate · Deduce · Categorize · Test

**Learning objectives**
- **Categorize** every error produced in a session into syntax, runtime or semantic, and record the root cause.
- **Deduce** from wrong output alone which line introduced the defect, before adding any print statements.
- **Diagram** the flow of a program from input through each transformation to output.
- **Test** a program against a deliberately hostile input and identify what it fails to handle.

**Study questions**
- Your rate calculation returns 0 for every campaign. What are the three most likely causes, ranked?
- Why does this program produce the correct answer for one input and a wrong one for another?
- Which of your variable names would confuse a reader, and what does that reveal about your model?
- Where does this program assume something about its input that it never checks?

**Drill / assessment:** Error Triage log and Break It.

**AI boundary:** Claude is genuinely useful here and allowed. Rule: form your own hypothesis
first and write it down. Then ask. A hypothesis you never committed to cannot be corrected.

---

## Level 5 — Evaluating

**What this means here:** Judging between two versions that both work, and defending the
choice when the criteria pull against each other.

**Key verbs:** Justify · Critique · Rank · Defend · Assess

**Learning objectives**
- **Justify** your choice of variable names and structure to a reader who has never seen the program.
- **Critique** a working alternative implementation on readability, correctness at the edges, and extensibility.
- **Rank** three ways of handling a division-by-zero case and defend the one you shipped.
- **Assess** whether a piece of code is finished, using criteria you wrote down in advance.

**Study questions**
- You have two versions that both produce correct output. Which ships, and what is the argument?
- Is it better to crash loudly on bad input or return a default? Defend your answer for this specific tool.
- When does adding a comment signal clarity, and when does it signal that the code failed to be clear?
- What would a reviewer criticize first, and are they right?

**Drill / assessment:** Refactor Judgment — write two versions, then argue in writing for one.

**AI boundary:** Claude may argue the opposing side. Claude may not pick. The defense has to
be yours or the level did not happen.

---

## Level 6 — Creating

**What this means here:** A working program that solves a problem you chose, exists in
public, and can be explained cold.

**Key verbs:** Design · Construct · Integrate · Compose · Validate

**Learning objectives**
- **Design** the input, processing and output contract for Campaign Readout before writing a line of it.
- **Integrate** every Course I chapter into one program — variables, casting, both operator families, and a debugging trace.
- **Compose** a README that a non-programmer can follow to run the tool.
- **Validate** the finished tool against five realistic campaign scenarios, including two designed to break it.

**Study questions**
- What does this tool do that a spreadsheet does not, and is that honest?
- What is the next layer, and what does the course have to teach you first?
- Can you explain this program end to end, from memory, in ninety seconds?

**Drill / assessment:** Ship a Layer — one artifact version per week, committed publicly.

**AI boundary:** **Closed for the first draft of every layer.** Claude may review after the
layer is committed. This is the level the whole window is graded on.

---

# The Drill Library

Eight named drills. Each has a fixed duration and a level it serves. Run them by name so a
session never becomes unstructured reading.

| Drill | Level | Time | What you do |
|---|---|---|---|
| **Cold Recall** | 1 | 5 min | Blank page. Write yesterday's syntax, operators and rules from memory. Score against the reference only after the page is full. |
| **Trace Table** | 2 | 8 min | Take a program. On paper, record every variable's value after every line. Then run it and diff against your table. |
| **Predict-Then-Run** | 2 | 5 min | Write the exact expected output before executing. Any mismatch becomes an Error Triage entry. |
| **Blank Page Build** | 3 | 20–25 min | A requirement in plain English. Empty file. Timer. Nothing open. Produce running code. |
| **Error Triage** | 4 | 5 min | Log every error hit this session: category, root cause, fix. Runs at the close of every session without exception. |
| **Break It** | 4 | 10 min | Deliberately introduce one bug into working code. Walk away for a minute. Return and diagnose from the behavior alone. |
| **Refactor Judgment** | 5 | 10 min | Write a second version of something that already works. Argue in writing which ships. |
| **Ship a Layer** | 6 | 30–45 min | Add one chapter's worth of capability to Campaign Readout. Commit it. Weekly, not daily. |

## Error Triage taxonomy

This deliberately mirrors the three-type defect log you already run for calculus, so the same
habit serves both projects.

| Code | Python category | What it means | Remediation |
|---|---|---|---|
| **A** | Syntax error | Typo, missing colon, unbalanced parenthesis. The model is fine. | Slow down. Read the line above the reported one — the cause is often there. |
| **B** | Runtime error | Wrong type, division by zero, bad cast. A rule was misapplied. | Add to Cold Recall. Drill five targeted cases. |
| **C** | Semantic error | It runs and the answer is wrong. No message appears. | Stop coding. Build a Trace Table by hand. This is a model failure, not a code failure. |

**Type C is the one that matters.** A program that crashes tells you it is broken. A program
that silently computes the wrong open rate does not — and that is precisely the failure mode
that would embarrass you in a campaign readout.

---

# The Ladder Drill — the daily session

45 minutes, four blocks, climbing the taxonomy in order. It fits inside the 55-minute habit
you already run for calculus, with margin.

| Block | Time | Level | Activity |
|---|---|---|---|
| **1 · Recall** | 5 min | 1 | Cold Recall on yesterday's material. No editor open. |
| **2 · Predict** | 8 min | 2 | Trace Table or Predict-Then-Run on today's new construct. Written before execution. |
| **3 · Build** | 25 min | 3 → 6 | Blank Page Build, or Ship a Layer on artifact days. Closed book. The core of the session. |
| **4 · Interrogate** | 7 min | 4 → 5 | Error Triage log, plus one Break It or Refactor Judgment. |

**Three non-negotiables.**

1. **Block 3 is closed-book.** Notes, search and Claude stay shut until your attempt is in a
   file and has been run. This is the rule the whole routine exists to enforce.
2. **Block 4 never gets cut for time.** If the session is short, shorten Block 3. An
   untriaged error is a defect you will meet again without recognizing it.
3. **Blocks 1 and 2 stay written.** Mental rehearsal feels like recall and is not.

**Frequency:** five sessions a week. Four Ladder Drills plus one Ship a Layer session where
Block 3 expands to 40 minutes and Blocks 1 and 2 are skipped.

---

# The Roadmap

Six weeks, with the Bloom target rising. The course content is nearly flat in difficulty,
so the roadmap climbs by changing **what you do with it**, not by changing the material.

| Week | Dates | Chapters | Bloom ceiling | Drill emphasis | Gate |
|---|---|---|---|---|---|
| **S0** | Sep 19–20 | Ch 1 Computing | 1–2 | Cold Recall, diagnostic | Repo exists, first commit |
| **1** | Sep 21–27 | Ch 2 Programming · Ch 3 Debugging · Ch 4 Procedural | 2 → 3 | Trace Table daily. Error Triage becomes habit. | v0.1 runs. Ten triage entries logged. |
| **2** | Sep 28–Oct 4 | Ch 5 Variables · Ch 6 Logical · Ch 7 Mathematical | 3 → 4 | Blank Page Build daily. Break It twice. | **v1.0. Course I complete. Every chapter at Level 3, closed-book.** |
| **3** | Oct 5–11 | Course II: conditionals | 4 | Break It, Error Triage, first Refactor Judgment | v1.1 branching. A Type C bug found by trace, not by luck. |
| **4** | Oct 12–18 | Course II: loops | 4 → 5 | Refactor Judgment twice | **v2.0 multi-campaign. One written design defense.** |
| **5** | Oct 19–25 | Course II: remaining | 5 | Refactor Judgment, hostile-input testing | v2.5. Five scenarios pass, two of them adversarial. |
| **6** | Oct 26–31 | None. Consolidation. | 6 | Ship a Layer, cold explanation rehearsal | **v3.0 published. Ninety-second cold walkthrough recorded.** |

**Week 6 adds no new course material on purpose.** Creating is a level, not a leftover. Every
previous attempt ran out of calendar before it reached the top of the ladder, because the
calendar was filled with Levels 1 and 2 to the last day.

## Chapter-to-level targets

By the Gate 1 date of 4 October, each chapter should sit at the level in the right column.
Not every chapter needs to reach 6.

| Chapter | Target by Oct 4 | Evidence that proves it |
|---|---|---|
| 1 · Computing | 2 | Explain source versus execution without notes |
| 2 · Programming | 3 | Write and run a program from a blank file |
| 3 · Debugging | **4** | Triage log with correct categories and root causes |
| 4 · Procedural Programming | **4** | Diagram your own program's flow; reorder it and predict the break |
| 5 · Variables | **4** | Trace table with zero mismatches on a ten-line program |
| 6 · Logical Operators | 3 | Benchmark flag computed correctly with no `if` available |
| 7 · Mathematical Operators | 3 | Rate math correct, including the integer-division trap |

---

# Mastery Gates

How to know a level actually happened, rather than feeling like it did. Each gate is
pass/fail and self-scored honestly.

| Level | Gate | Fails if |
|---|---|---|
| 1 | Write the operator set and error categories from a blank page in under 3 minutes | You reach for anything |
| 2 | Trace a ten-line program with zero value mismatches | You run it first to check |
| 3 | Requirement to working code in 25 minutes, nothing open | You open Claude, notes or search before your file runs |
| 4 | Diagnose a Type C bug from behavior alone, before adding print statements | You fix it by trial and error without naming the cause |
| 5 | Two working versions, one written paragraph defending the shipped one | The defense is "it felt cleaner" |
| 6 | Public repo, README, ninety-second cold explanation | You need the code open to explain it |

**Your existing crystallization standard already encodes levels 2, 3 and 4:** explain it to a
non-programmer from a cold start, write working code from a requirement without looking
anything up, and identify one edge case the happy path misses. All three, not two of three.
That standard was correct. It was never applied to a finished thing. Levels 5 and 6 above are
the extension it was missing.

---

# Domain Notes

**Calibration used.** Technical tools normally emphasize Levels 2 through 4 — how it works
and why. That calibration is overridden here. For this learner the binding constraint is
crossing into 5 and 6, because the documented failure pattern is four consecutive stalls at
Level 2. The roadmap therefore front-loads Level 3 harder and earlier than a general Python
course would.

**The course cannot reach Level 6 on its own.** Computing in Python I stops before
conditionals and loops, so the largest thing buildable with its toolkit is a single-pass
calculator. That is why Creating is anchored to the Campaign Readout artifact, which keeps
growing after the course ends, rather than to any course exercise. The course supplies
Levels 1 through 4. The artifact supplies 5 and 6.

**Levels 1 and 2 are cheap here and should be treated that way.** Seven chapters of
introductory material with two-to-three-minute videos and auto-graded questions will produce
Level 1 and 2 competence almost as a side effect. Do not build study infrastructure for
them. The temptation to make beautiful notes on Chapter 5 Variables is the exact shape of the
previous three attempts.

**Type C errors are the real curriculum.** Syntax errors are announced by the interpreter and
teach little. Semantic errors — the program runs, the number is wrong, nothing complains —
are where the trace table, the hand-drawn model and genuine Level 4 analysis get built. Seek
them deliberately.

**The AI boundary is the load-bearing rule.** Every level here is achievable in seconds by
asking Claude. That makes levels 3 and 6 unfalsifiable unless you close the tool first. The
closed-book constraint on Block 3 is not pedagogical purity; it is the only mechanism that
makes the whole ladder mean anything for someone learning alongside a capable assistant.

---

## Changelog

- **2026-09-19** — Created. Revised taxonomy with AI layer. Window 19 Sep → 31 Oct 2026.
