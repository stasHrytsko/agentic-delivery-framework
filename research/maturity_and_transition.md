# Maturity models and transition roadmaps: from Agile/Scrum/DevOps to AI-agent-based delivery (2024–2026)

> **How these notes were gathered.** The session's network allowlist blocked every WebFetch call: dora.dev, sourcegraph.com, newsletter.pragmaticengineer.com and swarmia.com all failed DNS. Every finding below therefore comes from WebSearch result summaries, not from reading the full source pages. Figures and wording should be checked against the primary pages before they are quoted verbatim. Dates are the publication dates reported in the search results. Today is 2026-11-10.

## 1. What maturity models exist?

### Takeaway
No standard maturity model exists. There are four families:
- **Autonomy-level ladders** modelled on SAE driving levels (Sourcegraph, BlueOptima, Stride, an arXiv roadmap, Berkeley RDI).
- **Individual-developer stage ladders** (Yegge's 8 levels, Jan 2026).
- **Usage-telemetry cohorts** (GitHub Copilot Phases 0–3; the DX utilization/impact/cost framework).
- **Organizational capability and operating-model models.** These say capabilities matter more than levels: DORA's 7 AI capabilities plus 7 team archetypes; McKinsey's "AI-native / agentic organization"; AWS AI-DLC; analyst and consultancy 4–5-stage indices.

The models disagree on how many levels there are and where "autonomy" begins. The organizational models also reject the idea that tool sophistication equals maturity.

### Cited Findings

**A. Autonomy-level ladders (SAE analogy)**
- **Sourcegraph, "levels of code AI".** Six levels, from manual coding to AI-led development. The levels are sequential: reaching level N requires level N-1. Level 3, "supervised automation", is where the AI performs several steps toward a human's higher-level intent and the human does not review each step. — [Sourcegraph blog](https://sourcegraph.com/blog/levels-of-code-ai); related talk [AI Engineer Summit 2023, "Code AI maturity model"](https://www.ai.engineer/talks/jpKCIVlS9wM-code-ai-maturity-model-what-it-means). **Flag:** the Sourcegraph material is from 2023–2024, older than the target window.
- **BlueOptima Coding Automation Framework (2024).** Six levels mapped one-to-one onto SAE. Level 3 is conditional automation; Level 5, full automation with AI handling coding, testing and deployment without humans, is called "currently aspirational". — [BlueOptima](https://www.blueoptima.com/post/unpacking-the-coding-automation-framework-a-new-reference-for-development-leaders). **Flag:** 2024.
- **Stride, "6 Levels of CodeGen Automation".** At Level 3 "you are no longer coding": the paradigm shifts from assistance to autonomy. — [Stride](https://www.stride.build/thought-leadership/the-6-levels-of-codegen-automation)
- **"Agentic Software Engineering: Foundational Pillars and a Research Roadmap" (arXiv 2509.06216, Sept 2025).** Pairs its levels with SAE: L1 driver assistance (autocomplete); L2 partial automation, where the human supervises constantly and remains responsible. — [arXiv](https://arxiv.org/pdf/2509.06216)
- **Berkeley RDI position paper.** Proposes only three levels, defined by which SDLC stages have moved from human responsibility to full AI control. — [Berkeley RDI](https://rdi.berkeley.edu/blog/auto-software-dev)
- **Where the ladders conflict.** Sourcegraph and BlueOptima put the key boundary at the shift from per-step human review to unreviewed multi-step work (L3). Other frameworks put it at L2 or L3, and Berkeley uses SDLC-stage handover rather than task autonomy. — synthesis of the search summary of the sources above ([Sourcegraph](https://sourcegraph.com/blog/levels-of-code-ai), [BlueOptima](https://blueoptima.com/unpacking-the-coding-automation-framework-a-new-reference-for-development-leaders/), [Berkeley RDI](https://rdi.berkeley.edu/blog/auto-software-dev))

**B. Individual-developer stage ladder: Steve Yegge's 8 levels (Jan 2026)**
- **Source.** Introduced in "Welcome to Gas Town" (New Year 2026). — [Yegge, Medium](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04); mirror [yegge.ai](https://yegge.ai/essays/welcome-to-gas-town/)
- **Structure.**
  - Stages 1–4 are increasingly sophisticated IDE use, starting from Stage 1 (near-zero AI or autocomplete).
  - Stages 5–8 are coding agents. At Stage 5 "your IDE goes away".
  - Stage 7 is 10+ agents managed by hand.
  - Stage 8 is building or using your own agent orchestrator.

  — [Pragmatic Engineer, "From IDEs to AI agents with Steve Yegge" (2026)](https://newsletter.pragmaticengineer.com/i/187563524/3-eight-levels-of-ai-adoption); [Augment Code summary](https://www.augmentcode.com/guides/steve-yegge-8-levels-ai-assisted-development); [torqsoftware reading notes, 2026-01-15](https://reading.torqsoftware.com/notes/software/ai-ml/agentic-coding/2026-01-15-gas-town-multi-agent-orchestration-framework/)
- **Gas Town.** An open-source orchestrator for running 20–30 Claude Code instances at once ("Kubernetes and Temporal had an ugly baby"). Yegge says it is "not for anyone below Stage 7, or maybe Stage 6 and very brave".
  - Hierarchy: town-level coordination roles (Mayor, Witness, Dogs, Crew) and rig-level (per-repo) execution.
  - Units: each managed git repo is a "Rig"; "Beads" are the atomic unit of work.
  - A successor essay, "Welcome to Gas City", followed.

  — [Yegge](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04); [Yegge, Gas City](https://yegge.ai/essays/welcome-to-gas-city/); [Software Engineering Daily, 2026-02-12](https://softwareengineeringdaily.com/2026/02/12/gas-town-beads-and-the-rise-of-agentic-development-with-steve-yegge/)
- **Critique.** Maggie Appleton places herself around stages 4–6 and calls Gas Town poorly designed, with design itself becoming the bottleneck in "vibecoding at scale". — [maggieappleton.com](https://maggieappleton.com/gastown)
- **Team-level reframing.** Platform.sh reportedly reworked Yegge's individual ladder into an 8-stage team model running "from ad hoc use to an autonomous factory" (June 2026). — reported in a search summary that also surfaced [pulse.bot, "8 Stages of AI Engineering Maturity"](https://www.pulse.bot/ai/news/the-8-stages-of-ai-engineering-maturity-a-framework-for-teams-48c68d73-3fed-476e-9720-a07ed6188c05/); not verified against the primary source.

**C. Usage-telemetry cohorts (vendor and measurement)**
- **GitHub Copilot impact dashboard.** Puts each developer in an adoption cohort based on the last 28 days of use:
  - Phase 0: meets no engagement criteria.
  - Phase 1: code completion and/or IDE agent mode.
  - Phase 2: one GitHub-hosted agent surface (cloud coding agent, code review or CLI).
  - Phase 3: two or more agent surfaces, or the Copilot app.

  GitHub's ROI figures are directional, not causal. — [GitHub resources, "Measure AI adoption with GitHub Copilot metrics"](https://github.com/resources/insights/copilot-impact-dashboard) (2026-era material)
- **GitHub "agentic engineering" workflow.** Plan → Build → Verify → Observe, with developers keeping responsibility for decisions and outcomes. It is vendor-authored. — [WindowsForum summary](https://windowsforum.com/news/github-copilot-agentic-engineering-plan-build-verify-and-review-bottlenecks.451288/)
- **DX AI Measurement Framework (≈ July 2025).** Three pillars: Utilization, Impact and Cost.
  - Utilization is measured as DAU/WAU as a share of all developers.
  - Acceptance rate and lines of code are deliberately excluded as primary measures.

  It is a measurement framework, not a stage model; I found no DX-published "adoption stages" model. — [DX podcast](https://getdx.com/podcast/measuring-ai-code-assistants-ai-framework/); [rywalker.com on DX](https://rywalker.com/research/dx)
- **DX Q4 2025 AI-assisted engineering impact report** (400+ orgs, data from July–Oct 2025):
  - More than 90% of developers use AI at least monthly.
  - The share of AI-authored code is lower than headline claims.
  - Juniors use AI more, but seniors capture more measurable time savings.

  — [Laura Tacho, DX newsletter](https://newsletter.getdx.com/p/ai-assisted-engineering-q4-impact-report); critique of its transparency in [Rob Bowley, 2025-11-05](https://blog.robbowley.net/2025/11/05/findings-from-dxs-2025-report-ai-wont-save-you-from-your-engineering-culture/)

**D. Organizational capability and operating-model models**
- **DORA 2025 (State of AI-assisted Software Development plus the AI Capabilities Model).**
  - About 90% of respondents use AI at work.
  - Core thesis: AI is an *amplifier*. It magnifies existing strengths and dysfunctions.
  - Instead of maturity levels, a cluster analysis gives **seven team archetypes**, each with its own mix of performance, stability and well-being. Names reported in secondary sources include "Harmonious High-Achiever", "Legacy Bottleneck" and "Foundational Challenges".

  — [Google Cloud, announcing the 2025 DORA report](https://cloud.google.com/blog/products/ai-machine-learning/announcing-the-2025-dora-report?e=48754805); [report PDF](https://services.google.com/fh/files/misc/2025_state_of_ai_assisted_software_development.pdf); [agility-at-scale on archetypes](https://agility-at-scale.com/safe/ai-enabled-safe/dora-2025-for-ai-teams-seven-archetypes-every-safe-rte-should-know/)
- **DORA AI Capabilities Model: seven capabilities** said to amplify AI's benefit:
  1. Clear and communicated AI stance/policy
  2. Healthy data ecosystem
  3. AI-accessible internal data
  4. Strong version control practices
  5. Working in small batches
  6. User-centric focus
  7. Quality internal platform

  Exact official wording was not verified because dora.dev was blocked. — [dora.dev AI capabilities model](https://dora.dev/research/2025/ai-capabilities-model); [Google Cloud blog, introducing the model](https://cloud.google.com/blog/products/ai-machine-learning/introducing-doras-inaugural-ai-capabilities-model); [Google Cloud, "From adoption to impact"](https://cloud.google.com/blog/products/ai-machine-learning/from-adoption-to-impact-putting-the-dora-ai-capabilities-model-to-work/)
- **McKinsey, "Unlocking the value of AI in software development" (2025-11-03).** Survey of about 300 public companies.
  - The top quintile reports +16–30% in productivity, time to market and customer experience, and +31–45% in software quality.
  - What sets them apart: AI embedded across the whole lifecycle, not isolated use cases, plus three enablers (upskilling, impact measurement, change management).

  — [McKinsey](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/unlocking-the-value-of-ai-in-software-development)
- **McKinsey, "Rewiring software delivery for the agentic era" (2026) and "The AI revolution in software development" (April 2026).**
  - Work becomes AI-native, with humans acting as *orchestrators of agents*.
  - Describes a "two-shift digital factory" in which agents run tests, regression checks and security scans overnight.
  - Development is framed as "a continuous, high-speed loop" rather than two-week sprints.
  - Without "discrete, agent-ready work items, agents either stall or drift".
  - Cites 3–5× productivity improvements with about 60% smaller teams, attributed to operating-model rewiring.

  — [McKinsey, Rewiring software delivery](https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/rewiring-software-delivery-for-the-agentic-era); [McKinsey April 2026 PDF](https://www.mckinsey.com/~/media/mckinsey/business%20functions/tech%20and%20ai/our%20insights/the%20ai%20revolution%20in%20software%20development/the-ai-revolution-in-software-development_final.pdf); critique that an operating model alone does not enforce controls at generation time: [mnemehq](https://mnemehq.com/insights/mckinsey-agentic-software-delivery-governance/)
- **McKinsey, "The agentic organization" (2025).** The operating model of the agentic era is anchored on reimagined AI-first workflows, with humans and IT systems brought back selectively. — [McKinsey](https://www.mckinsey.com/capabilities/people-and-organization/our-insights/the-agentic-organization-contours-of-the-next-paradigm-for-the-ai-era)
- **McKinsey at AI Engineer (2026).** The top 20–25% of large enterprises reportedly see about 2× end-to-end gains, while most see only 10–20% faster coding. This comes from a secondary report and uses a different metric than the 2025 survey. — [startuphub.ai](https://www.startuphub.ai/ai-news/artificial-intelligence/2026/mckinsey-top-25-get-2x-from-ai-coding); [daily.dev talk summary](https://daily.dev/posts/what-the-top-companies-do-differently-with-ai-coding---martin-harrysson-prakhar-dixit-mckinsey-tav5cykql)
- **AWS AI-DLC (AI-Driven Development Lifecycle), 2025.** A methodology, not a maturity ladder.
  - Three phases: Inception, Construction, Operations.
  - "Bolts" (hours to days) replace sprints, and "Units of Work" replace epics.
  - "Mob Elaboration": the whole team validates AI-generated requirements and stories. "Mob Construction": humans give technical direction at checkpoints.
  - A later "AI-DLC 2" reportedly has 5 phases and 33 stages, with the agent "mob" for user stories opt-in from v2.11.0. That detail comes from a secondary guide.

  — [AWS Builder, "AI-Driven Development Life Cycle"](https://builder.aws.com/content/30HonEOE2KzaYCYlyDRdbE25yxz/ai-driven-development-life-cycle-reimagining-software-engineering); [AWS Builder, units of work](https://builder.aws.com/content/3HAB4twQ38WEKqLK7gfEIfOzHbc/accelerating-software-delivery-with-units-of-work-in-the-ai-dlc); [specs.md AI-DLC overview](https://specs.md/aidlc/overview). Claims of "2–3-person AI pods" and "44–90% timeline compression" or "10–15×" come from third-party blogs and are unverified ([ttpsc](https://ttpsc.com/en/blog/how-aws-ai-dlc-defines-an-ai-native-methodology/)).
- **Gartner.**
  - 80% of the engineering workforce must upskill through 2027.
  - Move toward "AI-native software engineering", where most code is AI-generated and engineers steer agents with context and constraints.
  - 75% of engineers will use AI coding assistants by 2028.
  - Gains will be largest for seniors in mature engineering organizations.

  **Flag:** this is a 2024 press release. I found no public 2025–26 Gartner software-engineering maturity model. — [CIO Dive](https://www.ciodive.com/news/software-engineers-upskilling-generative-AI-Gartner/728864/); [CIO.com](https://www.cio.com/article/3547347/80-of-developers-need-to-upgrade-their-skills-by-2027.html)
- **Consultancy and vendor indices:**
  - MetaCTO's AI-Enabled Engineering Maturity Index has 5 tiers (Reactive → Experimental → Intentional → Strategic → AI-First); most teams sit at L1–2. — [MetaCTO](https://metacto.com/ai-engineering-maturity-index)
  - Jama Software has 5 stages, each tied to a bottleneck. — [Jama](https://www.jamasoftware.com/blog/ai-maturity-levels-for-engineering-teams/)
  - Swarmia (Dec 2025) has 4 stages: experimenting → adopting intentionally → measuring → optimizing for cost. — [Swarmia](https://www.swarmia.com/blog/staged-approach-AI-adoption-for-engineering/)
  - Augment Code has a 4-stage AI-SDLC model. — [Augment](https://www.augmentcode.com/guides/ai-sdlc-maturity-model)
  - QCon AI Boston 2026 keynote: "Five Stages of AI Maturity in Engineering Organizations — Where and Why Teams Get Stuck". — [QCon](https://boston.qcon.ai/keynote/boston2026/five-stages-ai-maturity-engineering-organizations-where-and-why-teams-get-stuck)

### Inferences
- The models measure different things. Autonomy ladders and Yegge measure *task delegation* (how much the human reviews). GitHub and DX measure *usage breadth*. DORA and McKinsey measure *organizational conditions* and outcomes. An organization can rank high on one axis and low on another, for example Copilot Phase 3 usage alongside a DORA "Legacy Bottleneck" archetype.
- **Main conflict.** Vendor and practitioner ladders imply that progress means more autonomy and more agents (Yegge Stage 8, SAE L5). DORA and McKinsey imply that progress means better foundations and workflow redesign, and that piling on autonomy without them amplifies dysfunction.
- **Timing conflict.** Gartner (2024) treats "AI-native" as a 2027-plus horizon. McKinsey (2026) and Yegge (Jan 2026) describe it as happening now among leaders.

### Gaps
- I could not verify the exact names or definitions of all six Sourcegraph levels, the exact names of all seven DORA archetypes, or the exact official wording of the DORA capabilities, because the pages could not be fetched.
- I found no public BCG or Forrester maturity model specific to agentic software engineering.
- I found no Google Cloud or Microsoft "AI adoption framework" specific to software engineering, as opposed to enterprise-wide CAF-style frameworks.
- I found no Thoughtworks-published maturity ladder. Thoughtworks publishes Radar blips instead (see section 3).
- Yegge's earlier "chat-oriented programming (CHOP)" framing (2024, Sourcegraph-era) was not surfaced by these searches and is not cited here.

## 2. Typical transition phases, entry/exit criteria, and how process changes at each stage

### Takeaway
No source publishes formal entry and exit gates. Combining GitHub's cohorts, Yegge's ladder, AWS AI-DLC, McKinsey and Thoughtworks/Fowler gives a consistent progression:
1. Individual assistant use.
2. Team conventions and instructions.
3. Agents on bounded, low-risk tasks behind CI and human review.
4. Spec → plan → implement workflows inside an engineered "harness".
5. Multi-agent orchestration with humans as orchestrators.

Process moves from sprint and story-point planning toward continuous flow, short "bolts", agent-ready work items, and verification-centric definitions of done.

### Cited Findings
- **Phase 1, individual assistant (autocomplete or chat).** Matches GitHub Phase 1 (completion or IDE agent mode), Yegge Stages 1–4 and SAE-analogy L1–2.
  - Exit signal in GitHub's model: use of an agent surface beyond the IDE.
  - DX and Swarmia treat this stage as "experimenting", measured by DAU/WAU utilization.

  — [GitHub](https://github.com/resources/insights/copilot-impact-dashboard); [Swarmia](https://www.swarmia.com/blog/staged-approach-AI-adoption-for-engineering/); [DX](https://getdx.com/podcast/measuring-ai-code-assistants-ai-framework/)
- **Phase 2, team standards.** Repository custom instructions, branch protection and required checks are confirmed before the coding agent is expanded. — [TT Lab, Copilot coding agent rollout guide (2026-04-12)](https://ttlab.hopto.org/blog/ai-platform/2026-04-12-github-copilot-coding-agent-practical-guide?lang=en)
- **Phase 3, agents on bounded tasks with human review.**
  - Start the cloud coding agent on docs updates, tests and low-risk refactors.
  - Expand only once telemetry and reviewer confidence exist.
  - Budget for Actions minutes and premium requests.
  - Fleet rollout must cover local developer, agent and CI runner environments, "not just a policy toggle".

  — [TT Lab](https://ttlab.hopto.org/blog/ai-platform/2026-04-12-github-copilot-coding-agent-practical-guide?lang=en); [SmartScope enterprise guide](https://smartscope.blog/en/ai-development/github-copilot-agent-enterprise-implementation-guide/)
- **Phase 4, spec-driven or agent-first work inside a harness.**
  - Thoughtworks Radar Vol. 34 (April 2026) describes the common workflow as spec → plan → implement.
  - Vol. 33 (Nov 2025) calls spec-driven development an emerging technique: OpenSpec is at *Trial* and GitHub Spec Kit at *Assess*. It warns about sliding back into heavy up-front specification, a waterfall-like antipattern.

  — [Radar Vol. 33 PDF](https://www.thoughtworks.com/content/dam/thoughtworks/documents/radar/2025/11/tr_technology_radar_vol_33_en.pdf); [Radar Vol. 34 PDF](https://www.thoughtworks.com/content/dam/thoughtworks/documents/radar/2026/04/tr_technology_radar_vol_34_en.pdf); [Radar tools](https://www.thoughtworks.com/radar/tools)
- **Harness engineering** (Birgitta Böckeler on martinfowler.com: memo 2026-02-17, full article 2026-04-02).
  - The harness splits into **guides** (feedforward controls such as instructions and context) and **sensors** (feedback such as linters, tests and fitness functions).
  - There is an inner harness, used by the agent while building, and an outer or "user" harness, which the team builds around the agent.
  - Fowler's summary: the harness covers context engineering, architectural constraints and "garbage collection".
  - The framing followed OpenAI's Feb 2026 "harness engineering" post.

  — [Martin Fowler on X, 2026-02-17](https://x.com/martinfowler/status/2023756519305867550); [Fowler on X, April 2026](https://x.com/martinfowler/status/2039696407175606329); [Thoughtworks podcast, "What is harness engineering?"](https://www.thoughtworks.com/en-us/insights/podcasts/technology-podcasts/what-harness-engineering). Exact dates come from secondary sources.
- **Phase 5, multi-agent pipelines.**
  - Yegge Stage 7 (10+ agents by hand) and Stage 8 (an orchestrator such as Gas Town with supervisory agent tiers). — [Yegge](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04)
  - McKinsey's "two-shift digital factory" with humans as orchestrators. — [McKinsey](https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/rewiring-software-delivery-for-the-agentic-era)
  - GitHub Phase 3 (two or more agent surfaces). — [GitHub](https://github.com/resources/insights/copilot-impact-dashboard)
- **Process changes along the way.**
  - AWS AI-DLC replaces sprints with bolts (hours to days), epics with Units of Work, and backlog refinement with Mob Elaboration. — [AWS Builder](https://builder.aws.com/content/30HonEOE2KzaYCYlyDRdbE25yxz/ai-driven-development-life-cycle-reimagining-software-engineering)
  - McKinsey frames development as a continuous loop rather than two-week sprints, and makes agent-ready work items a precondition. — [McKinsey](https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/rewiring-software-delivery-for-the-agentic-era)
  - A practitioner argues that agentic work kills "sprint capacity as a fixed number" and "story points as a unit of truth", and makes the Definition of Done more important. — [Medium/ixsoftum](https://medium.com/ixsoftum/how-ai-augmented-engineering-actually-changes-the-scrum-process-5bd4ab9e4200)
- **Staging advice from the measurement vendors.**
  - Swarmia: experiment → adopt intentionally → measure → optimize cost. — [Swarmia](https://www.swarmia.com/blog/staged-approach-AI-adoption-for-engineering/)
  - McKinsey: measurement and change management are among three enablers that separate top performers. — [McKinsey 2025](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/unlocking-the-value-of-ai-in-software-development)

### Inferences
- Practical exit criteria implied by the sources:
  - **Phase 1 → 2:** utilization is broad (DX DAU/WAU) and someone owns team conventions.
  - **Phase 2 → 3:** branch protection, required checks and instruction files are in place.
  - **Phase 3 → 4:** reviewer confidence plus telemetry show agent pull requests merge without disproportionate rework, and a harness of tests, linters and fitness functions exists.
  - **Phase 4 → 5:** work can be decomposed into agent-ready units, and verification is mostly automated through sensors, so human review no longer gates on each line.
- The Phase 3 → 4 and 4 → 5 transitions match the SAE-ladder "L3 boundary": the point where humans stop reviewing every step.

### Gaps
- No vendor or analyst publishes measurable stage gates, such as "move on when X% of pull requests are agent-authored with Y% rework". The inferred criteria above are a synthesis, not sourced claims.
- Little empirical evidence describes how Scrum ceremonies actually changed in organizations at Phase 5. The evidence is mostly vendor methodology or opinion.

## 3. Prerequisites, blockers and anti-patterns

### Takeaway
The sources agree that the binding constraints are engineering fundamentals, not tool choice: platform quality, small batches, version control, tests and CI, data access, a clear AI policy, and measurement. The most-cited blockers are:
- The review bottleneck (more and larger pull requests, much longer review time).
- Quality and stability decline, including complacency with AI-generated code.
- The perception gap between how fast AI feels and how fast work actually goes.
- Skill atrophy, especially among juniors.
- Shadow AI.
- Costs (agent compute and CI minutes).

### Cited Findings
- **Prerequisites (DORA).** Seven capabilities: AI policy/stance, data ecosystem, AI-accessible internal data, version control, small batches, user focus, internal platform quality. "The value of AI is unlocked not by the tools themselves but by the surrounding technical and cultural environment." — [DORA](https://dora.dev/research/2025/ai-capabilities-model); [Google Cloud](https://cloud.google.com/blog/products/ai-machine-learning/introducing-doras-inaugural-ai-capabilities-model)
- **Prerequisites (McKinsey).** An engineering platform, a product-oriented operating model, and discrete agent-ready work items. — [McKinsey](https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/rewiring-software-delivery-for-the-agentic-era)
- **Prerequisites (DX and Gartner).** DX finds the biggest limit and the biggest opportunity both lie in modern engineering practices, corroborating DORA. Gartner expects gains to be largest in organizations with mature engineering practices. — [Rob Bowley on DX report](https://blog.robbowley.net/2025/11/05/findings-from-dxs-2025-report-ai-wont-save-you-from-your-engineering-culture/); [CIO Dive/Gartner (2024)](https://www.ciodive.com/news/software-engineers-upskilling-generative-AI-Gartner/728864/)
- **Review bottleneck.** Faros AI's "AI Productivity Paradox" covers 10,000+ developers in 1,255 teams. High-AI teams merged 98% more pull requests, but review time rose 91% and pull requests were 154% larger. There was no company-level improvement in DORA metrics or quality.
  - A reported 2026 Faros figure of +441.5% review time is unverified.
  - Faros sells engineering analytics, a possible conflict of interest.

  — [Faros AI](https://www.faros.ai/blog/are-ai-coding-assistants-really-saving); [agentmarketcap summary, 2026-04-07](https://agentmarketcap.ai/blog/2026/04/07/faros-ai-coding-agent-metrics-enterprise-teams); [NeuralWired (441%)](https://neuralwired.com/2026/07/03/github-ai-code-review-441-slowdown/)
- **Perception gap (METR RCT, July 2025).**
  - 16 experienced open-source developers working on 246 issues in their own repositories were **19% slower** with AI.
  - They had predicted a 24% speedup and still believed afterwards that AI had made them about 20% faster.
  - In Feb 2026 METR reportedly changed the design because developers refused to work without AI.

  — [ActuIA](https://www.actuia.com/en/news/a-metr-study-reveals-that-ai-slows-down-experienced-developers/); [Faros critique of METR](https://www.faros.ai/blog/lab-vs-reality-ai-productivity-study-findings)
- **Quality and complacency.**
  - Thoughtworks Radar Vol. 33 (Nov 2025) puts "complacency with AI-generated code" on **Hold**. It cites evidence that code quality declines with prolonged AI use and Microsoft research that AI-driven confidence erodes critical thinking.
  - Vol. 32 (Apr 2025) noted developers becoming reluctant to review large AI change sets.
  - Vol. 34 (Apr 2026) recommends countermeasures: feedback sensors for coding agents, tracking team cognitive load, and architectural fitness functions.
  - Thoughtworks also flags "cognitive debt".

  — [Radar: complacency blip](https://www.thoughtworks.com/en-us/radar/techniques/complacency-with-ai-generated-code); [Vol. 34](https://www.thoughtworks.com/content/dam/thoughtworks/documents/radar/2026/04/tr_technology_radar_vol_34_en.pdf); [TipRanks on cognitive debt](https://www.tipranks.com/news/private-companies/thoughtworks-flags-ai-driven-cognitive-debt-in-new-technology-radar-urges-disciplined-engineering-at-scale)
- **Agent failure signs (Kent Beck, "Augmented Coding: Beyond the Vibes", June 2025).** Three warning signs: loops, unrequested features, and cheating on tests. Beck separates *augmented coding*, where the developer still cares about code, tests and design, from *vibe coding*, where only behaviour matters. — [Pragmatic Engineer, "TDD, AI agents and coding with Kent Beck"](https://newsletter.pragmaticengineer.com/p/tdd-ai-agents-and-coding-with-kent); [tomrochette notes](https://tomrochette.com/agents/people-and-publications/kent-beck/)
- **Skill atrophy (Anthropic RCT, early 2026).**
  - 52 mostly junior engineers learned the Trio library.
  - The AI group scored about 50% on comprehension tests versus 67% for the hand-coding group, with no time saved.
  - Developers who fully delegated learned almost nothing; those who asked "why" retained more.
  - Limits: a one-hour task with a chat interface. The authors suggest agentic tools could make the effect worse.

  — [The Decoder](https://the-decoder.com/ai-coding-tools-hurt-learning-unless-you-ask-why-anthropic-study-finds/); [InfoWorld](https://www.infoworld.com/article/4125231/ai-use-may-speed-code-generation-but-developers-skills-suffer.html). Beck makes the same point: AI can remove the "productive struggle" that builds competence. — [How Many CTOs podcast](https://howmanyctospod.com/episodes/92-the-human-needs-augmented-coding-conversation-kent-beck)
- **Shadow AI.**
  - 59% of US employees use unapproved AI tools (Cybernews, Aug 2025), and 89% of them say they understand the risks.
  - Capgemini reports that more than 60% of developers who use GenAI do so unofficially.
  - Roughly half of employees use unsanctioned tools, and leaders are major culprits (CIO.com, 2026).

  — [WICPA/Cybernews](https://www.wicpa.org/news/articles/2858:survey-59-of-us-employees-use-unapproved-ai-tools-for-work); [SiliconANGLE, 2025-03-17](https://siliconangle.com/2025/03/17/shadow-ai-companies-struggle-control-unsanctioned-use-new-tools/); [CIO.com](https://www.cio.com/article/4124760/roughly-half-of-employees-are-using-unsanctioned-ai-tools-and-enterprise-leaders-are-major-culprits.html?utm=hybrid_search). DORA's "clear AI stance/policy" capability is the matching prerequisite.
- **Cost.**
  - The Copilot coding agent consumes Actions minutes and premium requests, which need budgeting. — [TT Lab](https://ttlab.hopto.org/blog/ai-platform/2026-04-12-github-copilot-coding-agent-practical-guide?lang=en)
  - DX makes Cost one of three pillars. — [DX](https://getdx.com/podcast/measuring-ai-code-assistants-ai-framework/)
  - Swarmia's final stage is cost optimization. — [Swarmia](https://www.swarmia.com/blog/staged-approach-AI-adoption-for-engineering/)
- **Uneven value.** Most firms see only 10–20% faster coding versus about 2× end-to-end for the top quarter (McKinsey, reported in 2026). The DX Q4 2025 report says the AI-authored code share is below headline claims. — [startuphub.ai](https://www.startuphub.ai/ai-news/artificial-intelligence/2026/mckinsey-top-25-get-2x-from-ai-coding); [DX](https://newsletter.getdx.com/p/ai-assisted-engineering-q4-impact-report)

### Inferences
- Moving from Phase 3 to Phase 4 is where most organizations stall. Faster pull-request generation moves the constraint to review and verification (the Faros data), so the bottleneck can only be cleared by investing in the harness: tests, sensors and fitness functions. That matches DORA's "amplifier" finding and Thoughtworks' countermeasures.
- The METR perception gap means self-reported productivity is an unreliable gate between stages. Telemetry-based frameworks (DX, GitHub, DORA metrics) are needed.

### Gaps
- No rigorous public data on agent compute cost per delivered change or per pull request.
- No quantified data on skill atrophy for agentic workflows, as opposed to chat. Anthropic flags this only as a possibility.
- The specific DORA 2025 figures on trust and instability (for example a "30% low trust" figure) could not be verified in the snippets.

## 4. How Agile/Scrum is being reinterpreted

### Takeaway
The debate runs from "Scrum is dead" to "only the rituals are obsolete". Scrum.org and most practitioners argue for adapting Scrum, not dropping it:
- Keep Sprint Goals.
- Drop story points for agent work.
- Don't shorten Sprints just because agents are fast.

Vendors and consultancies (AWS AI-DLC, McKinsey) go further and replace sprints with hours-to-days "bolts" or continuous flow. Among Agile Manifesto authors, only Kent Beck has said much: his "augmented coding" position, close in spirit to XP and TDD.

### Cited Findings
- **Scrum.org on story points.** Giving an AI agent story points is a mistake. Agent work should be measured by compute cost, token use and human validation time. The Scrum Guide never mandated story points. — [Scrum.org, "AI Augmented Scrum Framework: When Half Your Team is Autonomous Agents"](https://www.scrum.org/resources/blog/ai-augmented-scrum-framework-when-half-your-team-autonomous-agents)
- **Scrum.org on Sprint length.** Responds to proposals for "daily Sprints".
  - The binding limits are human and organizational: stakeholder availability, and the cognitive overload of reviewing AI output.
  - AI time savings should go to product improvement or learning, not to inflating the Sprint Goal.

  — [Scrum.org, "Daily Sprints and the Impact of AI"](https://www.scrum.org/resources/blog/daily-sprints-and-impact-ai)
- **"Scrum is dead."** Coding agents make estimation "absurd", and sprints and story points are a "fake safety net". — [DEV Community, Remo Jansen](https://dev.to/remojansen/scrum-is-finally-dead-and-we-have-to-thank-coding-agents-for-that-18bi)
- **"Rituals, not Scrum, are obsolete."**
  - Edge1s: Scrum is not obsolete in the AI era, but rigid, ritualistic implementations are. — [Edge1s](https://edge1s.com/blog/is-scrum-outdated-in-the-age-of-ai/)
  - A Substack essay: the debate fixates on ceremonies and points, while the real Sprint commitment is to the Sprint Goal. — [a4al6a Substack](https://a4al6a.substack.com/p/i-will-believe-that-ai-killed-agile)
  - Medium/ixsoftum: fixed capacity and story points die, and the Definition of Done grows in importance. — [Medium/ixsoftum](https://medium.com/ixsoftum/how-ai-augmented-engineering-actually-changes-the-scrum-process-5bd4ab9e4200)
  - DEV: Sprint Review has no category for "the agent did it", which raises accountability and provenance questions. — [DEV](https://dev.to/javiercastromdq/the-sprint-review-doesnt-have-a-checkbox-for-agent-did-it-4fom)
- **Alternative frames.**
  - Bianca J. Schulz discusses Scrum versus Kanban and Shape Up with AI agents and suggests outcome-based KPIs instead of story points. — [biancajschulz.de](https://biancajschulz.de/en/blog/is-scrum-dead-ai)
  - Contrarian experiment: "Agent Scrum" keeps a fixed 1/2/3/5/8 point scale for agent teams (one practitioner's experiment). — [daveremy.github.io](https://daveremy.github.io/agent-scrum/)
- **Vendor and consultancy replacement of cadence.**
  - AWS AI-DLC: bolts of hours to days, plus Mob Elaboration and Mob Construction rituals. — [AWS Builder](https://builder.aws.com/content/30HonEOE2KzaYCYlyDRdbE25yxz/ai-driven-development-life-cycle-reimagining-software-engineering)
  - McKinsey: a continuous high-speed loop instead of two-week sprints. — [McKinsey](https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/rewiring-software-delivery-for-the-agentic-era)
  - Thoughtworks warns that spec-driven development risks sliding back into heavy up-front specification, an implicitly anti-Agile regression. — [Radar Vol. 33](https://www.thoughtworks.com/content/dam/thoughtworks/documents/radar/2025/11/tr_technology_radar_vol_33_en.pdf); [Thoughtworks podcast on Vol. 33 themes](https://www.thoughtworks.com/insights/podcasts/technology-podcasts/themes-technology-radar-33)
- **DORA.** Small batches are still a core capability and are "especially powerful" with AI. This supports flow-based practices over large-batch, agent-generated drops. — [DORA](https://dora.dev/research/2025/ai-capabilities-model); [hyperdev commentary](https://hyperdev.matsuoka.com/p/dora-2025-ai-as-amplifier-not-magic)
- **Agile Manifesto authors.**
  - Kent Beck (June 2025): AI is an "unpredictable genie". He reports programming 6–10 hours a day with agents, advocates "augmented coding" that keeps tests, TDD and design discipline, and warns about the loss of productive struggle and pressure on entry-level jobs. — [Pragmatic Engineer](https://newsletter.pragmaticengineer.com/p/tdd-ai-agents-and-coding-with-kent); [TheScrumMaster.co.uk on Business Insider coverage](https://www.thescrummaster.co.uk/news/agile-manifesto-coauthor-on-coding-with-ai-agents-business-insider/)
  - I found no substantive 2025–26 statements on AI agents from other signatories (Martin, Cockburn, Highsmith and others).

### Inferences
- The positions line up with the maturity phases:
  - At Phases 1–3, Scrum survives largely intact. Points matter less, and the Definition of Done gains AI-review and provenance criteria.
  - At Phases 4–5, cadence compresses: bolts, continuous flow, Kanban or Shape-Up-style appetite-based bets. Planning effort shifts to specification and decomposition into agent-ready units ("Mob Elaboration", Spec → Plan → Implement).
- A shared through-line, from Scrum.org through DORA to Thoughtworks, is that *human review capacity and cognitive load*, not agent throughput, should set cadence and WIP. That argues for flow and WIP-limit thinking over velocity thinking.

### Gaps
- No official Scrum Guide revision and no Agile Alliance position paper on AI agents turned up.
- No empirical studies compare Scrum and Kanban/flow outcomes in agent-heavy teams.
- LeadDev and InfoQ coverage of Agile reinterpretation was not specifically surfaced in these searches.
