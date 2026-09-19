# Computing in Python I · The October Window

**Vision, Product Roadmap & Narrative**
**Course:** GTx — Computing in Python I: Fundamentals and Procedural Programming (Georgia Tech, edX, David Joyner)
**Horizon:** Saturday 19 September → Saturday 31 October 2026
**Owner:** Nevin Fuentes

---

## 0. What this course actually is

| | |
|---|---|
| Format | Self-paced, introductory, no prerequisites |
| edX estimate | 5 weeks at 9–10 hours per week |
| Structure | 2–3 minute videos, multiple choice, auto-graded coding problems |
| Exams | None. No proctoring, no final |
| Chapters | 7 |

**The seven chapters:** Computing · Programming · Debugging · Procedural Programming ·
Variables · Logical Operators · Mathematical Operators.

Two facts about that list matter more than anything else in this document.

**First, the course stops before conditionals and loops.** `if` statements and `for` loops
are Course II: Control Structures. Course I is sequential code only: declare variables,
apply operators, print results, and debug.

**Second, you have already done most of this.** Your own re-baselined roadmap records L01,
Variables and the Memory Model, as "Done (deep) — full Learning Guide covered." Your
Learning Notebook contains written work on conditionals, short-circuit evaluation, falsy
values and loops, with marketing examples. That is Course II material, already touched.

So the edX estimate of 45–50 hours is calibrated for someone who has never seen a variable.
**Your real completion time for Course I is closer to 12–18 hours.** Planning October as if
this course will fill it is the central risk, and the roadmap below is built to avoid it.

---

# Part 1 — Vision

## 1.1 The near-horizon vision statement

> By 31 October I will have finished Computing in Python I and published one working thing
> that someone else can open and run. Not a plan for a thing. Not a curriculum for the thing.
> The thing. This is the fourth time I have started Python foundations, and the difference
> this time is not the syllabus — the syllabus was never the problem. The difference is that
> the deliverable is an artifact instead of a schedule.

**Anchor for the window:** *Finish the course fast. Ship the artifact anyway.*

## 1.2 The product vision statement

**For** a lifecycle and CRM marketer pivoting toward analytics,
**who** has restarted Python foundations four times without producing an inspectable artifact,
**Computing in Python I** is a self-paced procedural programming course
**that** supplies the formal scaffolding and the credential,
**unlike** the three previous attempts, which each produced a better plan than the last and
no running code,
**it** is treated here as an input on a two-week clock, not as October's destination — the
destination is a published tool that turns campaign numbers into a performance readout.

## 1.3 What "done" means on 31 October

This is deliberately not "course complete."

1. **Course I finished.** All seven chapters, every coding problem attempted.
2. **One public artifact.** A GitHub repository containing a working campaign-metrics tool,
   a README a non-programmer can follow, and a commit history showing it grew week by week.
3. **The certificate decision made and closed.** Audit or verified, decided once, not
   carried as an open loop into November.
4. **No fifth plan.** No new roadmap page, no re-baseline, no re-sequenced curriculum
   created between now and 31 October.

## 1.4 Anti-goals

- **Not** a new learning system. You have four. The fifth will not be the one.
- **Not** local environment setup in week one. See §2.6, risk R3.
- **Not** pandas, APIs or AI agents. Those are M2 through M4 in the re-baselined roadmap and
  they have waited this long.
- **Not** running the LearnKey/Certiport track and this course in parallel. One anchor.
  That is your own Anti-Dabbling Rule 1.

---

# Part 2 — Product Roadmap

## 2.1 The governing constraint, from your own strategy

Your Career Upskilling Strategy, written 10 September, already decided how this works:

> *If the Python course starts: Python becomes the anchor for the duration of the course.
> SQL moves to maintenance. Every major Python concept should be connected to an analytical
> use case. Avoid treating syntax exercises as the end product.*

And the weekly rule from the same document:

> *Replace "What should I study this week?" with "What visible piece of evidence will exist
> by the end of this week?"*

This roadmap is that rule applied to seven chapters. Every week below has an artifact
column, and the artifact column is the one that counts.

