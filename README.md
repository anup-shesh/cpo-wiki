# CPO Intelligence Wiki — an LLM Wiki for Chief Product Officers

A personal knowledge system for Chief Product Officers — built and maintained by Claude. Inspired by [Andrej Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

Instead of searching files every time you have a question, Claude maintains a **living wiki** that compounds everything you know — competitive intel, customer insights, product decisions, delivery tracking, and team performance — getting richer with every source you add.

---

## What you'll need

- [Claude Code](https://claude.ai/code) — the AI agent that maintains your wiki
- [Obsidian](https://obsidian.md) — where you read and browse your wiki
- [Obsidian Web Clipper](https://obsidian.md/clipper) — browser extension to clip articles into your wiki

---

## Setup (one time)

**Step 1 — Download the prompt**

Download `cpo-intelligence-wiki.md` from this repo.

**Step 2 — Create your Obsidian vault**

Open Obsidian and create a new vault, or use an existing one.

**Step 3 — Let Claude do the rest**

Open Claude Code and navigate to your Obsidian vault folder. Copy the full contents of `cpo-intelligence-wiki.md` and paste it as your first message. Claude will:
- Create the `cpo-wiki/` folder structure inside your vault
- Save itself as `CLAUDE.md` — the schema it reads every session
- Create empty `index.md` and `log.md` files, ready for your first ingest

<img width="1081" height="722" alt="image" src="https://github.com/user-attachments/assets/4090bb82-c157-430e-92e2-03409700d59a" />


**Step 4 — Install Obsidian plugins**

In Obsidian, go to Settings → Community Plugins and install:
- **Dataview** — lets Claude tag pages with metadata you can query
- **Marp** (optional) — lets Claude generate slide decks from wiki content

**Step 5 — Set up Obsidian Web Clipper**

Install the [Obsidian Web Clipper](https://obsidian.md/clipper) browser extension. Configure it to save clipped articles into `cpo-wiki/raw/`. Use it to pull in competitor pages, analyst articles, or anything you want Claude to ingest.

---

## Starting a session

1. Open Obsidian and Claude Code side by side
2. In Claude Code, navigate to the `cpo-wiki/` folder and type `Start`

Claude will confirm today's date, how many pages are in your wiki, and what was last ingested. You're ready.

---

## How to use it

**Ingesting a source**

Drop any file into `cpo-wiki/raw/` — a call transcript, a PDF, a clipped article — and tell Claude:

> *"Ingest [filename]"*

Claude reads it, updates the relevant wiki pages, and logs the ingest.

**Asking questions**

Ask anything in plain English:

> *"What are the top reasons enterprise customers churn?"*
> *"Which delivery initiatives are most at risk this quarter?"*
> *"How has Competitor X repositioned in the last six months?"*

Claude searches the wiki, synthesizes an answer, and cites its sources. Good answers get saved back as new wiki pages.

**Keeping the wiki healthy**

Once a month, tell Claude:

> *"Lint the wiki"*

Claude checks for stale pages, missing cross-references, contradictions, and orphan pages — and suggests what to investigate next.

---

## What the wiki covers

| Domain | What it tracks |
|--------|----------------|
| Competitive Intelligence | Competitor moves, positioning, battlecards |
| Customer Insights | Pain themes, feature requests, churn signals |
| Product Decision Memory | What was decided, why, what was rejected |
| Delivery Tracking | Initiative status, blockers, shipped log |
| Team & Performance | OKRs, metrics, squad health |

---

## Tips

- **Start with one domain.** Competitive intel or customer insights is the easiest place to begin. Get comfortable with the ingest/query loop before expanding.
- **Stay involved during ingests.** Claude will discuss key takeaways before updating pages — use this to guide what gets emphasized.
- **Use Obsidian's graph view** to see what's connected to what. Pages with many links are your knowledge hubs.
- **The schema is yours.** If you want Claude to track something differently, edit `CLAUDE.md` and tell Claude what changed. It will adapt.

---

## Credits

Pattern by [Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f). Adapted for CPOs.
