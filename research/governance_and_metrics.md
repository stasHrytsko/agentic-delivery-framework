# Governance, Management and Measurement of AI-Agent-Driven Software Delivery (2025–2026)

> Method note: research date 2026-11-10. WebFetch was blocked by the session network for faros.ai, metr.org, dora.dev and blog.robbowley.net, so most findings below come from search-result snippets and secondary coverage, not full primary documents. Only the Google Cloud DORA announcement blog was read in full. Labels used: [INDEPENDENT] = academic, nonprofit or neutral research; [VENDOR] = a company that sells tools or analytics in this space; [SECONDARY] = a blog or press summary. Data older than 2025 is flagged [OLDER].

## 1. Metrics frameworks and concrete metrics for AI-assisted and agentic engineering

### Takeaway
The main frameworks are DORA 2025 (the four delivery metrics plus a 7-capability "AI Capabilities Model"), DX's AI Measurement Framework (Utilization → Impact → Cost, tied to its Core 4 of DORA+SPACE+DevEx), and analytics-vendor benchmarks (LinearB, Faros). These benchmarks are moving away from activity metrics such as acceptance rate and % AI-written code, and toward flow and outcome metrics: PR acceptance and merge rate of AI or agent PRs, review wait time, PR size, change failure rate and instability, and cost per outcome.

