# VM Agent-Native Project Charter

## Mission

**Make Varun Malhotra the most AI-native executive in federal consulting.**

Not AI-curious. Not AI-augmented. AI-native — where every decision, workflow, and deliverable flows through an intelligent system that learns, adapts, and compounds over time. The agent isn't a tool you use. It's infrastructure you operate on.

## Vision

A single human, backed by a world-class agent system, operating with the intelligence surface of a 50-person team. Real-time market intelligence. Automated opportunity capture. Multi-model orchestration that optimizes itself. Institutional memory that never forgets. All of it composable, auditable, and continuously improving.

This isn't about replacing people. It's about redefining what one person with the right system can do — and then bringing that capability to Changeis clients.

## Why This Matters

1. **Personal edge** — As CEO, Varun's time is the scarcest resource. Every hour the agent system saves is an hour redirected to strategy, relationships, and decisions only a human can make.

2. **Proof of concept** — Changeis is selling agentic services to federal clients. Varun operating AI-native *is* the demo. Every workflow we build here becomes a reference architecture for client engagements.

3. **Compounding advantage** — AI-native isn't a one-time upgrade. Each workflow automated, each memory stored, each optimization logged makes the system better tomorrow than it is today. Competitors who start later can't catch up.

## Principles

1. **Quality over speed** — A wrong answer fast is worse than a right answer later. Use the right model for the right job. Never cut corners on deliverables.

2. **Human in the loop, agent in the flow** — The human sets direction, makes judgment calls, and handles exceptions. The agent handles execution, coordination, and scale.

3. **Transparent operations** — Every model choice, cost decision, and quality tradeoff is logged and visible. No black boxes.

4. **Continuous optimization** — The system improves itself. Track metrics, identify waste, upgrade workflows, log changes. Never settle.

5. **Security by default** — Private data stays private. External actions require approval. Audit trails for everything that matters.

6. **Eat your own cooking** — Every capability built for Varun should be generalizable to Changeis clients. If it works for a CEO, it works for a federal program office.

## Workstreams

### WS-1: Multi-Agent Orchestration
**Status:** Active — foundational infrastructure in place
**Goal:** A fleet of specialized agents coordinating through shared workspace, memory, and task handoffs.

**What exists:**
- Main session (Opus) — direct interaction, orchestration, strategic work
- Nightly crons — agentic-services-research (Opus), xsam-monitor (Sonnet), reddit-scan (Haiku)
- Heartbeat system — 15-min intelligence scans
- Sub-agent spawning via OpenClaw sessions_spawn
- Shared workspace at /data/.openclaw/workspace/

**What's needed:**
- Multi-model sub-agent pipelines (Haiku scraper → Sonnet analyst → Opus writer)
- Agent-to-agent communication patterns (not just shared files)
- Error recovery and retry logic for failed agent runs
- Agent health monitoring (did the 1 AM cron actually succeed?)
- Workflow templates — reusable patterns for common multi-agent tasks

### WS-2: Model Optimization
**Status:** Active — tiering strategy established, dashboard live
**Goal:** Optimal model selection for every task, continuously refined.

**What exists:**
- MODEL-STRATEGY.md — tiering philosophy and rules
- Model Usage Dashboard — https://vm-coderock.github.io/model-usage.html
- Three-tier system: Haiku (scrape) → Sonnet (analyze) → Opus (strategize)
- Optimization log with cost impact tracking

**What's needed:**
- Automated cost tracking per workflow run (tokens used × rate)
- Quality scoring system (1-5 per deliverable, track rework rate)
- Model benchmarking — when new models drop, evaluate against current tiers
- Cost alerts — flag if a workflow exceeds expected spend
- Monthly optimization review cadence

### WS-3: Intelligence & Research Automation
**Status:** Active — multiple systems operational
**Goal:** Continuous, automated intelligence gathering across all domains that matter.

**What exists:**
- Heartbeat scans (topics.json — FAA, AI, govcon, human capital)
- XSAM nightly monitor (SAM.gov opportunity tracking)
- Reddit nightly scan (r/ATC, r/govcon, r/fednews)
- VEB executive briefs (daily editorial intelligence)
- Agentic Services research (7-stream deep research project)
- xopp workflow (full SAM.gov opportunity analysis pipeline)

**What's needed:**
- Email intelligence automation (auto-triage, newsletter extraction, action items)
- Calendar integration (proactive briefings before meetings)
- LinkedIn/social monitoring (track competitors, partners, key contacts)
- News clustering — group related stories across sources, deduplicate
- Automated VEB assembly — collect → summarize → draft → review pipeline
- RSS/feed monitoring for key publications (FedScoop, FCW, GovExec, NextGov)

### WS-4: Memory & Knowledge Management
**Status:** Partial — daily memory files, workspace docs
**Goal:** Persistent, searchable institutional memory that compounds over time.

**What exists:**
- Daily memory files (memory/YYYY-MM-DD.md)
- MEMORY.md (long-term curated)
- Heartbeat state tracking
- Project-specific knowledge in Dropbox

