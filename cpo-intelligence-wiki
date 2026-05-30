# CPO Intelligence Wiki
*A personal knowledge system for Chief Product Officers, built and maintained by Claude.*

This is an idea file designed to be copy-pasted into Claude Code. Share it at the start of every session. Claude will build out your wiki in collaboration with you — starting simple, growing richer over time.

---

## What this is

Your job generates more signal than any human can synthesize: customer calls, competitor moves, sprint data, team performance, roadmap debates. Most of it disappears into Slack, Notion, or your own memory. Nothing compounds.

This system changes that. Instead of asking Claude to "search your files" every time you have a question, Claude maintains a **living wiki** — a structured set of interlinked notes that gets smarter every time you add something new. When you feed it a competitor's press release, Claude doesn't just file it. It reads it, connects it to what you already know, flags where it contradicts your current assumptions, and updates the relevant pages across your wiki.

The wiki is your second brain. Claude is the one doing the maintenance.

---

## What you do (the CPO's role)

You do three things:

1. **Drop in sources.** Paste a call transcript, upload an analyst report, share a sprint summary. Tell Claude: *"ingest this."*
2. **Ask questions.** Ask anything: *"What are customers saying about onboarding?"* or *"How has our delivery velocity changed this quarter?"* Claude searches the wiki, synthesizes an answer, and cites its sources.
3. **Explore and redirect.** Read the wiki in Obsidian. Follow links. Notice what's missing. Tell Claude what to dig into next.

You never write the wiki yourself. Claude writes and maintains all of it.

---

## What Claude does (the agent's role)

You maintain a persistent wiki in the user's Obsidian vault under a folder called `cpo-wiki/`. The wiki is organized into five domains. For every ingest, query, or lint operation, follow the conventions in this document. When in doubt, ask the user before creating new page types or changing structure.

**Session start command:** When the user says `Start`, read `CLAUDE.md` and `index.md` and respond with a one-line confirmation: what date it is, how many pages are in the wiki, and what was last ingested.

---

## The five domains

Your wiki is organized into five sections, each covering a distinct area of the CPO's work:

### 1. Competitive Intelligence (`cpo-wiki/competitive/`)
*What your competitors are doing, how they're positioning, where they're moving.*

**Raw sources you'll feed here:** competitor press releases, product launch announcements, G2/Trustpilot reviews of competitors, analyst reports (Gartner, Forrester), LinkedIn posts from competitor PMs, win/loss call notes.

**Page types Claude maintains:**
- One page per competitor (positioning, product moves, pricing, weaknesses)
- A `competitive-overview.md` — the landscape at a glance
- A `battlecards.md` — where you're stronger, where you're vulnerable
- A `signals-log.md` — chronological feed of notable moves

### 2. Customer Insights (`cpo-wiki/customers/`)
*What customers actually want, say, and feel — accumulated over time.*

**Raw sources you'll feed here:** sales call transcripts, CS escalation notes, NPS verbatims, support ticket themes, user interview notes, churn reason reports.

**Page types Claude maintains:**
- One page per major customer segment or persona
- A `pain-themes.md` — recurring problems, ranked by frequency
- A `feature-requests.md` — what's being asked for, with supporting quotes
- A `churn-signals.md` — patterns in why customers leave

### 3. Product Decision Memory (`cpo-wiki/decisions/`)
*Why you chose what you chose — so you never relitigate settled debates.*

**Raw sources you'll feed here:** PRD excerpts, roadmap review notes, design review summaries, your own voice memos or journal entries about strategic choices.

**Page types Claude maintains:**
- One page per significant decision (what was decided, what was considered, what was rejected and why)
- A `principles.md` — recurring rules of thumb that have held up
- A `reversals.md` — decisions that were changed and what caused the shift

### 4. Product Development & Delivery (`cpo-wiki/delivery/`)
*What's being built, what shipped, what's slipping, and why.*

**Raw sources you'll feed here:** sprint review summaries, release notes, incident post-mortems, roadmap snapshots, dependency logs.

**Page types Claude maintains:**
- One page per major initiative (status, owner, blockers, key milestones)
- A `shipped.md` — rolling log of what launched and when
- A `blockers.md` — recurring friction patterns across teams
- A `roadmap-snapshot.md` — current quarter priorities, updated each ingest

### 5. Team & Product Performance (`cpo-wiki/performance/`)
*How your teams and your product are actually doing over time.*

**Raw sources you'll feed here:** OKR check-ins, engineering velocity reports, product usage analytics summaries, Net Revenue Retention data, team health survey results.

**Page types Claude maintains:**
- One page per team or squad (current focus, recent wins, concerns)
- A `metrics-dashboard.md` — key numbers with trend notes (not a live dashboard — a narrative summary)
- A `okr-tracker.md` — current OKRs, progress, risk flags

