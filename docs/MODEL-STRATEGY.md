# MODEL-STRATEGY.md — Optimal Model Tiering

## Philosophy
Use the cheapest model that delivers the required quality. Never overpay for routine work. Never underpay for strategic work. Quality matters — the tier defines the floor, not the ceiling.

## Tier Definitions

### 🟢 Haiku 4.5 — Data Collection & Scraping
**Cost:** ~$0.25/MTok input, $1.25/MTok output
**Use when:** The task is structured, repetitive, or the output is raw data that will be processed downstream.
- Reddit scanning (keyword matching, flagging)
- RSS/feed monitoring
- Simple web scraping and data extraction
- Status checks (is this site up? did this file change?)
- Formatting/templating (fill in a known template)
- Simple file operations (copy, rename, organize)

### 🟡 Sonnet 4.5 — Intel & Analysis Work
**Cost:** ~$3/MTok input, $15/MTok output
**Use when:** The task requires judgment, synthesis, or producing polished content from raw inputs.
- SAM.gov opportunity monitoring (xsam) — needs to evaluate significance
- News/topic scanning (heartbeat intel)
- Competitive intelligence gathering
- Email triage and summarization
- First-draft VEB sections from collected data
- xopp data processing (extract, parse, organize attachments)
- Code generation for dashboards/pages
- Todoist task management

### 🔴 Opus 4.6 — Planning, Orchestration, QA & High-Value
**Cost:** ~$15/MTok input, $75/MTok output
**Use when:** The task requires strategic thinking, multi-step planning, quality assurance, or is client-facing.
- Main session (direct conversation with Varun)
- Agentic services deep research (strategy, frameworks, models)
- xopp final analysis writing (the published HTML)
- VEB editorial review and final assembly
- Quality assurance passes on any deliverable
- Workflow orchestration (deciding what to do, in what order)
- Complex reasoning (pricing models, positioning strategy, competitive analysis)
- Anything going to a client or public page

## Workflow Model Maps

### Heartbeat Scan (every 15 min)
| Step | Model | Why |
|------|-------|-----|
| Topic search (web_search) | Main session (Opus) | Runs in-session, judgment needed to filter noise |

### xsam Nightly Monitor (1:30 AM)
| Step | Model | Why |
|------|-------|-----|
| Fetch SAM.gov API | Sonnet | Structured data retrieval + significance evaluation |
| Download attachments | Sonnet | Mechanical but needs error handling |
| Search for related opps | Sonnet | Needs judgment on relevance |
| Competitive intel search | Sonnet | Synthesis of search results |
| Update watchlist | Sonnet | Simple structured update |
| Report to memory | Sonnet | Light summarization |

### xopp Full Analysis (on demand)
| Step | Model | Ideal |
|------|-------|-------|
| Download docs from SAM.gov | Haiku | Mechanical fetching |
| Extract text (PDF/XLSX) | Haiku | Structured extraction |
| Parse and organize data | Sonnet | Needs some judgment |
| **Write analysis HTML** | **Opus** | **Strategic, client-facing** |
| **QA review** | **Opus** | **Quality gate** |
| Git push + Dropbox sync | Haiku | Mechanical |

### VEB Brief (daily)
| Step | Model | Ideal |
|------|-------|-------|
| Collect source articles | Haiku | Web fetch, scraping |
| Summarize each source | Sonnet | Synthesis |
| **Write editorial sections** | **Opus** | **Voice, insight, strategy** |
| **Final assembly + QA** | **Opus** | **Quality gate** |
| Publish (git, Dropbox) | Haiku | Mechanical |

### Agentic Services Research (1:00 AM nightly)
| Step | Model | Why |
|------|-------|-----|
| All steps | Opus | Deep strategic research — every output is a deliverable |

### Reddit Scan (2:00 AM nightly)
| Step | Model | Why |
|------|-------|-----|
| All steps | Haiku | Keyword search + flag |

## Active Cron Assignments
| Time | Job | Model | Tier |
|------|-----|-------|------|
| 1:00 AM | agentic-services-research | Opus (default) | 🔴 |
| 1:30 AM | xsam-monitor | Sonnet 4.5 | 🟡 |
| 2:00 AM | reddit-scan | Haiku 4.5 | 🟢 |

## Cost Optimization Rules
1. **Never use Opus for data collection** — it's 60x more expensive than Haiku for output
2. **Never use Haiku for strategy** — cheap output that needs to be redone costs more than doing it right
3. **When in doubt, use Sonnet** — it's the safe middle ground
4. **Multi-step workflows should cascade up** — start cheap, escalate for judgment
5. **QA always runs at Opus** — catching errors at the quality gate saves rework
6. **Track cost per deliverable** — not cost per token. A $2 Opus analysis that's right > a $0.10 Haiku analysis that's wrong

## Metrics to Track
- Cost per workflow run (tokens × rate)
- Quality score (did it need human revision? 1-5 scale)
- Time to complete
- Rework rate (how often does output need to be redone at a higher tier)

---
*Updated: March 11, 2026. Review monthly or when models/pricing change.*
