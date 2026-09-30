# Exec Skills

A collection of Claude Skills for executive project management and communication. Right now it has two email skills (one for drafting new emails, one for reviewing drafts), a skill for capturing meetings, and the design for a team leadership tool. More may be added later.

## What's a skill?

A skill is a small folder with a set of written instructions inside it (a file called `SKILL.md`) that teaches Claude how to do a specific kind of task the way we actually want it done, not just the generic default way. Once a skill is added to someone's Claude setup, Claude reads it automatically whenever it's relevant, so there's no need to re-explain the approach every time.

Each skill lives in its own folder in this repo, and every skill's main file is named `SKILL.md`. The folder name is what tells skills apart. To use one, copy that folder into wherever your own Claude setup reads skills from (see "Using a skill" below).

## What's in this repo

| Skill | Use it when | What it does |
|---|---|---|
| `email-draft/` | You need to draft a **new** email | Drafts it from scratch for you to review |
| `email-review/` | You've **already written** a draft | Marks it up with suggestions, never rewrites it |
| `meeting-notes-capture/` | A meeting had **no AI note-taker** | Turns your notes or transcript into a clear record of requests, decisions, dates, and next steps |

None of these skills sends, publishes, or saves anything without your approval. You stay in control of what goes out.

**Designs in progress** (not working skills yet):

| Folder | What it will be |
|---|---|
| `team-radar/` | A tool for leaders of delivery teams: tracks every request, spots late work and silence early, drafts follow-ups, and gives the leader one page of what needs them. See `DESIGN.md`. |

### email-draft/

Drafts new emails from scratch. It will not send or publish anything. It uses executive communication right practices to draft an email for you to review.

It starts by asking why you're sending the email, since that shapes both the subject line and the opening ask. It pulls facts from anything you upload (a meeting transcript, JIRA tickets, a prior thread) and asks only for what's still missing: who it's to, the outcome you want, any deadlines, and who to cc. It matches your voice using your my-writing-style profile, or offers to build one from a few of your own emails (see "Your writing voice" below).

After your signature, it adds a closing line: *"Content drafted by AI for efficiency, quality checked by me."* This is there for full transparency. Keep or discard it at your discretion.

### email-review/

Reviews any email draft, a new one or a reply, and marks it up with numbered suggestions, similar to how the old "Just Not Sorry" plugin used to underline self-undermining phrases like "I'm sorry but" or "just" and explain what to say instead. It never silently rewrites the email: the original stays intact, each flagged spot gets an explanation and a suggested alternative, and the author decides what to accept.

It flags hedging language, jargon, unnecessary wordiness, a buried main point, and weak scannability. Every review ends with a clean version showing what the email would look like if every suggestion were accepted, so it's easy to see the whole picture, but that combined version always comes after the marked-up original, never in place of it.

### meeting-notes-capture/

Captures what mattered in a meeting that had no AI note-taker: a client's own video call, a phone call, or a hallway conversation. Share whatever you have: a transcript, rough notes, the call's chat, or a few sentences from memory. It shows you what it's listening for (who was there, requests, who is waiting on whom, next steps, dates, promises, decisions, changes, risks, anything for the leader, anything private). If you have nothing written down, that same list works as a guide for what to write.

It pulls out the key points, asks only about what's missing or unclear, and shows you the record to approve, with what needs action first. Then it gives you two ready-to-paste versions: facts only for the ticket in your task tracker, and the full record, including private notes, for your team wiki. It never invents names, dates, or promises. Tip: block 10 minutes after meetings with no note-taker and use it while details are fresh.

### team-radar/ (design)

The design for a team leadership tool, for agencies, consulting firms, and in-house delivery teams. It tracks every request from the day it's made, sends reminders and escalates to the leader on a schedule, replaces manual status updates with a short daily summary each person approves, and gives the leader one page, with Gantt timelines, showing only what needs them. It uses email-draft for follow-ups and meeting-notes-capture for meetings with no note-taker. Read `team-radar/DESIGN.md` for the full design.

## The frameworks behind the email skills

The email skills are built on two real frameworks, not a one-off style preference:

- **Alignment and Attunement**, from Kelly's Executive Communications training (Margaret Keys' framework, which Kelly has taught for years). Alignment is about the message itself: right content, right room, right time, no buried surprises. Attunement is about the audience: bringing your own authority while genuinely meeting the reader where they are, not talking down to them and not going over their head either.
- **PULSE's "Anatomy of an Action-Based Email"** (DoubleGemini, Prasanth Nair), an 8-step structure covering tone, specific recipients, an action-oriented subject line, an up-front "Launch" (the one thing the reader most needs to know, stated before the background, in italics), scannable formatting, and a sign-off matched to the situation.

The specific instructions in the email skills are applications of those two frameworks, drawn from the same training Kelly already gives on executive communication and email etiquette. Examples: deciding whether an email is an Action Ask or an Action Taken before writing the subject line, writing the Launch last but placing it first, when to keep versus change a subject line on a reply, and when a technical term should get its own clearly labeled line instead of being cut.

## Your writing voice

email-draft works best when it knows how you write. The first time you use it, it asks for two or three emails you've written yourself, then offers to save a short profile of your voice as your own personal skill called **my-writing-style**. After that, it uses your profile and doesn't ask again.

Your voice profile is yours: it lives in your own Claude setup, not in this repo. That way, updating these shared skills never overwrites anyone's voice, and nobody's personal profile ends up here by accident.

## Using a skill

1. Download or copy the skill's folder (for example, `email-draft`) from this repo. Copy the whole folder, not only the `SKILL.md` file inside it.
2. Place that folder where your Claude setup reads skills from. In Claude Code, that's typically a `.claude/skills/` folder, either inside a specific project or in your home directory if you want it available everywhere. In the Claude apps, add it through your skills settings.
3. That's it. Claude picks it up automatically and uses it when a task matches what the skill describes. You don't need to invoke it by name.

The two email skills work well together: draft with email-draft, then run email-review on your edited version before sending.

## Adding a new skill

Create a new folder in this repo named after the skill, with a `SKILL.md` file inside describing what it should do and when Claude should use it. Keep it in plain language, and explain the reasoning behind each instruction rather than just listing rules. That's what makes a skill generalize well instead of only working for the one example it was built from.

Keep new additions in the executive project management and communication space, including writing, reviewing, or preparing for high-stakes conversations, so the repo stays focused rather than becoming a catch-all.
