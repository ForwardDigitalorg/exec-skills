---
name: email-draft
description: Draft a brand-new email from scratch using PULSE's "Anatomy of an Action-Based Email" and Margaret Keys' Alignment and Attunement framework. Starts by asking why the email is being sent, pulls facts from any context the author uploads (meeting transcripts, JIRA tickets, email threads, docs), asks only for what's still missing (recipient, desired outcome, deadline, cc's), matches the author's own voice from their my-writing-style profile (or builds one from writing samples), and returns a ready-to-send draft with an action subject line and an italicized Launch. Use whenever someone asks to write, draft, or compose a new email, or to turn notes, a transcript, or a ticket into an email. To review a draft the author already wrote, use email-review instead.
---

# Email Draft

This skill drafts new emails. Its sister skill, **email-review**, marks up
emails someone has already written. Both use the same two frameworks:

- **Alignment and Attunement** (Margaret Keys, Executive Communications).
  Alignment is the message: right content, right room, right time, no buried
  surprises. Attunement is the reader: the writer brings their own authority
  while meeting the reader where they are, without talking down to them or
  going over their head.
- **PULSE's "Anatomy of an Action-Based Email"** (DoubleGemini, Prasanth
  Nair): tone, specific recipients, an action subject, a friendly greeting,
  an up-front action (the **Launch**), scannable content, a sign-off matched
  to context, and a timely send.

## Step 1: Ask for the goal first

Before anything else, ask: **"Why are you sending this email? What do you
need to happen after they read it?"**

This is the most important question in the skill. The answer becomes both
the subject line and the Launch, so nothing else can be written well until
it's clear. If the author's answer is vague ("just to update them"), help
them sharpen it: "If they read only one sentence, what should it be?"

Then decide whether the email is an **Action Ask** (the reader needs to do,
decide, or reply to something) or an **Action Taken** (informing them,
nothing needed back). When in doubt: does the reader need to do anything
after reading? If yes, it's an Ask. Emails that are really asks but are
worded like updates are the most common way a request gets ignored.

## Step 2: Gather context before asking more questions

Invite the author to upload or paste anything relevant: a meeting
transcript, JIRA tickets, the prior email thread, a doc, their own rough
notes. Pull out the facts: what was asked, by whom, on what date, what was
agreed, what's still open.

Then ask **only what's still missing** from this list, in one short batch
rather than one question at a time. Skip anything the context already
answers.

- **Who is it to?** Name, role, and their relationship to the author. This
  drives Attunement: how technical to be, how warm, how much background.
- **What's the desired outcome?** What does "done" look like after they act?
- **Is there a deadline?** By when, and what's driving that date? A deadline
  with a reason gets met more often than a bare date.
- **Should anyone be cc'd?** For each person, ask why. PULSE's "specific
  recipients" step: everyone on the email should have a reason to be there.
- **Email addresses.** Ask only if the author wants a draft created directly
  in their email tool. Names are enough for a draft they'll paste.
- **Tone.** Don't ask if the author has a voice profile (see below).

## The author's voice

Every draft should sound like the author, not like AI. Voice lives in a
separate, personal skill called **my-writing-style**, not in this one. This
skill is shared by many people; each person's voice is theirs alone, and
keeping it separate means updating this skill never overwrites anyone's
voice.

- **If a my-writing-style skill is available,** follow it. Don't ask for
  samples.
- **If not,** ask once for two or three emails the author wrote themselves.
  Draft from them, then offer to build their voice profile: a short
  description of how they write (greeting and sign-off habits, sentence
  length, formality, how they phrase asks, words they use and avoid), with
  one or two short excerpts as examples. Save it as the author's own
  my-writing-style skill, using whatever this Claude environment offers for
  saving a personal skill. If saving isn't possible here, give them the file
  to add themselves.
- **If they have no samples,** write in a plain, warm, direct voice and say
  so.
- **When the author edits a draft's tone,** offer to add what changed to
  their my-writing-style profile, so the next draft starts closer.

## Step 3: Draft using the PULSE structure

- **Subject line.** Action-oriented, so the reader knows what's needed before
  opening. Action Ask: `Request: [topic]`, `Decision Needed: [topic]`,
  `Feedback Requested: [topic]`. Action Taken: `Update: [topic]`,
  `FYI: [topic]`.
- **Greeting.** Friendly and matched to the relationship.
- **The Launch.** The single most important sentence, first, in its own
  sentence or short paragraph, in *italics*. Write it last, place it first:
  draft the body, then write the one line that says what you need, then move
  it to the top. Clear and warm are not in tension. Write the ask the way the
  author would say it out loud to this person, not as an instruction manual.
- **Body.** Scannable: bullets for lists and options, bold lead-ins where a
  skimming reader needs to find their part, one job per paragraph. Include
  dates, owners, and what's blocked. Link to relevant work, but only to
  things the recipient can actually open.
- **Sign-off.** Matched to the context and the relationship.
- **Timing.** If it matters (time zones, end of week, before a meeting),
  suggest when to send.

## Step 4: Check the draft before showing it

Run the email-review checklist on your own draft and fix what you find:
hedging ("just," "I think," "does that make sense?"), unexplained jargon,
throat-clearing ("I wanted to reach out..."), a buried Launch, dense
paragraphs, and any standing point at risk of getting lost. The review
skill's no-silent-rewrite rule protects the author's words, not yours, so
fix your own draft directly.

Then check both frameworks one last time:

- **Alignment:** is anything in here a surprise the reader shouldn't get by
  email? Is this the right room and the right time?
- **Attunement:** does it match what this reader needs, in their language,
  at their level?

## Step 5: Present the draft

1. Two or three subject line options, recommended one first.
2. **To** and **Cc**, with a one-line reason for each cc.
3. The full draft, from greeting through sign-off.
4. After the signature, this line:
   *Content drafted by AI for efficiency, quality checked by me.*
   It's there for transparency. Include it by default; the author keeps or
   deletes it at their discretion.
5. **Assumptions to check:** a short list of anything you inferred rather
   than read in the context or heard from the author. Skip it if there are
   none.

## Never

- **Send or publish anything.** This skill drafts only. Even when a draft is
  created in the author's email tool, it stays a draft; the author reviews
  and sends it themselves.
- **Invent facts.** No made-up dates, names, numbers, or commitments. Use a
  visible placeholder like `[date?]` and list it under assumptions.
- **Use filler openers.** No "Hope this finds you well" or "Just following
  up." A follow-up states what's new: the date of the original ask and what
  the delay now affects.
- **Pad it.** If it's running past about 200 words, check whether it's
  really two emails.
