---
name: meeting-notes-capture
description: Turn whatever someone has from a meeting (a transcript, rough typed notes, or just memory) into a clear record of requests, decisions, dates, promises, blockers, and next steps, ready to approve and paste into a task tracker or team wiki. Use whenever someone wants to capture a meeting, call, or conversation that had no AI note-taker, uploads meeting notes or a transcript to summarize, or says something like "I just got off a call with the client." Works on its own, and is also used by team-radar for meetings with no transcript.
---

# Meeting Notes Capture

Meetings are where requests, promises, and decisions happen. When no AI
note-taker was there (a client's own video call, a phone call, a hallway
conversation), those things are easy to lose. This skill helps a person
capture what matters in a few minutes, while it is still fresh.

The person is the source. Claude organizes, and the person approves.

## Step 1: Ask for whatever they have

Start simple. Invite them to share **anything** they have from the meeting:

- a transcript or recording summary
- typed notes, even rough bullets
- a copy of the chat from the call
- or just a few sentences from memory

Tell them what Claude is **listening for**, so they know what is useful:

> Share whatever you have. I'm listening for:
>
> - **Who** was there, and which **project** it was about
> - **Requests:** did they ask us for anything?
> - **Waiting on:** are we waiting on them, or are they waiting on us?
> - **Next steps:** who does what, and by when?
> - **Dates and deadlines** that were mentioned
> - **Promises** anyone made
> - **Decisions** that were made
> - **Changes** to scope, priority, or an earlier decision
> - **Risks or concerns** that came up
> - **Anything the leader should know,** or where they should step in
> - **Anything private,** such as notes about people or internal politics

**If they have nothing written down,** the same list works as a guide. They
can read it and write a few lines in their own words. It is a prompt, not a
form: they do not need to answer every item, only what applies.

## Step 2: Pull out what matters

Read everything they share. Sort it into the items above. Keep their words
where you can.

Then ask **only about what is missing or unclear**, in one short batch.
Most people with notes or a transcript will get 2 or 3 questions, or none.
Good follow-up questions are specific:

- "You mentioned the data file. Who is sending it, and by when?"
- "Was the 15-Oct date agreed, or only suggested?"

Do not ask about items that simply did not come up. Not every meeting has
a decision or a risk.

## Step 3: Show the record for approval

Present the record in this order, with what needs action first and what is
already settled last. Leave out any section that is empty.

1. **For the leader:** anything they need to know or act on
2. **Requests:** what was asked of us, by whom
3. **Waiting on:** who is waiting on whom, for what
4. **Next steps:** who does what, by when
5. **Dates and deadlines**
6. **Promises made**
7. **Changes:** to scope, priority, or earlier decisions
8. **Risks or concerns**
9. **Decisions**
10. **Private notes:** kept separate (see below)

Header each record with the meeting date, who was there, and the project.

Then ask the person to confirm or correct it.

## Step 4: Offer ready-to-paste versions

After the person approves, offer two versions they can copy:

- **For the ticket (task tracker, for example JIRA, GitHub Issues, Asana, or
  Monday.com):** facts only. Requests, next steps with owners and dates,
  deadlines, decisions, and what we are waiting on. No opinions about
  people.
- **For the team wiki (for example Confluence, Notion, or an internal
  wiki):** the full record, including private notes, in a space only the
  team can see.

If the person uses team-radar, the approved record goes straight into it
instead.

## Rules

- **Never invent anything.** No made-up names, dates, or promises. If
  something is unclear, ask, or mark it with a visible placeholder like
  `[date?]`.
- **Private notes stay private.** Opinions about people, internal politics,
  and sensitive context never go in the ticket version. Tickets may be seen
  by more people, sometimes including the client.
- **Plain English.** The person may speak English as a second language, be
  new to the team, or be less familiar with the project. Use short
  sentences and common words. No idioms or jargon.
- **Keep their meaning.** Tidy the wording, but do not change what they
  said. When you are not sure what they meant, ask.
- **Nothing is sent or saved without approval.** This skill drafts only.

## Tip for the person

Block **10 minutes on your calendar** right after meetings with no
note-taker, and use this skill then, while the details are fresh. If you
often have meetings with no note-taker, Claude can suggest adding these
blocks.
