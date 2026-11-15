# AWS AI-DLC (AI-Driven Development Life Cycle): reading notes

Method note: read from primary sources in the official repository `awslabs/aidlc-workflows` (release 2.11.4, November 2026): the user guide in `docs/guide/`, the principles file `core/knowledge/aidlc-shared/ai-dlc-principles.md`, and the 6-page specification `assets/AI-DLC-Workflows-2.0-Specification.pdf` (Raja SP, AWS, July 2026). The original AWS blog post (2025) could not be opened from this session; the repository says the implementation "originated from the AWS AI-DLC methodology". Read on 2026-11-14.

Sources: [GitHub: awslabs/aidlc-workflows](https://github.com/awslabs/aidlc-workflows) · [AWS DevOps blog: AI-Driven Development Life Cycle](https://aws.amazon.com/blogs/devops/ai-driven-development-life-cycle)

## What it is

A methodology plus a working engine that runs inside coding harnesses (Claude Code, Kiro, Codex CLI, Cursor, opencode, GitHub Copilot). Version 2: 5 phases, 33 stages, 14 agents (11 domain personas, 2 reviewers, 1 composer), 11 workflow profiles ("scopes"), 3 depth levels, an append-only audit trail with 134 event types.

## Phases

| Phase | Purpose (repo wording) | Notable stages and artifacts |
|---|---|---|
| Initialization | Bootstrap workspace, state, audit | Runs automatically, no approval gate |
| Ideation | "Validate the initiative" | Intent capture, market research, feasibility (RAID log), scope, team formation, rough mockups, approval and handoff (initiative brief, decision log) |
| Inception | "Elaborate the requirements" | Reverse engineering (brownfield), practices discovery, requirements, user stories, mockups, domain design (`decisions.md` = ADRs), units generation (`unit-of-work.md`, dependency DAG), contract design, delivery planning (`bolt-plan.md`) |
| Construction | "Build the solution … in reviewable slices" | Per unit: functional design, NFR requirements, NFR design, infrastructure design, code generation. Once at the end: build and test, CI pipeline |
| Operation | "Deploy and operate" | Deployment pipeline (incl. rollback runbook), environments, deployment execution, observability (SLO config), incident response, performance validation, feedback and optimization → loop back to Ideation |

## Gates

- Human approval gate after every stage from Ideation on ("Approve" / "Request Changes").
- Phase boundary verification (automated): required artifacts exist, traceability links intact ("every requirement maps to a story"), no orphaned artifacts, artifacts consistent.
- Construction: the user may let routine checkpoints continue automatically, but "Failures always stop Construction, even in autonomous mode"; plan approval and the choice of verification command remain human decisions.
- Walking skeleton: the first unit is "the smallest working integrated slice"; it must pass a human-authorized end-to-end verification command and be approved before later units start.
- "3-strike escape hatch": after three rounds of requested changes on a stage the gate offers "Accept as-is".

## Adaptive depth

Same lifecycle, different ceremony. Profiles select stages: `poc` 8 of 33, `bugfix` 9, `refactor` 10, `security-patch` 10, `express` 10, `infra` 15, `classic` 18, `mvp` 23, `feature` and `enterprise` 33. Depth (minimal / standard / comprehensive) sets artifact detail. Axis = type of work.

## Principles (specification v2, Raja SP)

1. Human judgement insights can be distilled into machines.
2. Every intent starts ambiguous: "AI must therefore ask clarifying questions without making assumptions".
3. AI as a self-correcting solver with a safety net: post-conditions "must be checkable by a program the AI cannot modify"; every loop has a halting condition (iterations or token budget), then escalation to a human.
4. Three-compartment model per stage: the "What" (inputs and outputs), "How do we know it's right" (post-conditions), "What did we learn" (learning capture).
5. Every SDLC stage fits this construct.
6. Staged decomposition over single-shot compression.
7. Autonomy in safe increments, not big-bang: start with codified rules, hydrate more over time.
8. Extensibility.
9. Learning from practice: a human correction becomes a candidate rule; "The proposal is shown to the human for approval before being promoted".

Verification: inferential (LLM) rules for nuanced checks; computational (executable) checks for zero-tolerance rules. "A stage whose Compartment 2 contains only LLM-judged post-conditions will not self-halt" — it goes to a human.

The shorter principles file in the repo lists: user decides, AI executes; adaptive depth; traceable artifacts; multi-role expertise; no emergent behavior; questions before assumptions; contradiction detection.

## Where it differs from this framework

- Stated direction of v2: "march progressively towards autonomous software delivery — reducing human intervention". This framework keeps the decision on the result with a human; automation may take over more checks.
- The orchestrator has "Goal Ownership" and is "accountable for delivering the declared outcome". Here accountability is always human.
- Agents carry role names (product, architect, developer…). Here roles are people; agents assist them.
- "Accept as-is" after three revisions. Here a stuck task is re-sliced or finished by a human (Andon).

## What this framework takes

Mechanics, not the autonomy philosophy: phase-boundary traceability checks, walking skeleton, operation and maintenance as a full phase with a loop back to intake, two axes of strictness (type of work × risk class), halting condition → human (Andon), human-approved learning loop.
