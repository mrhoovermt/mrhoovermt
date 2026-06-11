<p align="center">
  <img src="./jake1.png" alt="Jake Hoover — pixel art portrait" width="400">
</p>

# Hello. I hope you're here from Anthropic. I've been waiting.

I'm Jake Hoover. I'm a service tech by trade, a casino operator by circumstance, and a builder by compulsion. I have more ideas than I could ever execute — or at least, that used to be true. Claude and Claude Code changed that.

I didn't start with Claude. I started with Gemini, made some songs with Suno, played around with image generation. Honestly, I wasn't paying much attention to Anthropic until you told the US Government **no**. I was sold. The Hardfork podcast mentioned how far the coding had come, so I figured I'd take a leap.

It changed my life. I'm not being dramatic. It literally changed my life.

---

## The Short Version

I'm a solo founder with no traditional engineering background building production SaaS entirely through Claude Code. My flagship product — **Hoover Bookkeeping & Payroll** — is a full QuickBooks replacement running in production for my casino. It has 56 database models, AI-powered receipt extraction, bank reconciliation, full payroll with federal and state tax calculations, and a multi-tenant architecture preparing for a second business. It's not completely finished, but it is very close. I'm starting live testing at my casino on 6/13/26 for real remote deposit processing.

I also moderate [r/claude](https://reddit.com/r/claude), hold Swiss citizenship, and I'm currently building a platform called FLIPNET that's designed to be transferred to a Swiss Foundation and belong to humanity forever. I'm married with three dogs and two cats. 

I'm looking for a role at Anthropic where I can help other people do what I did.

---

## How I Got Here

I dropped out of college after setting the class average in Calc 2 without attending a single lecture. Khan Academy taught me better than the professor did. She was at first upset I would just show up for the test, then stunned the next day when I received my score. I walked out and withdrew right then and there. The world has been my school and it's been a lot of fun.

To get my first website launched back in March, it took me probably 50 screenshots to Claude. I just refused to give up. I'm a service tech, I'm used to trying things until they work. When failing has almost no cost, you can keep trying until you stumble upon the way. Getting everything set up on Cloudflare, Railway, Resend, GitHub, and my local repo was a challenge. But after seven hours, my site was live. I learned as I went.

I was pushing right to master and fixing issues live. Rolling out feature after feature and being amazed at how it all worked. It was like I was a muggle that fell into Diagon Alley and nobody cared that I was stumbling around seeing how magic worked.

After making an incredibly bloated but feature-rich product that would fall apart at about 1,000 users, I knew it was time to reevaluate. I started a project called "Continuing Education" and had Claude evaluate me. That's when the holy trinity of books entered my life: **The Phoenix Project**, **Thinking in Systems**, and **Designing Data-Intensive Applications**. These books changed me in ways I couldn't have imagined. I never really understood that I loved thinking in systems, it's just how my brain is wired. Having Claude and CC is like adding gasoline to the engine.

The next revelation was the `.md` file. The heart and soul of the project and the thing that can torpedo everything if not done right. A clear, well-thought-out CLAUDE.md is the most important artifact in any CC project. Keeping it updated and as the source of truth is what keeps CC happy and on track. CC loves to make things work. It will do some untraditional things that technically function but aren't right, because you didn't know better. The `.md` file is how you know better.

---

## What I've Built

### Hoover Bookkeeping & Payroll (HBP) — [hooverpayroll.com](https://hooverpayroll.com)
**Status: In production. Live testing and implementation.**

A full QuickBooks replacement for my casino, Red Hills Company (DBA Victorian Casino, Whitefish, MT). This is the showcase.

**What it does:**
- Double-entry general ledger with 72 accounts across 11 categories
- Deposit reports with approval workflow (bookkeeper submits → owner approves → posts to GL)
- AI-powered receipt extraction using Claude's vision API — drag a receipt, get vendor/date/total/account suggestion
- Email ingestion that parses shift reports into structured data (no brittle regex — Claude handles format drift)
- Bank reconciliation with AI-assisted transaction matching and confidence scoring
- Full payroll: federal + Montana state withholding, FICA, FUTA, SUTA, FLSA weighted-average overtime, SIMPLE IRA with employer match
- Time clock with kiosk PIN entry, admin timecards, automatic payroll wizard population
- Paystub PDF generation
- Weekly regulatory monitoring via Claude API
- Month-close anomaly detection

**How it's built:**
- Next.js 15 (App Router, TypeScript), Prisma ORM, PostgreSQL on Railway
- 56 models, 43 enums, 35 migrations
- 15 completed build phases, each with its own design doc
- 8 AI prompt files across 3 Claude model tiers (Haiku for high-volume OCR, Sonnet for statement parsing, Opus for reconciliation)
- Clerk auth, Cloudflare R2 for document storage, Resend for email
- Staging → production promotion via fast-forward merge
- Multi-tenant architecture with Prisma middleware auto-scoping 38 models by businessId

**Multi-tenant is already live.** Two businesses: Victorian Casino and ET Company (Gold Bar + Dirty Boy Laundry, Kalispell MT — my mom's casino with a laundromat attached). A third business is in discussion with my CPA. The $3,000/year QuickBooks subscription that started this journey is about to become a platform.

---

### FLIPNET — [Constitution](https://github.com/mrhoovermt/flipnet-docs/blob/main/CONSTITUTION.md) · [Foundation](https://github.com/mrhoovermt/flipnet-docs/blob/main/FOUNDATION.md)
**Status: Pre-launch. Architecture and governance complete. Building Phase 0.**

Permanent public infrastructure for human communication. Not a startup — there is no launch date. Built to be transferred to a Swiss Foundation (Stiftung) and belong to its community forever.

Every account is a verified human ($5/year, Stripe Identity). No ads, no behavioral manipulation, no algorithmic exploitation, no acquisition, no investors. The codebase is AGPL-3.0, open source from the first commit. The founder draws no profit.

The governance is the product. I wrote a full [Founding Constitution](CONSTITUTION.md) with irrevocable provisions, a compelled-transition trigger that prevents indefinite founder control, and a purpose-locked Swiss Foundation structure. The codebase has the governance scaffolded in from day one — append-only audit logs with cryptographic chain hashing, OpenTimestamps anchoring, a `governance_decisions` table, and feature predicates that enforce constitutional provisions at runtime.

**Stack:** React 18 + Vite, Fastify, Drizzle ORM, PostgreSQL on Neon, Better Auth, Upstash Redis, Cloudflare R2, Railway. Full stack definition with an explicit banned-technology list and mandatory architecture patterns (idempotency keys on every write endpoint, Postgres outbox pattern, transport-swappable real-time).

I am the Founding Chair of FLIPNET LLC (Oregon Registry #255242399, USPTO Serial #99725384).

---

### TitanListing — [titanlisting.com](https://titanlisting.com)
**Status: Postponed. Feature-complete marketplace.**

A business listing platform with buyer/seller/lender portals, document vaults with watermarking and NDA workflows, Stripe Identity verification for buyers, magic-link authentication, geo-filtered lender matching, and a superuser operations dashboard. Node.js/Express, PostgreSQL, Railway.

---

### Stringer
**Status: Active development. Ingest pipeline running, pushing to pressrun.news**

A self-hosted content intelligence pipeline that pulls from Bluesky (Jetstream firehose), Reddit, Hacker News, RSS, and enriches via Claude for content creation. TypeScript, Fastify 5, SQLite via Node.js built-in `node:sqlite`, Claude Haiku. Includes an eval harness for prompt quality testing.

---

### Timetrace
**Status: Planning complete. Ready for scaffold.**

A passive time tracker that reconstructs project hours from Claude Code session logs. No timers, no popups — it reads `~/.claude/projects/` and attributes time per-turn with rule-based matching and optional API-assisted attribution for ambiguous sessions. Privacy-first with hard security rules preventing raw log content from ever reaching an external API.

---

## How I Use Claude Code

I don't use Claude Code like a code generator. I use it like a senior engineering partner on a team where I'm the product owner and domain expert.

Every project gets a `CLAUDE.md` that serves as the operating guide. It defines the working style, the stack, the pause-and-flag protocol for risky actions, the branching strategy, and the project's source of truth hierarchy. My HBP project has companion docs: `ARCHITECTURE.md` for the technical blueprint, `CONTEXT.md` as the living session handoff, and individual phase documents for each build stage.

My settings tell Claude to "push back once and firmly if I'm going down the wrong road or there is a better way to do something." This has been the single most valuable learning accelerator. Instead of just doing what I ask, Claude says, "that's a great idea, but there is a better way to do it" — usually some open-source library or database pattern I didn't know existed. Being humble enough to listen is how you learn.

I've run full audit campaigns using CC's extended thinking to systematically find and fix security gaps across 80+ files. I manage session continuity through CONTEXT.md so every new session picks up exactly where the last one left off. I use tiered AI model selection within my apps — Haiku for high-volume/low-latency, Sonnet for mid-complexity, Opus for the hard stuff.

The `.md` file isn't documentation. It's the contract between you and the model. Get it right and CC will build you an enterprise application. Get it wrong and you'll spend your time fighting drift.

---

## The Books That Changed Everything

If you're reading this and you want to do what I'm doing, read these three books:

1. **The Phoenix Project** — taught me that software development is a system, not a series of tasks
2. **Thinking in Systems** — gave me the language for how my brain already worked
3. **Designing Data-Intensive Applications** — taught me to think about data the way engineers think about data

I didn't go to school for this. These books, Claude, and stubbornness got me here.

---

## What I Want

I don't need this job. I want this job.

I want to help other people do what I did. The technology exists right now for someone with domain expertise and determination to build production software without a CS degree. I'm living proof. My casino runs on software I built. My mom wants her own version. My CPA is interested in replacing a $12,000/year product.

If this works out with Anthropic, I want to be the person who helps enterprise customers and startup founders understand what's actually possible — not by reciting feature lists, but by showing them what I built and teaching them how to do it themselves. I want to see their business and where Anthropic could help.

If it doesn't work out, I'm going to start pushing on social media and help as many people as I can utilize this technology. Either way, the mission is the same.

The biggest thing is be humble. Admit what you don't know. Let it help you. It's a team.

---

## The Moment I Knew

I was in the car heading to a Facebook Marketplace meetup to pick up RAM for a Linux server build.  I had taken an old i3 PC, added 32 GB of RAM and a 3060 with 12GB VRAM, and was setting it up to run local models for a side project. Claude had helped me figure out the build and set up install scripts.

I turned to my wife and said, "You do realize that we are currently driving to pick up RAM because my AI convinced me this is a good idea and I should do it."

It was a surreal realization. What a time to be alive.

---

*Built with Claude, written by me. Obviously.*

**GitHub:** [mrhoovermt](https://github.com/mrhoovermt)