## 2.2 The artifact: Campaign Readout

One tool, built in layers, where each layer is the chapter you just finished. It takes raw
campaign counts and returns a formatted performance readout with benchmark flags.

This is chosen specifically because it is buildable with Course I's restricted toolkit —
sequential code, variables, operators, input and output, no loops required — and because it
sits in the domain you already know.

| Chapter | What it adds to the artifact |
|---|---|
| 1 · Computing | Repository created, environment confirmed, first commit |
| 2 · Programming | The file runs end to end and prints something |
| 3 · Debugging | Break it deliberately; keep a written trace of each error and its fix |
| 4 · Procedural Programming | The input → process → output skeleton |
| 5 · Variables | Named metric variables; casting raw input strings to numbers |
| 6 · Logical Operators | Benchmark flags — above or below target, eligible to scale |
| 7 · Mathematical Operators | The rate math — open rate, CTR, conversion, cost per acquisition, revenue per send |

By the end of Course I the tool computes real campaign metrics from real inputs. After
Course II adds conditionals and loops, the same tool extends to handle many campaigns at
once. It grows. It does not get replaced by a new project.

## 2.3 Week by week

Sprint 0 is this weekend. Weeks run Monday to Sunday.

| Week | Dates | Course work | Artifact due |
|---|---|---|---|
| **S0** | Sep 19–20 | Confirm enrollment · **cold diagnostic** (§2.4) · Ch 1 Computing | Repo created, first commit |
| **1** | Sep 21–27 | Ch 2 Programming · Ch 3 Debugging · Ch 4 Procedural Programming | v0.1 — runs, prints, input→process→output skeleton + debugging log |
| **2** | Sep 28–Oct 4 | Ch 5 Variables · Ch 6 Logical Operators · Ch 7 Mathematical Operators | **v1.0 — computes all metrics with benchmark flags** |
| — | **Sun Oct 4** | **RELEASE GATE 1 — Course I complete. Certificate decision closed.** | |
| **3** | Oct 5–11 | Course II: conditionals | v1.1 — branching logic replaces flat flags |
| **4** | Oct 12–18 | Course II: loops | **v2.0 — handles a list of campaigns, not one** |
| — | **Sun Oct 18** | **RELEASE GATE 2 — multi-campaign tool working** | |
| **5** | Oct 19–25 | Course II: remaining chapters | v2.5 — refactored, edge cases handled |
| **6** | Oct 26–31 | Consolidation. No new course material. | **v3.0 — README, cleanup, published** |
| — | **Sat Oct 31** | **RELEASE GATE 3 — public repository, explainable in an interview** | |

**Weeks 3 through 6 are a recommendation, not a fact about the course.** Course I ends at
Gate 1. I have verified Course I's seven chapters directly; I have not verified Course II's
chapter breakdown beyond its title and subject. Confirm that sequence against the edX
dashboard before committing to weeks 3–6. What is not negotiable is that four weeks of
October remain after Course I ends, and they need a plan before they arrive.

## 2.4 The Sprint 0 diagnostic

Before watching a single video, and with nothing open — no notes, no search, no assistant:

> Write a program that takes the number of emails sent, emails opened, and clicks, and
> prints the open rate and click-through rate as percentages rounded to one decimal.

Ten minutes, timed. Then score honestly:

| Result | Track |
|---|---|
| Wrote it correctly, no reference | **Track A — Compressed.** Videos at 1.5–2×, skip nothing, but do not linger. Course I closes 4 October as planned. |
| Got the structure but fumbled casting, rounding or division | **Track A, with attention.** Same schedule; flag the specific gap and drill it in the coding problems. |
| Could not start | **Track B — Full.** Take the edX pacing seriously. Course I closes 18 October, gates shift two weeks right, artifact target drops to v2.0. |

The diagnostic exists because I cannot verify your current fluency from your notes, and the
whole schedule hangs on it. Ten minutes on Saturday decides six weeks.

## 2.5 Time budget, and the conflict inside it