**What's needed:**
- Structured knowledge base (not just daily logs — entities, relationships, decisions)
- Semantic search over memory (find "what did we decide about SATSS-II teaming?")
- Automatic memory consolidation (daily → weekly → monthly summaries)
- Contact/relationship tracking (who did we talk to, about what, when)
- Decision log (what we decided, why, what the alternatives were)
- Lessons learned database (what worked, what didn't, patterns)

### WS-5: Tool Integration & Automation
**Status:** Partial — core tools connected, gaps remain
**Goal:** Every tool Varun uses is agent-accessible and automated where possible.

**What exists:**
- Email (himalaya — IMAP/SMTP)
- Task management (Todoist)
- GitHub (repos, Pages, CI)
- SAM.gov API (opportunity tracking)
- Web search (Brave)
- Dropbox sync
- NordVPN SOCKS5 (proxy for blocked services)

**What's needed:**
- Google Workspace (Gmail, Calendar, Drive) — gog OAuth setup blocked
- SharePoint/Teams integration (Changeis corporate systems)
- LinkedIn API or browser automation
- SAM.gov saved searches (automated, not manual API calls)
- USASpending.gov automated tracking
- Slack/Teams monitoring for client channels
- PDF generation (polished reports from HTML)
- Voice/TTS for briefings (ElevenLabs or similar)

### WS-6: Dashboards & Visibility
**Status:** Active — hub and model dashboard live
**Goal:** Everything important is visible at a glance, always current.

**What exists:**
- Intelligence Hub (https://vm-coderock.github.io/)
- Model Usage Dashboard
- Individual analysis pages (xopp outputs)
- Agentic Services research hub

**What's needed:**
- Mission Control dashboard (Kanban, agent activity, cron status, intel feed)
- Real-time agent status (what's running now, what ran last, what failed)
- Portfolio view (all tracked opportunities, status, deadlines, actions)
- Cost tracking dashboard (daily/weekly/monthly spend by model and workflow)
- Quality metrics dashboard (deliverable scores, rework rates)

### WS-7: Security, Governance & Compliance
**Status:** Foundational — basic practices in place
**Goal:** Enterprise-grade security and auditability befitting a federal contractor.

**What exists:**
- Private data handling rules (SOUL.md, AGENTS.md)
- External action approval requirements
- Workspace isolation
- Gateway authentication

**What's needed:**
- Audit trail for all external actions (emails sent, files shared, APIs called)
- Data classification (what's public, internal, confidential, restricted)
- Access control documentation (what the agent can and can't do)
- Incident response plan (what if the agent sends something wrong?)
- Compliance mapping to federal standards (for when we sell this to clients)
- Backup and recovery (workspace, memory, configurations)

### WS-8: Client Replication Framework
**Status:** Not started — dependent on WS-1 through WS-7 maturity
**Goal:** Package the VM Agent-Native system into a deployable framework for Changeis clients.

**What's needed:**
- Reference architecture document
- Deployment playbook (how to stand up an agent-native system for a client)
- Customization guide (which workflows apply to which client types)
- Security and compliance package (FedRAMP, NIST 800-53 mapping)
- Training materials (how to be an AI-native operator)
- ROI calculator (hours saved, cost reduction, quality improvement)
- This is the bridge between personal system and Changeis service offering

## Success Metrics

| Metric | Current | 30-Day Target | 90-Day Target |
|--------|---------|---------------|---------------|
| Workflows automated | 5 | 10 | 20 |
| Model cost efficiency | Baseline | -30% per deliverable | -50% per deliverable |
| Intelligence coverage | FAA + govcon | + DoD, DHS, OPM | Full federal landscape |
| Memory searchability | File grep | Structured queries | Semantic search |
| Tool integrations | 7 | 12 | 20 |
| Deliverable quality (1-5) | Untracked | 4.0 avg | 4.5 avg |
| Time to opportunity analysis | ~2 hours manual | 45 min (multi-agent) | 20 min (automated pipeline) |
| Agent uptime | Best-effort | 95% | 99% |

## Timeline

**Phase 1 (Weeks 1-2): Foundation** ← WE ARE HERE
- ✅ Multi-agent infrastructure (crons, sub-agents, shared workspace)
- ✅ Model tiering strategy and dashboard
- ✅ Intelligence automation (heartbeat, xsam, reddit, VEB)
- 🔄 Multi-model pipelines (xopp, VEB)
- 🔄 Mission Control dashboard
- 🔲 Google Workspace integration

**Phase 2 (Weeks 3-4): Expansion**
- Memory and knowledge management overhaul
- Tool integration sprint (calendar, LinkedIn, RSS)
- Automated VEB assembly pipeline
- Cost tracking and quality metrics
- Agent health monitoring

**Phase 3 (Weeks 5-8): Optimization**
- Semantic memory search
- News clustering and deduplication
- Portfolio opportunity dashboard
- Security audit and compliance mapping
- Monthly optimization cadence

**Phase 4 (Weeks 9-12): Client Readiness**
- Reference architecture documentation
- Deployment playbook
- ROI framework and case studies
- First client pilot (internal Changeis team?)

## Governance

- **Executive sponsor:** Varun Malhotra (CEO, Changeis)
- **System operator:** VM2 (AI agent system)
- **Review cadence:** Weekly progress check via VEB or dedicated briefing
- **Decision authority:** Varun approves all external-facing changes, new integrations, and budget decisions
- **Optimization authority:** VM2 autonomously optimizes within established tiers and rules; logs all changes

---

*This charter is a living document. Updated as the project evolves.*
*Created: March 11, 2026*