---

## Architecture

There are three layers. Do not mix them.

**Raw sources** (`cpo-wiki/raw/`) — everything you feed in. Call transcripts, PDFs, copied articles, sprint exports. Immutable. Claude reads from here but never edits these files.

**The wiki** (`cpo-wiki/` subfolders above) — Claude-generated and Claude-maintained. Pages are markdown files. Claude creates, updates, and cross-links them. You read them in Obsidian.

**The schema** (this file, saved as `cpo-wiki/CLAUDE.md`) — the instructions Claude follows. When you want to change how the wiki works, edit this file. Claude will adapt.

---

## Operations

### Ingest
*What you do:* Drop a file into `cpo-wiki/raw/` and tell Claude: *"Ingest [filename]."*

*What Claude does:* Read the source. Identify which domain(s) it belongs to. Discuss key takeaways with the user briefly. Write or update the relevant wiki pages. Update `index.md`. Append an entry to `log.md`. A single source may touch 5–10 pages across domains — for example, a customer call might update a pain theme, a competitor mention, and a delivery blocker simultaneously.

**Claude must always cross-link.** If a customer complaint names a competitor, the customer insight page links to the competitor page. If a delivery blocker is causing churn, the blockers page links to the churn signals page.

### Query
*What you do:* Ask Claude anything in plain English. Examples:
- *"What are the top three reasons enterprise customers churn?"*
- *"How has Competitor X changed their pricing positioning this year?"*
- *"Which initiatives are most at risk this quarter?"*

*What Claude does:* Read `index.md` first. Pull the relevant pages. Synthesize a direct answer with citations to specific wiki pages. If the answer is valuable — a good comparison, a pattern, a strategic insight — offer to save it as a new wiki page so it compounds into the knowledge base.

### Lint
*What you do:* Periodically tell Claude: *"Lint the wiki."* Do this monthly or after a major batch of ingests.

*What Claude does:* Scan for — contradictions between pages, stale claims superseded by newer sources, orphan pages with no inbound links, important topics mentioned but lacking their own page, missing cross-references, data gaps worth investigating. Produce a short health report and a list of suggested next sources to find.

---

## Indexing and logging

**`cpo-wiki/index.md`** — a catalog of every page in the wiki: link, one-line summary, domain tag. Claude reads this first on every query. Claude updates it on every ingest. Format:

```
| Page | Domain | Summary |
|------|--------|---------|
| [Competitor X](competitive/competitor-x.md) | competitive | Positioning, product moves, pricing as of Q2 2026 |
```

**`cpo-wiki/log.md`** — append-only chronological record. Every ingest, query, and lint pass gets an entry. Format:

```
## [2026-05-30] ingest | Gartner Magic Quadrant 2026
## [2026-05-30] query | Top enterprise churn reasons
## [2026-05-31] lint | Monthly health check
```

---

## Setting up Obsidian

*These are one-time steps you take yourself before your first session:*

1. Open Obsidian. Create a new vault or use your existing one.
2. Create a folder called `cpo-wiki/` inside the vault.
3. Save this document as `cpo-wiki/CLAUDE.md`.
4. Install the **Obsidian Web Clipper** browser extension — use it to clip articles and competitor pages directly into `cpo-wiki/raw/` as markdown.
5. Enable the **Dataview** plugin (Obsidian community plugins) — Claude can add metadata tags to pages so you can run queries like "show all pages tagged `competitor` updated this month."
6. Open Obsidian's graph view anytime to see what's connected to what.

*To start every Claude Code session:*
- Keep Claude Code open in one window, Obsidian open in the other.
- Type `Start` — Claude will read your wiki, confirm today's date, page count, and last ingest, and is ready to go.

---

## Why this works for a CPO

The problem with every knowledge system CPOs try is maintenance. Someone has to update the Notion pages, keep the competitive tracker current, consolidate the customer research. That someone never has time. The pages go stale. The system gets abandoned.

Claude doesn't get bored. It doesn't forget to update a cross-reference. It can touch fifteen pages in one pass. The cost of maintenance is near zero.

Your job is to bring the signals — the calls, the reports, the intuitions. Claude's job is everything else: the filing, the cross-referencing, the synthesis, the flagging of contradictions. Over months, the wiki becomes a genuine competitive asset. Every new hire, every strategy review, every board prep starts from a richer base than the last one.

---

## Note

Start small. Begin with one domain — competitive intel or customer insights — and get comfortable with the ingest/query loop before expanding. The schema is yours to evolve. If you want Claude to capture something differently, edit `CLAUDE.md` and tell Claude what changed. The right version of this wiki is the one that fits how you actually think.