### Cited Findings
**DORA 2025 "State of AI-assisted Software Development" (Google Cloud) [INDEPENDENT-ish: Google-run research program; Google also sells AI tools]**
- The survey ran June 13 to July 21, 2025 and covers nearly 5,000 technology professionals plus more than 100 hours of qualitative data. 90% of respondents use AI at work (up 14% year on year). More than 80% believe AI raised their productivity. 30% report little or no trust in AI-generated code — [Google Cloud blog, Sept 2025](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report); [Report PDF](https://services.google.com/fh/files/misc/2025_state_of_ai_assisted_software_development.pdf)
- In 2024, AI adoption correlated negatively with throughput. In 2025 it correlates positively with software delivery throughput and product performance, but still correlates negatively with delivery stability (instability goes up) — [Google Cloud blog](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report)
- The central thesis is "AI is an amplifier". Teams with loosely coupled architecture, strong automated testing, mature version control and fast feedback loops gain from AI. Teams with tightly coupled systems and slow processes see little benefit — [Google Cloud blog](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report)
- 90% of organizations have adopted at least one internal platform, and platform quality correlates with unlocking AI's value — [Google Cloud blog](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report)
- A cluster analysis produced 7 team archetypes based on performance, stability and well-being. Two are named on the blog: "Foundational challenges" (low performance, high burnout and friction) and "Harmonious high achievers" — [Google Cloud blog](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report)
- **DORA AI Capabilities Model (7 capabilities):** (1) a clear and communicated AI stance (expectations, permitted tools, support for experimentation); (2) a healthy data ecosystem; (3) AI-accessible internal data (DORA calls the shift from "prompt engineering" to "context engineering"); (4) strong version control practices; (5) working in small batches, described as "especially powerful in AI-assisted environments"; (6) user-centric focus (teams with weak user focus that adopt AI see performance *decline*); (7) quality internal platforms — [Google Cloud: Introducing DORA's inaugural AI Capabilities Model](https://cloud.google.com/blog/products/ai-machine-learning/introducing-doras-inaugural-ai-capabilities-model); [Google Research pub](https://research.google/pubs/introducing-the-dora-ai-capabilities-model-7-keys-to-succeeding-in-ai-assisted-software-development/); [capabilities report](https://cloud.google.com/resources/content/2025-dora-ai-capabilities-model-report). The list of 7 was assembled from search summaries; check exact wording at dora.dev/ai/capabilities-model/report.
- A secondary analysis claims "61% never use autonomous agent mode". This could not be confirmed in the primary report and should be treated as unverified — [hyperdev.matsuoka.com (SECONDARY)](https://hyperdev.matsuoka.com/p/dora-2025-ai-as-amplifier-not-magic)

**DX AI Measurement Framework [VENDOR: DX/getdx.com, acquired by Atlassian in 2025 (from memory, not verified in this session)]**
- There are three dimensions. **Utilization**: DAU/WAU of AI tools, % of PRs that are AI-assisted, % of committed code that is AI-generated. **Impact**: AI-driven time savings (hours per developer per week), plus longitudinal comparison against the Core 4 (DORA + SPACE + DevEx) and developer satisfaction. **Cost**: AI spend overall and per developer, net time gained (time saved minus spend), and "AI hourly rate" (human-equivalent hours divided by AI spend) — [DX AI Measurement Framework](https://getdx.com/ai-measurement-framework/); [PDF](https://getdx.com/uploads/ai-measurement-framework.pdf); [DX: measuring AI code assistants and agents](https://getdx.com/research/measuring-ai-code-assistants-and-agents/); [The New Stack](https://thenewstack.io/how-to-measure-the-roi-of-ai-coding-assistants/)
- DX warns against using these metrics in individual performance reviews and against top-down usage mandates. It notes that code-generation volume metrics are especially easy to game — [DX blog](https://getdx.com/blog/how-to-measure-ai-impact-engineering-team/)

**LinearB 2026 Software Engineering Benchmarks [VENDOR]**
- The benchmark covers 8.1M PRs. "Acceptance rate" means the share of PRs merged within 30 days. Manual PRs: 84.4%. AI PRs: 32.7% (more than 2x lower), and the gap holds across every performance tier. Elite threshold: above 95% for manual PRs, and just above 71% for AI PRs — [LinearB 2026 Benchmarks](https://linearb.io/resources/engineering-benchmarks-report); [PDF](https://assets.linearb.io/image/upload/v1764965485/resources/LinearB_2026_Software_Engineering_Benchmarks_Report.pdf); [Dev Interrupted podcast](https://linearb.io/dev-interrupted/podcast/linearb-2026-benchmarks-ai-pr-merge-rate)
- A separate LinearB AI dataset covers 2.7M PRs across 253 organizations. At elite organizations, 79% of agent PRs merge within 30 days versus 92% of human-only PRs. "When no developer owns an agent's PR, it often never merges." Agent-written changes wait more than 5x as long for review. AI-assisted PRs are about 2.6x larger at P75. PRs that get an AI review merge at the highest rate, up to +5 percentage points over baseline — [LinearB AI in software development](https://linearb.io/library/ai-in-software-development); [LinearB AI productivity gap](https://linearb.io/resources/ai-engineering-productivity-gap). These are marketing-page figures; the two datasets should not be mixed.

**Faros AI [VENDOR telemetry]**
- *AI Productivity Paradox Report 2025* (about 10,000 developers; one secondary source says 1,255 teams). On high-AI-adoption teams, developers complete 21% more tasks and merge 98% more PRs, but PR review time rises 91%. At the company level, the gains disappear — [Faros AI 2025](https://www.faros.ai/blog/ai-productivity-paradox-report-2025)
- *AI Engineering Report 2026: "Acceleration Whiplash"* (22,000 developers, more than 4,000 teams, 2 years of telemetry; compares each organization's own low-adoption and high-adoption periods). Median time to first PR review is up 156.6% and median time in review is up 441.5% — [Faros 2026 takeaways](https://www.faros.ai/blog/ai-acceleration-whiplash-takeaways); [report page](https://www.faros.ai/research/ai-acceleration-whiplash). Several secondary sites misattribute the 2025 figures (91%/98%) to the 2026 report.

**Other metric definitions in use**
- Activity and adoption metrics in use: acceptance rate of suggestions, % AI-authored code, DAU/WAU — [DX](https://getdx.com/ai-measurement-framework/). Agent-era metrics: agent PR merge rate, time to merge, revert rate, PR size, review wait — [LinearB](https://linearb.io/library/ai-in-software-development); [TechRepublic on Microsoft study](https://www.techrepublic.com/de/article/news-ai-coding-agents-microsoft-pull-requests/)
- GitClear's code-quality metrics: churn (lines revised or reverted within 2 weeks), duplicated blocks, "moved" (refactored) versus copy/pasted lines — [LeadDev on GitClear](https://leaddev.com/software-quality/how-ai-generated-code-accelerates-technical-debt)
- Proposed flow metrics for agent review queues: review queue size, time to first meaningful review, PR age, batch size, rework after review, and a cumulative flow diagram — [Developer Toolkit: review queue (SECONDARY)](https://developertoolkit.ai/en/teams/review-queue/)

### Inferences
- The industry is converging on a layered measurement model. Adoption metrics (usage, % AI code) are a leading but gameable indicator. Flow metrics (review wait, PR size, merge rate) show where the bottleneck has moved. Outcome metrics (DORA throughput and instability, product performance, cost per outcome) are the real test.
- DORA's "instability up" finding and the vendor telemetry from Faros and LinearB (larger PRs, longer reviews) point the same way: the constraint has moved downstream of code generation.
- Merge or acceptance rate of agent PRs is becoming the de facto "agent success rate" metric in production, alongside benchmark pass rates.

### Gaps
- Could not access the GitHub Copilot metrics API docs to confirm which fields it offers (for example acceptance rate or agent PR counts), or Google's "% of code AI-generated" public statements.
- No Jellyfish 2025/2026 AI impact data was retrieved.
- Could not read the full DORA PDF for the throughput and instability effect sizes, the names of the other 5 archetypes, or any new DORA metric (such as rework rate).

## 2. Evidence on effects: speed, quality, review bottlenecks, burnout, security

### Takeaway
The independent evidence is mixed and depends on context. METR's 2025 RCT found experienced open-source developers were 19% *slower* while believing they were 20% faster. METR's 2026 follow-up could not produce a reliable estimate because of selection bias. Google's enterprise RCT found about 21% faster with wide confidence intervals. Telemetry from vendors consistently shows more PRs at the individual level, but longer reviews, larger PRs, more instability and, by most survey accounts, more review load and burnout. Security studies find insecure output in about 45% of benchmark tasks.

### Cited Findings
**Speed**
- **METR RCT (July 2025) [INDEPENDENT].** 16 experienced OSS developers worked 246 real issues in their own mature repos, using early-2025 tools (Cursor plus Claude 3.5/3.7). Allowing AI *increased* completion time by 19% (CI roughly +2% to +39%). Before the study, developers forecast a 24% speedup; afterward they still believed AI gave a 20% speedup — [ScienceBlog summary](https://scienceblog.com/t-a-randomized-trial-by-metr-found-that-experienced-developers-completed-real-coding-tasks-19-slower-when-allowed-to-use-ai-tools-yet-afterwards-they-estimated-on-average-that-ai-had-made-them-20-fast/); primary: metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study (URL from memory; metr.org was unreachable in this session)
- **METR follow-up (Feb 24, 2026) [INDEPENDENT].** A larger experiment started in August 2025. METR says selection effects were severe enough that its central estimate is a poor proxy, and it is redesigning the study. Developers were reluctant to work on tasks without AI and withheld AI-suitable tasks; one secondary source says 30–50% of tasks were withheld. METR plans developer-level experiments next. Online claims of "18–20% faster" are disputed as misreadings — [METR: uplift update](https://metr.org/blog/2026-02-24-uplift-update/); [Rob Bowley analysis (SECONDARY)](https://blog.robbowley.net/2026/04/04/metrs-developer-productivity-research-2026-update/)
- **METR AI usage survey (May 11, 2026) [INDEPENDENT, self-report].** Median *self-reported* value uplift was about 1.4x–2x for March 2026. METR's own staff reported the lowest uplift of any subgroup — [METR AI usage survey](https://metr.org/blog/2026-05-11-ai-usage-survey/) (via search snippet)
- **Google enterprise RCT (ICSE-SEIP 2025) [INDEPENDENT-ish, Google internal]** [OLDER data, 2024]. 96 Google engineers were randomized to use or not use 3 AI features on an enterprise-grade task. The AI group was about 21% faster, but the CI is large and the effect is not significant in some adjusted models. Senior developers and those who code more hours per day were faster overall — [arXiv 2410.12944](https://arxiv.org/html/2410.12944v2); [ICSE 2025 listing](https://conf.researchr.org/details/icse-2025/icse-2025-software-engineering-in-practice/26/How-much-does-AI-impact-development-speed-An-enterprise-based-randomized-controlled-)
- **Microsoft study of command-line agents (press coverage, July 2026).** About 24% more merged PRs over four months. Merge rates were roughly flat and the revert rate declined. Copilot CLI users saw about 2.2x the PR lift of Claude Code users (press summary only) — [TechRepublic](https://www.techrepublic.com/de/article/news-ai-coding-agents-microsoft-pull-requests/)
- **Faros 2025 [VENDOR].** +21% tasks, +98% merged PRs, +91% PR review time, and no company-level gain — [Faros](https://www.faros.ai/blog/ai-productivity-paradox-report-2025)

**Agent PR success rates (academic, AIDev dataset and similar) [INDEPENDENT]**
- **Claude Code PRs.** 567 PRs across 157 OSS projects (Feb–Apr 2025). Human PRs had a significantly higher acceptance rate than agent PRs. Median time to merge was about 1.2h for agent PRs versus 1.0h for human PRs. Agent PRs "largely acceptable but benefit from human oversight" — [arXiv 2509.14745](https://arxiv.org/abs/2509.14745?context=cs)
- **Failed agentic PRs study (AIDev).** Merge rate by agent: Codex 82.59% (highest), Copilot 43.04% (lowest). By task type: docs 84%, CI 79%, bug-fix 64%, performance 55%. Main failure causes are reviewer abandonment, duplicate PRs and CI failures — [Moonlight review of "Where Do AI Coding Agents Fail?"](https://www.themoonlight.io/review/where-do-ai-coding-agents-fail-an-empirical-study-of-failed-agentic-pull-requests-in-github). Note: cross-agent comparisons are confounded by task mix and by how each agent opens PRs.
- Related papers: [arXiv 2601.18749](https://www.arxiv.org/pdf/2601.18749) (developer vs agentic PRs); [arXiv 2602.19441](https://arxiv.org/html/2602.19441v1)

**Quality and churn**
- **GitClear "AI Copilot Code Quality" (Feb 2025) [VENDOR; data 2020–2024, partly OLDER].** Analysis of 211M changed lines. In 2024, duplicated blocks of 5 or more lines rose 8x. Copy/pasted lines exceeded moved (refactored) lines for the first time. Refactoring ("moved") fell from about 24% (2021) to under 10%. Copy/paste rose from under 10% to about 15%. One summary reports churn rising from 3.3% (2021) to 5.7% (2024). The study is correlational and does not attribute specific lines to AI — [LeadDev](https://leaddev.com/software-quality/how-ai-generated-code-accelerates-technical-debt); [DevClass](https://www.devclass.com/ai-ml/2025/02/20/ai-is-eroding-code-quality-states-new-in-depth-report/1626250); [TechCrunch](https://techcrunch.com/2025/02/21/report-ai-coding-assistants-arent-a-panacea)
- For contrast, DORA 2024 [OLDER] reported that more AI adoption was associated with about a 3.4% gain in code quality — as cited in [The New Stack](https://thenewstack.io/whats-missing-with-ai-generated-code-refactoring)
- **SmartBear survey (Mar 2026) [VENDOR].** 70% say application quality has already degraded as AI accelerated development — via [search summary of letsdatascience/others (SECONDARY)](https://letsdatascience.com/news/ai-agents-transform-software-engineers-into-managers-d439df51) (unverified)

**Trust (Stack Overflow Developer Survey 2025, July 2025) [INDEPENDENT-ish community survey]**
- 84% use or plan to use AI tools. 46% distrust the accuracy of AI output (up from 31%). Only about 3% "highly trust" it. 66% name "almost right, but not quite" as their top frustration. 45% say debugging AI code takes longer. 31% use AI agents, 17% plan to, and 38% have no plans. 87% are concerned about agent accuracy — [TechRepublic](https://www.techrepublic.com/article/news-developer-trust-in-ai-declines/); [ShiftMag](https://shiftmag.dev/stack-overflow-survey-2025-ai-5653/); [ADTmag](https://adtmag.com/Blogs/WatersWorks/2026/01/Stack-Overflow-Survey.aspx)

**Review bottleneck, burnout and "AI fatigue"**
- **Harness (2026) [VENDOR surveys].** About 31% of developer time goes to "invisible" AI work such as reviewing, fixing and supervising AI output. About 81% spend more time in code review than before AI. Among heavy AI users (multiple times per day), 96% do evening or weekend release work multiple times a month, versus 66% of occasional users. Contradicting this, Harness also cites 84% agreeing that AI reduced their feeling of burnout. Sample sizes are inconsistent across sources (700 vs about 3,000) — [ITPro on 81% review](https://www.itpro.com/software/development/ai-might-help-speed-up-software-development-but-81-percent-of-devs-now-spend-more-time-reviewing-code-and-its-creating-an-invisible-work-trend-thats-pushing-teams-to-the-limit); [SD Times](https://sdtimes.com/softwaredev/the-invisible-burden-how-ai-is-redefining-developer-productivity-in-2026/); [Harness State of DevOps Modernization 2026](https://www.harness.io/state-of-devops-modernization-2026); [Harness burnout blog](https://www.harness.io/blog/burnout-is-rising-heres-what-you-can-fix)
- **Stack Overflow 2026 survey** (30,903 respondents). 45.1% say they are "complacent" in their roles, and burnout or fatigue is the top cause (21.1%) — [Entrepreneur](https://www.entrepreneur.com/business-news/survey-of-30903-professionals-shows-they-are-adopting-ai-despite-the-drawbacks)
- **State of Devs 2026** (5,463 respondents). Views on AI are polarized: 49% positive, 42% negative, and many cite AI fatigue — via search summary [zeli.app (SECONDARY)](https://zeli.app/story/49985643)
- DORA 2025 ties burnout and friction to the "foundational challenges" archetype — [Google Cloud blog](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report)

**Security**
- **Veracode 2025 GenAI Code Security Report (July 30, 2025) [VENDOR].** 80 tasks were run through more than 100 LLMs. About 45% of outputs introduced OWASP Top 10 or CWE vulnerabilities. Java failed in over 70% of cases; Python, C# and JS fell between 38% and 45%. XSS defenses failed 86% of the time and log injection 88%. The CTO said security performance is "not improving" with newer or larger models — [Veracode press release](https://www.veracode.com/press-release/ai-generated-code-poses-major-security-risks-in-nearly-half-of-all-development-tasks-veracode-research-reveals/); [Help Net Security](https://www.helpnetsecurity.com/2025/08/07/create-ai-code-security-risks/)

### Inferences
- The best-supported finding is a perception gap: developers overestimate speedups (METR). Self-reports and vendor surveys therefore need to be paired with telemetry or experiments.
- Individual-level output gains (more PRs) are real in telemetry. Organization-level delivery gains are not reliably observed (Faros 2025, DORA's instability finding). This is consistent with a downstream constraint in review, testing and integration.
- Measurement itself is getting harder. METR's redesign shows that controlled trials break down once developers will not work without AI.

### Gaps
- There is no independent large-scale study linking agent-authored code to production incident rates or change failure rate.
- The "AI brain fry" HBR study (2026) appeared only secondhand and was not verified.
- Veracode's 2026 update, if one exists, was not found.

## 3. How roles, team topology and ceremonies are changing

### Takeaway
Most sources describe engineers shifting from writing code to specifying, orchestrating and reviewing agent output, and engineer and manager roles converging. The evidence is mostly practitioner commentary and vendor framing; only a few surveys exist. Platform teams become owners of agent infrastructure, context and guardrails, which DORA endorses indirectly. Proposals to adapt ceremonies focus on retros: agent-trace reviews and AGENTS.md updates as action items. None are empirically validated.

### Cited Findings
- **Pragmatic Engineer 2026 survey** (more than 900 engineers and leaders; secondhand). Engineers orchestrate more and context-switch more, managers can be more hands-on, and "the engineer and manager roles are becoming similar" — [Nick Talwar Substack (SECONDARY)](https://nicktalwar.substack.com/p/when-engineers-manage-agents-and)
- **LeadDev (May 2026).** Demand for engineering-management *skills* is surging in the agentic era. Roles and career ladders are being "flipped and collapsed". Staff and principal engineers at top companies out-earn EMs by 15–25% (per HR Oasis) — [LeadDev](https://leaddev.com/career-development/demand-for-engineering-managers-is-surging-in-the-agentic-coding-era)
- **LinearB.** Agent PRs without a human owner often never merge, which implies explicit human ownership of agent output is needed — [LinearB](https://linearb.io/library/ai-in-software-development)
- Skill shift toward writing precise behavioral specs, designing eval datasets, and debugging agent behavior; "from prompt engineering to orchestration" — [LinearB blog on agentic roles](https://linearb.io/blog/the-impact-of-agentic-ai-on-software-engineering-roles[7]); [CIO.com](https://www.cio.com/article/4134741/how-agentic-ai-will-reshape-engineering-workflows-in-2026.html)
- "AI Agent Manager" role reportedly defined by HBR (Feb 2026); not verified — [letsdatascience (SECONDARY)](https://letsdatascience.com/news/ai-agents-transform-software-engineers-into-managers-d439df51)
- **Platform teams.** DORA 2025 finds 90% of organizations run internal platforms and lists "quality internal platforms" and "AI-accessible internal data" among its 7 AI capabilities, which positions platform teams as owners of context, tooling and guardrails for agents — [DORA AI Capabilities Model](https://cloud.google.com/blog/products/ai-machine-learning/introducing-doras-inaugural-ai-capabilities-model)
- **Ceremonies.** Proposals include: keep sprint length but run several generate-review-feedback loops inside it; story points fail for agent work; standups add questions about agent behavior ("would a better AGENTS.md have prevented this?"); the "trace retro" is the key remaining human ceremony; AGENTS.md updates become retro action items; and outcome cycles replace sprints. All of these are practitioner blogs — [Adapting Agile Ceremonies for AI Coding Agents (Apr 2026)](https://codex.danielvaughan.com/2026/04/12/adapting-agile-ceremonies-ai-coding-agents/); [agentpatterns.ai: agentic agile rituals](https://agentpatterns.ai/workflows/agentic-agile-rituals/); [Scrum.org: sprint planning when half your team are AI agents](https://www.scrum.org/resources/blog/how-do-sprint-planning-when-half-your-team-are-ai-agents)
- **Microsoft Code-With Engineering Playbook.** Use AI to draft plans and acceptance criteria, "but always validate and adapt output collaboratively with the team" — [Microsoft playbook](https://microsoft.github.io/code-with-engineering-playbook/agile-development/ceremonies/)
- Some teams drop sprints for Kanban-like "Agentic Flow" — [ai killed scrum (SECONDARY)](https://defragzone.substack.com/p/ai-killed-scrum)

### Inferences
- The recurring emerging roles are an engineer as spec-writer, orchestrator and reviewer who owns each agent PR; a platform or "AI enablement" team that owns agent runtime, context (AGENTS.md, MCP), guardrails and cost; and managers who are more hands-on. A formal "AI engineering manager" title is not well documented in primary sources.
- Ceremonies are shifting from status synchronization, which CI and dashboards now handle, to *context and guardrail improvement*: the retro becomes the place where agent instructions, tests and policies are updated.

### Gaps
- There is no rigorous evidence on PMs writing specs for agents, or on changes in team size or topology.
- The Pragmatic Engineer original was not accessed.
- There are no Gartner, Forrester or McKinsey primary figures; the "Bain 90% agent-assisted" claim surfaced but was not verified.

## 4. Governance and guardrails (HITL, permissions, sandboxing, audit, cost, standards, OWASP)

### Takeaway
In practice, governance means least-privilege agent identities, sandboxed execution with egress firewalls, mandatory human approval at merge and deploy, gating by blast radius and reversibility, unified audit trails, and spend caps at a gateway or orchestration layer. GitHub's Copilot coding agent is the clearest documented reference implementation. The OWASP Agentic Top 10 (Dec 2025) and NIST's 2026 agent identity work are the new standards anchors. The EU AI Act's GPAI obligations bind model *providers*, not teams using coding tools.

### Cited Findings
**Reference implementation: GitHub Copilot coding (cloud) agent [VENDOR docs]**
- The agent can only push to `copilot/*` branches (or the existing PR branch) and is subject to branch protections and required checks. The developer who asked Copilot to open a PR cannot approve it. When Copilot opens a PR under its own app identity, one extra approval is required, enabled by default in rulesets. Actions workflows on Copilot PRs require approval from a user with write access before they run. An outbound egress firewall is on by default with an allowlist; GitHub itself notes the firewall has coverage limitations — [GitHub Docs: risks and mitigations](https://docs.github.com/en/copilot/concepts/agents/cloud-agent/risks-and-mitigations); [Customize the agent firewall](https://docs.github.com/en/copilot/how-tos/use-copilot-agents/coding-agent/customize-the-agent-firewall); [GitHub blog: agentic security principles](https://github.blog/security/how-githubs-agentic-security-principles-make-our-ai-agents-as-secure-as-possible/)

**General control patterns (mostly vendor and practitioner guidance)**
- Agents generate output but do not decide what ships; human approval gates sit on existing RBAC — [GitLab blog, July 31, 2026](https://about.gitlab.com/blog/govern-agentic-ai-mcps-code-assistants/)
- Gate by blast radius combined with reversibility, not by action type. Reversible in-scope commands run freely and are logged; a small set of high-consequence actions needs explicit approval every time — [CoderabbIt guide](https://www.coderabbit.ai/guides/ai-governance-coding-agents); [TechRadar](https://techradar.com/pro/why-ai-coding-agents-keep-stalling-before-production-and-the-governance-controls-that-fix-it)
- "The sandbox is the new enterprise perimeter": bring vibe coding into a sandbox IT can see rather than banning it — [Zeabur](https://zeabur.com/blogs/vibe-coding-shadow-it-governance.md)
- Audit: link agent identity, approval events and rollback references in one trail. Review records and admin audit logs need separate access and retention checks. A repository instruction file must not silently grant exceptions to credential or deploy restrictions — [CoderabbIt guide](https://www.coderabbit.ai/guides/ai-governance-coding-agents)
- Cost: gateways enforce virtual keys, budgets, rate limits, MCP tool filtering and request logs per coding-agent request. A cost ceiling is enforced at the orchestration layer — [Maxim/Bifrost (VENDOR)](https://www.getmaxim.ai/articles/how-to-govern-ai-coding-agents-at-scale.md)
- Agent governance is increasingly framed as a non-human-identity problem — [NHIMG/Knostic, Dec 2, 2025](https://nhimg.org/articles/ai-coding-agent-governance-is-becoming-an-identity-problem/)
- Only about 20% of companies have a mature governance model for autonomous agents (attributed to Deloitte; secondhand, unverified) — via [search summary](https://www.techradar.com/pro/why-ai-coding-agents-keep-stalling-before-production-and-the-governance-controls-that-fix-it)

**OWASP Top 10 for Agentic Applications 2026 (published Dec 9, 2025; OWASP GenAI Security Project, more than 100 experts) [INDEPENDENT]**
- ASI01 Agent Goal Hijack; ASI02 Tool Misuse (least-agency tool scoping); ASI03 Identity and Privilege Abuse; ASI04 Agentic Supply Chain Vulnerabilities (models, tools, plugins and MCP servers pulled in at runtime); ASI05 Unexpected Code Execution (sandboxing, deny-by-default egress); ASI06 Memory and Context Poisoning; ASI07 Insecure Inter-Agent Communication (mutual authentication, signed messages); ASI08 Cascading Failures (blast-radius isolation, **circuit breakers**); ASI09 Human-Agent Trust Exploitation (forced confirmation for sensitive actions); ASI10 Rogue Agents — [TechRepublic](https://www.techrepublic.com/article/news-owasp-ai-agent-risk-list/); [Giskard, Dec 18, 2025](https://www.giskard.ai/knowledge/owasp-top-10-for-agentic-application-2026); [Speakeasy](https://www.speakeasy.com/blog/owasp-agentic-top-10-explained); [Cycode](https://cycode.com/blog/owasp-top-10-agentic-applications/). Category names come from secondary write-ups; confirm against genai.owasp.org.

**NIST**
- NCCoE draft concept paper, "Accelerating the Adoption of Software and AI Agent Identity and Authorization" (Feb 5, 2026; comments due Apr 2, 2026), proposes a demo project for agent identity and authorization in enterprises — [NIST news](https://www.nist.gov/news-events/news/2026/02/new-concept-paper-identity-and-authority-software-agents); [PDF](https://www.nccoe.nist.gov/sites/default/files/2026-02/accelerating-the-adoption-of-software-and-ai-agent-identity-and-authorization-concept-paper.pdf); [CSRC](https://csrc.nist.gov/pubs/other/2026/02/05/accelerating-the-adoption-of-software-and-ai-agent/ipd)
- NIST CAISI launched an "AI Agent Standards Initiative" (Feb 2026) on agent security, identity and authorization, separate from the AI RMF. A program built only on the AI RMF does not cover agent identity — [WorkOS explainer (SECONDARY)](https://workos.com/blog/nist-ai-agent-standards-initiative-explained); [CSA](https://labs.cloudsecurityalliance.org/research/governance-nist-ai-agent-standards-agentic-governance-v1-csa/)

**EU AI Act**
- GPAI-model provider obligations (transparency, copyright) apply from Aug 2, 2025. Models already on the market have until Aug 2, 2027. Commission enforcement and fines (up to €15M or 3% of turnover) apply from Aug 2, 2026. The voluntary GPAI Code of Practice can be used to demonstrate compliance. Obligations attach to *models and providers*; a coding assistant is in scope only through its underlying GPAI model and its provider — [European Commission](https://digital-strategy.ec.europa.eu/en/news/eu-rules-general-purpose-ai-models-start-apply-bringing-more-transparency-safety-and-accountability); [Baker McKenzie](https://bakermckenzie.com/en/insight/publications/2025/08/general-purpose-ai-obligations); [Mayer Brown](https://www.mayerbrown.com/en/insights/publications/2025/08/eu-ai-act-news-rules-on-general-purpose-ai-start-applying-guidelines-and-template-for-summary-of-training-data-finalized)
- Audit-trail retention timing related to the AI Act ("your audit trail expires in August") is discussed in [VirtusLab (SECONDARY)](https://virtuslab.com/blog/ai/shadow-ai-is-already-in-your-codebase/)

### Inferences
- A practical control stack for agentic SDLC, assembled from these sources:
  1. Each agent gets its own non-human identity with least privilege (OWASP ASI03, NIST NCCoE).
  2. Execution runs in an ephemeral sandbox with deny-by-default egress (ASI05, Copilot firewall).
  3. Agents write only to dedicated branches, with protected-branch rules and two-person approval (Copilot).
  4. CI on agent PRs needs human approval before it runs.
  5. Actions are gated by risk tier (blast radius × reversibility).
  6. Audit trails link agent identity, prompt and context, approval and rollback.
  7. Budgets and rate limits are enforced at a gateway.
  8. Circuit breakers and kill switches cover cascading failures (ASI08).
- For a user organization (not a model provider), the EU AI Act is mostly indirect for dev tooling. ISO/IEC 42001 and the NIST AI RMF serve as management-system wrappers, and the OWASP and NIST agent-identity work supplies the technical controls.

### Gaps
- Nothing retrieved on ISO/IEC 42001 certification as applied to engineering organizations, or on NIST AI 600-1 (GenAI profile) mappings to SDLC controls.
- No sources found on explicit "kill switch" products for coding agents, beyond OWASP circuit breakers.
- No dedicated policy-as-code tooling for agents (for example OPA rules on agent actions) was found in 2026 sources.
- Anthropic, OpenAI and Cursor enterprise admin controls were not researched in detail.

## 5. Lean concepts applied to agents (WIP limits, Andon / stop-the-line, flow metrics)

### Takeaway
Yes, but mostly in practitioner writing. Theory of Constraints framing (review is the constraint), WIP caps on unreviewed agent PRs, CI-enforced "stop dispatching agents" gates, small batches (which DORA explicitly endorses) and cumulative flow diagrams are all proposed. OWASP's circuit breakers resemble Andon for multi-agent systems. No rigorous studies of these practices were found.

### Cited Findings
- AI makes generation capacity elastic while review capacity stays roughly fixed, so review is often the constraint. Verify the constraint before acting; the constraint is what limits end-to-end throughput, not the busiest stage — [Scrum.org: AI coding made code review the bottleneck](https://www.scrum.org/resources/blog/ai-coding-made-code-review-bottleneck-now-what); [Larridin](https://larridin.com/blog/improve-change-lead-time-ai-code)
- WIP limits: a developer carrying several unreviewed PRs holds context for all of them. Start with loose limits and tighten them, since each tightening surfaces the next bottleneck. When review is the constraint, review before pulling new work — [Uplevel: WIP limits](https://uplevelteam.com/blog/wip-limits); [DEV: review bottleneck](https://dev.to/code-board/the-review-bottleneck-why-faster-code-generation-broke-your-pr-process-31gi)
- **Stop-the-line mechanism:** a CI script counts open, unapproved, non-draft PRs and *blocks agent dispatch* when the count hits a cap derived from review throughput. Track queue size, time to first meaningful review, PR age, batch size and rework, and use a cumulative flow diagram to see whether the review band is widening — [Developer Toolkit: running the review queue when agents open PRs](https://developertoolkit.ai/en/teams/review-queue/)
- **Small batches:** DORA lists "working in small batches" as an AI capability, "especially powerful in AI-assisted environments" — [DORA AI Capabilities Model](https://cloud.google.com/blog/products/ai-machine-learning/introducing-doras-inaugural-ai-capabilities-model). LinearB finds AI PRs about 2.6x larger at P75, which works against small batches — [LinearB](https://linearb.io/library/ai-in-software-development)
- Andon-like controls: OWASP ASI08 recommends circuit breakers and blast-radius isolation for cascading agent failures — [Speakeasy](https://www.speakeasy.com/blog/owasp-agentic-top-10-explained)
- Kanban-style "Agentic Flow" replacing sprints is reported anecdotally — [defragzone (SECONDARY)](https://defragzone.substack.com/p/ai-killed-scrum)

### Inferences
- The data from vendors (Faros review-time increases, LinearB's 5x review wait and larger PRs) and DORA's instability finding together make a strong case for Lean flow controls on review queues: WIP caps, small-batch limits on agent PR size, and an automated "stop dispatching" Andon.
- Agent-side analogues of jidoka are emerging: an agent halts on failing CI or tests, and circuit breakers stop it. These are technically available but not yet measured.

### Gaps
- No empirical study measuring the effect of WIP limits or stop-the-line on agent-heavy teams.
- No formal Lean or value-stream-management framework published specifically for agentic delivery (for example by the Lean Enterprise Institute or Flow Framework authors) was found.