Your strategy document sets the target allocation. Your calculus program sets a hard
commitment of 55 minutes a day, six days a week. Those two do not currently agree.

| Bucket | Target share | Hours at a 12 hr/week total | Reality today |
|---|---|---|---|
| Analytics Core (Python) | 45% | 5.4 | Starting now |
| Integrated Portfolio | 25% | 3.0 | The artifact |
| Long-Term Math | 15% | 1.8 | **5.5 hrs committed** |
| Lifecycle / Martech | 15% | 1.8 | Maintenance |

**Calculus at 5.5 hours a week is roughly 45% of a realistic learning budget, in the bucket
your own strategy caps at 15%.** For math to actually be 15%, the weekly total would have to
be near 37 hours, which is not available alongside a job search.

Your own guardrail already answers this:

> *Math should be consistent but bounded. It should not consume so much current
> career-development time that it displaces the analytical skills that can be used and
> demonstrated now.*

**Recommendation:** drop calculus to three days a week for the six weeks Python is the
anchor. That is 2.75 hours, about 20%, and it keeps the precalculus streak alive without
starving the thing that is supposed to be in front. Restore six days on 1 November. If that
trade is unacceptable, then Python is not really the anchor, and the honest move is to say
so and set a smaller October target rather than miss a larger one.

## 2.6 Risk register

| ID | Risk | Likelihood | Impact | Response |
|---|---|---|---|---|
| **R1** | The restart pattern repeats — attempt five | **High** | **Critical** | No new plan documents until 31 October. This file is frozen. Changes go in a changelog line at the bottom, never in a new page. A new roadmap page is the failure, not the fix. |
| **R2** | Course is too easy, attention drifts, momentum dies quietly | High | High | Compress ruthlessly on Track A. The artifact, not the video count, is the reason to show up. |
| **R3** | Environment setup consumes the first week | Medium | **Critical** | **Do all of Sprint 0 and Week 1 in the edX in-browser editor.** No local install, no IDE configuration, no virtualenv until Week 2 at the earliest. This is the documented cause of the May failure: "IDE troubleshooting consumed Week 1 velocity." Do not re-run that experiment. |
| **R4** | Calculus, PMP prep and the job search crowd out the anchor | High | High | §2.5. Decide the calculus trade this weekend, before Week 1. |
| **R5** | Certificate question stays open and nags | Medium | Low | Decide at Gate 1, 4 October. Audit is free and the course has no proctored exam; the certificate's value here is motivational, not evidentiary. The artifact is the evidence. |
| **R6** | Artifact slips because course work feels more measurable | High | High | The gates are artifact gates. A week where the chapters are done and the artifact did not move is a missed week. |

## 2.7 Success metrics

| Metric | Target by 31 Oct | Why |
|---|---|---|
| Course I chapters | 7 of 7 | The input, completed |
| Artifact versions shipped | 5 (v0.1 → v3.0) | The output, shipped weekly |
| Public commits | ≥ 20 | Evidence the work was continuous, not crammed |
| New plan documents created | **0** | The single strongest predictor of whether this attempt is different |
| Weeks with a visible artifact change | ≥ 5 of 6 | Your own weekly artifact rule |
| Certificate decision | Closed by Oct 4 | An open loop is a tax on every week after it |

**Watch the fourth row.** Every previous attempt scored well on planning and poorly on
shipping. The count of new planning documents is the leading indicator that matters.

---

# Part 3 — Narrative

## The Fourth Attempt

The honest place to start is not with the course. It is with the three that came before it.

In May there was a fourteen-day Learning Max sprint — charter, stakeholder register, risk
register, burndown chart, a definition of done with checkboxes. It was a genuinely good
plan. It reached L01, Variables and the Memory Model, and stopped. The post-mortem in your
own roadmap is one sentence long and unusually clear-eyed: *IDE troubleshooting consumed
Week 1 velocity.* Not the material. The setup.

In June it was re-baselined. The diagnosis was correct — *the content, sequence, and
methodology are correct; the only thing changing is the timeline* — and the new plan moved
from daily minimums to weekly blocks, which was the right call. Milestone 1 was due 4 July.

