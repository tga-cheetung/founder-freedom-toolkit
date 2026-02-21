# Founder Freedom Toolkit

**5 AI skills that give B2B founders 10 hours back every week.**

Built by [The GTM Architects](https://www.thegtmarchitects.com) — building AI-powered growth systems for scaling B2B companies.

---

## The Problem

You're a B2B founder past product-market fit. Product sells. Referrals close. You have paying customers and proof it works. But *you* are the bottleneck.

You're the sales team, the marketing brain, and the strategy department. Every deal, every campaign, every follow-up runs through you. The playbook only exists in your head — which means every new hire starts from zero, every week without you in the seat costs pipeline, and growth is capped at whatever your personal bandwidth allows.

Revenue growth isn't a product problem. It's a founder-dependency problem.

The Founder Freedom Toolkit attacks the 5 biggest GTM time drains keeping you stuck in the operator seat.

---

## The 5 Skills

| # | Skill | Time Drain It Kills | Est. Hours Saved/Week |
|---|---|---|---|
| 1 | **Founder Freedom Finder** | Trying to figure out what's actually broken in your GTM | ~1.5 hrs |
| 2 | **AI Sales Coach** | Reviewing calls, coaching yourself, second-guessing your pitch | ~2 hrs |
| 3 | **Cold Email Roast** | Rewriting outbound, guessing why replies dried up | ~2 hrs |
| 4 | **Content Engine** | Creating content from scratch — one topic should be a week of posts | ~3 hrs |
| 5 | **Landing Page CRO** | Staring at analytics wondering why traffic isn't converting | ~2 hrs |

**Total: ~10.5 hours per week redirected from guessing to building.**

---

## The System Logic

These aren't random tools. They follow a specific sequence:

1. **Find the bottleneck** — Stop guessing. Score your GTM across 6 dimensions. Know your #1 blocker in 8 minutes.
2. **Fix your pitch** — Your sales conversations are your highest-leverage activity. Make every one count.
3. **Fix your outbound** — You're sending emails that don't work. Find out why and get rewrites that do.
4. **Build your authority** — Turn one topic into a blog post + 6 LinkedIn posts. One idea = one week of content.
5. **Fix your funnel** — You're paying for traffic. Make sure your page converts it.

**The arc: Diagnose → Improve conversations → Improve outbound → Build authority → Convert traffic.**

Each skill is a standalone win. Together they take GTM diagnosis and optimization off your plate.

---

## Repository Structure

This repo is formatted as a **Claude Code skills folder**. Each skill lives in its own directory with a `SKILL.md` file:

```
founder-freedom-toolkit/
├── README.md
├── founder-freedom-finder/
│   └── SKILL.md
├── ai-sales-coach/
│   └── SKILL.md
├── cold-email-roast/
│   └── SKILL.md
├── content-engine/
│   └── SKILL.md
└── landing-page-cro/
    └── SKILL.md
```

Each `SKILL.md` contains YAML frontmatter (`name`, `description`, optional `argument-hint`) followed by the full skill prompt.

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
cp -r founder-freedom-toolkit/cold-email-roast ~/.claude/skills/
```

**Option 4: Install into a specific project**

```bash
mkdir -p /path/to/your-project/.claude/skills
cp -r founder-freedom-toolkit/cold-email-roast /path/to/your-project/.claude/skills/
```

**Invoke with:**

```
/founder-freedom-finder
/ai-sales-coach
/cold-email-roast
/content-engine "[topic] for [audience]"
/landing-page-cro
```

---

### In Web & Chat Interfaces

Each `SKILL.md` file works as a standalone system prompt. Open the skill file, copy the contents (everything below the YAML frontmatter `---` block), and paste it into your tool of choice.

#### Claude.ai

**Permanent setup (Projects — recommended):**
1. Go to [claude.ai](https://claude.ai) → **Projects** → **New Project**
2. Name it after the skill (e.g. "Cold Email Roast")
3. Click **Set project instructions** → paste the full contents of the `SKILL.md` file
4. Every conversation in that project now runs the skill automatically

> Tip: Create one project per skill, or combine all 5 into a single "Founder Freedom Toolkit" project by pasting all the files end-to-end.

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

> Note: ChatGPT also supports persistent custom instructions under **Settings → Personalization → Custom Instructions**, but this applies to all chats — better to use a Custom GPT for skill-specific behavior.

---

#### Google Gemini

**Permanent setup (Gems):**
1. Go to [gemini.google.com](https://gemini.google.com) → **Gems** → **New Gem** (or **Gem Manager**)
2. Paste the full `SKILL.md` file contents into the instructions field
3. Save → accessible from your Gems list

**One-off use:**
1. Start a new conversation
2. Paste the full file contents as your first message

---

#### Perplexity, Copilot Chat, and other web LLMs

No persistent system prompt support in most of these interfaces. Paste the full file contents as your opening message. The skill is active for that conversation.

---

### In AI Coding Editors

#### Cursor

**Project-level rules (`.cursor/rules/`):**

```bash
mkdir -p .cursor/rules
cp cold-email-roast/SKILL.md .cursor/rules/cold-email-roast.mdc
```

Cursor will pick up `.mdc` files from `.cursor/rules/` automatically. Add a front-matter block at the top of the file to control when it activates:

```
---
alwaysApply: false
description: "Roast and rewrite cold emails"
---
```

**Global rules (applies to all projects):**
Go to **Cursor Settings → Rules for AI** → paste the skill content.

---

#### Windsurf

**Project-level rules:**

```bash
cp cold-email-roast/SKILL.md .windsurfrules
```

Or for multiple skills, append them:

```bash
cat founder-freedom-finder/SKILL.md cold-email-roast/SKILL.md >> .windsurfrules
```

**Global rules:**
Go to **Windsurf Settings → AI → Global Rules** → paste the skill content.

---

#### GitHub Copilot (VS Code / JetBrains)

Create a `.github/copilot-instructions.md` file in your repo root:

```bash
cp cold-email-roast/SKILL.md .github/copilot-instructions.md
```

Copilot will use these instructions for all interactions in that repository.

---

#### Aider

Pass the skill file as additional context at startup:

```bash
aider --read cold-email-roast/SKILL.md
```

Or set it as the system prompt:

```bash
aider --system-prompt "$(cat cold-email-roast/SKILL.md)"
```

---

#### Continue.dev

Add to your `~/.continue/config.json` under `systemMessage`:

```json
{
  "models": [...],
  "systemMessage": "<paste skill content here>"
}
```

Or reference the file directly if your Continue config supports file includes.

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
| Continue.dev | `config.json` systemMessage | Global |

---

## What Each Skill Does

### `founder-freedom-finder`

A 10-question conversational diagnostic across 6 GTM dimensions: founder dependency, pipeline visibility, follow-up systems, proof assets, conversion infrastructure, and outbound engine.

Outputs a **Founder Freedom Score (0–30)**, identifies your #1 root bottleneck, and gives one first move that's completable this week.

**Use when:** "Why can't I scale?" / "Where's my GTM broken?" / "I feel like I'm the bottleneck but I don't know where to start."

---

### `ai-sales-coach`

Three modes detected automatically from your opening message:

- **Mode A: Post-Call Debrief** — Paste a transcript and get a scored call debrief (25-point scorecard across 5 dimensions), 3 flagged moments with exact rewrites in your voice, one recurring pattern, and one homework assignment for the next call.
- **Mode B: Deal Autopsy** — Describe a lost deal and get the stage of death, the turning point, 2 moves that would have changed it, and dollar impact where quantifiable.
- **Mode C: Objection Drill** — Ask how to handle a specific objection and get a 3-round live drill with 3 response options: direct, reframe, and question-back.

**Use when:** You just got off a call / a deal went dark / you keep getting the same objection and don't know what to say.

---

### `cold-email-roast`

Scans for Dirty Dozen violations (the phrases that signal mass template before the prospect reads a word), then roasts in reading order: subject line → opener → body → CTA.

Outputs a **Roast Score** with Dirty Dozen hit count, word count, subject/opener/CTA pass-fail, and reply rate estimate. Delivers a full rewrite under 80 words using one of 4 valid CTA types.

**Use when:** Replies have dried up / you want feedback before sending a new sequence / you're reviewing an existing campaign that isn't performing.

---

### `content-engine`

Takes a topic, audience, and one-line take. Runs a 3-gate workflow — you approve each stage before the next begins:

1. **Gate 1:** 3 angle options → you pick one
2. **Gate 2:** Full 1,200–1,500 word blog post → you review and edit
3. **Gate 3:** 6 LinkedIn posts in Justin Welsh style (teaser, announcement, framework, contrarian, case study, story)

No external tools, no APIs, no stack dependencies. Works in claude.ai, Claude Code, or any LLM.

**Use when:** "Write me a blog post about [topic]" / "I need content for this week" / "Turn this idea into LinkedIn posts."

---

### `landing-page-cro`

Starts with the 5-second test, then scores 7 dimensions: message match, above-the-fold, headline, CTA, trust signals, objection handling, and friction.

Outputs a **CRO Audit Score (0–35)** with conversion estimate, flags the 3 highest-cost elements with actual rewrites (not suggestions), and names the single highest-leverage fix.

**Use when:** "This page isn't converting" / you're running paid traffic to a page / you want to audit before a launch.

---

## About

The GTM Architects build AI-powered growth systems for B2B founders who have proven product-market fit and are ready to scale past themselves. We work with founder-bottlenecked companies at $500K–$5M ARR — past survival mode, not yet at scale — who need a GTM system built, not just more emails sent.

This toolkit is the free layer.

The paid layer is the **5-day GTM Diagnostic** — stage-by-stage pipeline reconciliation, real attribution by channel, and a cascade model that puts dollar values on every funnel drop-off. The average recoverable ARR we find is between $180K and $400K. Most founders didn't know that number existed before we ran it.

**[→ Book a GTM Diagnostic](https://tidycal.com/cheetung/discovery)**

---

## License

MIT. Use freely, fork it, adapt it. If you improve a skill, consider opening a PR.
