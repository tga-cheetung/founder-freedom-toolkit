# Founder Freedom Toolkit

**5 AI skills that help B2B founders stop being the bottleneck.**

Built by [The GTM Architects](https://www.thegtmarchitects.com) — turning founder-led sales into a GTM system you can scale and hand off.

---

## The Problem

You're a B2B founder past product-market fit. $500K–$5M ARR. Paying customers. Proof it works. But *you* are the ceiling.

You're the sales process, the follow-up system, the onboarding, and the closer. Every deal runs through you because nothing is written down anywhere else. You've thought about hiring — but the last time you tried, it didn't work out. The playbook only exists in your head, which means every new hire starts from zero, every week without you in the seat costs pipeline, and growth is capped at your personal bandwidth.

This isn't a product problem. It's a founder-dependency problem.

The Founder Freedom Toolkit is five tools that attack the root causes — one at a time.

---

## The 5 Skills

| # | Skill | The Job It Does |
|---|---|---|
| 1 | **Founder Freedom Finder** | Diagnose where your GTM is leaking and why you can't scale |
| 2 | **Sales Process Extractor** | Extract your sales process from your head into a one-pager + SOP gaps |
| 3 | **Founder GTM Time Map** | Map where your GTM hours go and what each one costs in real dollars |
| 4 | **First Hire Readiness Scorecard** | Decide if you're ready to hire, what to hire, and what to build first |
| 5 | **Proposal & Follow-Up Template Kit** | Build a proposal template, follow-up sequence, and objection cheat sheet |

---

## The System Logic

These tools follow a specific sequence — each one builds on the last:

1. **Diagnose** — Know exactly which dimensions of your GTM are broken and why. Score your situation across 6 dimensions in 8 minutes.
2. **Extract** — Get your sales process out of your head and onto a page. You can't systematize what isn't written down.
3. **Map the cost** — See exactly where your time goes and what each hour of the wrong work costs you. Dollar-denominated.
4. **Decide on hiring** — Armed with your process audit and time map, know whether you're ready to hire, what to hire, and what needs to exist before the hire walks in the door.
5. **Build the templates** — Proposals that take 20 minutes instead of 3 hours. Follow-up sequences that run without you. Objection responses that close.

**The arc: Diagnose → Document → Quantify → Decide → Execute.**

Each skill is a standalone win. Together they move you from "everything runs through me" to "I have a system worth handing off."

---

## Repository Structure

This repo is formatted as a **Claude Code skills folder**. Each skill lives in its own directory with a `SKILL.md` file:

```
founder-freedom-toolkit/
├── README.md
├── founder-freedom-finder/
│   └── SKILL.md
├── sales-process-extractor/
│   └── SKILL.md
├── founder-gtm-time-map/
│   └── SKILL.md
├── first-hire-readiness-scorecard/
│   └── SKILL.md
└── proposal-follow-up-template-kit/
    └── SKILL.md
```

Each `SKILL.md` contains YAML frontmatter (`name`, `description`) followed by the full skill prompt.

---

## Installation

### Claude Code *(recommended — slash command support)*

Skills become `/slash-commands` — the fastest way to invoke them.

**Option 1: Symlink the entire repo as your global skills folder**

```bash
git clone https://github.com/tga-cheetung/founder-freedom-toolkit.git
ln -s "$(pwd)/founder-freedom-toolkit" ~/.claude/skills
```

All 5 skills are now available in every Claude Code session.

**Option 2: Copy all skills globally**

```bash
git clone https://github.com/tga-cheetung/founder-freedom-toolkit.git
cp -r founder-freedom-toolkit/*/ ~/.claude/skills/
```

**Option 3: Install a single skill**

```bash
cp -r founder-freedom-toolkit/sales-process-extractor ~/.claude/skills/
```

**Option 4: Install into a specific project**

```bash
mkdir -p /path/to/your-project/.claude/skills
cp -r founder-freedom-toolkit/proposal-follow-up-template-kit /path/to/your-project/.claude/skills/
```

**Invoke with:**

```
/founder-freedom-finder
/sales-process-extractor
/founder-gtm-time-map
/first-hire-readiness-scorecard
/proposal-follow-up-template-kit
```

---

### In Web & Chat Interfaces

Each `SKILL.md` file works as a standalone system prompt. Open the skill file, copy the contents (everything below the YAML frontmatter `---` block), and paste it into your tool of choice.

#### Claude.ai

**Permanent setup (Projects — recommended):**
1. Go to [claude.ai](https://claude.ai) → **Projects** → **New Project**
2. Name it after the skill (e.g. "Sales Process Extractor")
3. Click **Set project instructions** → paste the full contents of the `SKILL.md` file
4. Every conversation in that project now runs the skill automatically

> Tip: Create one project per skill, or combine the full toolkit into a single "Founder Freedom Toolkit" project by pasting all five files end-to-end.

**One-off use:**
1. Start a new conversation
2. Paste the full file contents as your first message
3. The skill is active for that conversation only

---

#### ChatGPT

**Permanent setup (Custom GPTs):**
1. Go to [chatgpt.com](https://chatgpt.com) → **Explore GPTs** → **Create**
2. Switch to **Configure** tab
3. Paste the full `SKILL.md` file contents into the **Instructions** field
4. Save as a private GPT → accessible from your GPT list anytime

**One-off use:**
1. Start a new chat
2. Paste the full file contents as your first message
3. Active for that conversation only

---

#### Google Gemini

**Permanent setup (Gems):**
1. Go to [gemini.google.com](https://gemini.google.com) → **Gems** → **New Gem**
2. Paste the full `SKILL.md` file contents into the instructions field
3. Save → accessible from your Gems list

**One-off use:**
1. Start a new conversation
2. Paste the full file contents as your first message

---

#### Perplexity, Copilot Chat, and other web LLMs

No persistent system prompt support in most interfaces. Paste the full file contents as your opening message. The skill is active for that conversation.

---

### In AI Coding Editors

#### Cursor

**Project-level rules (`.cursor/rules/`):**

```bash
mkdir -p .cursor/rules
cp sales-process-extractor/SKILL.md .cursor/rules/sales-process-extractor.mdc
```

Add a front-matter block at the top to control when it activates:

```
---
alwaysApply: false
description: "Extract sales process into documented one-pager"
---
```

**Global rules:** Go to **Cursor Settings → Rules for AI** → paste the skill content.

---

#### Windsurf

**Project-level rules:**

```bash
cp founder-freedom-finder/SKILL.md .windsurfrules
```

Or append multiple skills:

```bash
cat founder-freedom-finder/SKILL.md sales-process-extractor/SKILL.md >> .windsurfrules
```

**Global rules:** Go to **Windsurf Settings → AI → Global Rules** → paste the skill content.

---

#### GitHub Copilot (VS Code / JetBrains)

```bash
cp founder-freedom-finder/SKILL.md .github/copilot-instructions.md
```

---

#### Aider

```bash
aider --read sales-process-extractor/SKILL.md
# or
aider --system-prompt "$(cat founder-freedom-finder/SKILL.md)"
```

---

### Quick Reference

| Tool | Method | Persistent? |
|---|---|---|
| Claude Code | Symlink or copy to `~/.claude/skills/` | Global |
| Claude Code | Copy to `.claude/skills/` in project | Per project |
| Claude.ai | Project Instructions | Per project |
| ChatGPT | Custom GPT | Saved GPT |
| Gemini | Gems | Saved Gem |
| Perplexity / other | Paste as first message | Per chat |
| Cursor | `.cursor/rules/skill.mdc` | Per project |
| Windsurf | `.windsurfrules` | Per project |
| GitHub Copilot | `.github/copilot-instructions.md` | Per repo |
| Aider | `--read skill/SKILL.md` | Per session |

---

## What Each Skill Does

### `founder-freedom-finder`

A 10-question conversational diagnostic across 6 GTM dimensions: founder dependency, pipeline visibility, follow-up systems, proof assets, documented process, and delegation readiness.

Outputs a **Founder Freedom Score (0–30)**, identifies your pattern ("I am the system," "Ready to hire, nothing to hand over," etc.), names the #1 root bottleneck, and gives one first move completable this week.

**Use when:** "Why can't I scale?" / "I'm the bottleneck but don't know where to start" / "What should I fix first?"

---

### `sales-process-extractor`

A guided conversation that pulls your sales process out of your head — not how you think you sell, how you actually sell — and turns it into a structured one-page process map.

Outputs: your **Sales Process Map** (stage-by-stage, in your own language), an **SOP Gap Analysis** (what's documented vs. in your head vs. ad hoc), and your **Top 3 SOPs to Build First** with a starter outline for each.

**Use when:** "It's all in my head" / "I couldn't hand my sales process to someone else" / "I need to document how we sell before I hire."

---

### `founder-gtm-time-map`

A conversation where you estimate your weekly GTM time across activities. Even rough numbers are enough — founders have never quantified this, and even rough numbers are revealing.

Outputs: a **Time Map** (each activity tagged 🟢 founder-essential / 🟡 systematizable / 🔴 should already be delegated), a **Dollar Map** (implied hourly rate, cost of each activity, total "trapped revenue"), and a **Delegation Roadmap** (ranked by hours freed, ease of systematization, and risk of delegation).

**Use when:** "I can't get out of the weeds" / "Everything runs through me" / "I don't know what to delegate first."

---

### `first-hire-readiness-scorecard`

A structured assessment across 5 dimensions: process readiness, pipeline predictability, economics, founder bandwidth, and role clarity. Includes the math on what a hire actually costs over 6 months.

Outputs: a **Verdict** (🟢 Ready / 🟡 Almost / 🔴 Not Yet) with specific reasoning, a **Role Recommendation** (title, seniority, comp range, archetype, specific activities, 90-day success metrics), and a **Pre-Hire Checklist** with priority build order and timeline.

**Use when:** "Should I hire a sales rep?" / "My last hire didn't work out" / "I don't know if I should hire marketing or sales first."

---

### `proposal-follow-up-template-kit`

A 10-minute conversation that extracts your product, deal structure, buyer, objections, and best proof point. Then produces four ready-to-use artifacts in your voice.

Outputs:
- **Proposal Template** — one-page, price visible, buyer's language, takes 20 min to customize per deal
- **Post-Demo Follow-Up Sequence** — 3 emails (same day, 3 days, 7 days), each under 100 words
- **Gone-Dark Re-Engagement Sequence** — 3 emails for cold deals (check-in, new angle, breakup)
- **Objection Handling Cheat Sheet** — top 3-5 objections with what they mean + example responses in your language

**Use when:** "Proposals take forever" / "Deals go cold because I can't follow up fast enough" / "I lose deals to silence, not to competitors."

---

## About

The GTM Architects turn founder-led sales into a GTM OS you can scale and hand off. We work with B2B founders at $500K–$5M ARR — past PMF, not yet at scale — who are the ceiling of their own growth because everything runs through them.

The toolkit is the free layer.

The paid layer is an **Extract + Systematize** engagement — we extract your sales process, systematize it into a full GTM OS (playbook, pipeline, attribution, onboarding), and hand it off so your first hire inherits a system instead of a prayer.

The average time to complete: 30 days. The average founder hours reclaimed: 15–20 hours/week.

**[→ Book a funnel mapping call](https://tidycal.com/cheetung/discovery)** — I'll bring 30 minutes of research on your business before we talk.

---

## License

MIT. Use freely, fork it, adapt it. If you improve a skill, consider opening a PR.