By 10 August there was a different curriculum, PY-0 through U8, a 34.5-hour LearnKey
sequence and a proctored Certiport exam. Another architecture, another set of unit pages,
another first day.

Now it is 19 September and there is an edX course from Georgia Tech.

Four attempts in five months. Here is the thing worth sitting with: **not one of them failed
because the material was too hard.** L01 was completed deeply. The Learning Notebook has
written work on falsy values, short-circuit evaluation and loops, applied to suppression
logic and send eligibility — which is Course II material, produced during an attempt that
supposedly stalled. The capability is demonstrably there.

What has never existed is the artifact. Four plans, zero shipped things.

That is the pattern, and it has a mechanism. Planning is the part of this work that feels
like progress while carrying no risk of being wrong. A roadmap cannot throw an error. A
burndown chart cannot fail to run. Each restart has been genuinely better designed than the
last, and each one has been a way of staying in the part of the work where nothing can break
in public. The fifth plan would be the best one yet. That is exactly why it must not get
written.

So the uncomfortable fact about this particular course is that it is too easy for you, and
that is the opportunity rather than the problem. Seven chapters that stop before `if`
statements. Videos two to three minutes long. No exam. You have already done the hardest
chapter of it, deeply, in May. At your actual level this is twelve to eighteen hours of
work, not forty-five, which means it closes in two weeks and leaves four weeks of October
standing empty.

Those four weeks are the whole question. Filled with another curriculum, they become attempt
number five with a Georgia Tech logo on it. Filled with a repository that anyone can open
and run, they become the first time this has ever produced evidence.

Which is why the artifact is small on purpose. Not a portfolio. Not a pipeline. A script
that takes the number of emails you sent, the number opened, the number clicked, and prints
the rates with a flag on whether they beat the benchmark. You could do that arithmetic in
your head. That is not the point. The point is that it runs, it lives somewhere public, it
has a README, and it grows by one layer each week as the course hands you another tool —
variables, then logical operators, then the math. By the end of Course I it is a real thing.
By the end of October, with loops, it handles a whole campaign list instead of one.

And the first defense of all of this is almost insultingly small: **do not install anything.**
Stay in the browser editor for two weeks. The May attempt died on IDE configuration, and the
instinct to set up the environment properly before beginning is the same instinct that
produces the perfect plan instead of the working script. Configure nothing. Open the edX
editor. Write the code there.

There is also a trade to make this weekend and it will not feel good. Calculus currently
takes 55 minutes a day, six days a week — about 45% of a realistic learning budget, sitting
in the bucket your own strategy document caps at 15%. Python cannot be the anchor while
something else occupies the anchor's time. Your own guardrail says math should be bounded so
it does not displace the skills you can demonstrate now. Three days a week through October.
The streak survives. The anchor gets its hours back. On 1 November it goes back to six.

None of this is ambitious, and that is deliberate. Seven chapters you mostly already know,
one small tool, five versions, six weeks, and a rule against writing another plan. The
measure of success on 31 October is not a certificate and not a completion percentage. It is
a URL — something you can send to someone, or open in an interview, and say: I built this,
here is how it works, here is what I would add next.

Four attempts produced four excellent plans. This one has to produce one working thing.

---

## Changelog

Amendments go here as single dated lines. Not in a new document.

- **2026-09-19** — Created. Horizon 19 Sep → 31 Oct 2026.

## Sources

- [GTx: Computing in Python I — edX](https://www.edx.org/learn/python/the-georgia-institute-of-technology-computing-in-python-i-fundamentals-and-procedural-programming)
- [Computing in Python I — Class Central](https://www.classcentral.com/course/python-the-georgia-institute-of-technology-comput-11469)
- [Computing in Python I — OpenCourser](https://opencourser.com/course/h66sl0/computing-in-python-i-fundamentals-and-procedural-programming)
- Notion — Python Learning Roadmap (Re-Baselined), Career Upskilling Strategy, Python Foundations Course Plan, Learning Notebook
