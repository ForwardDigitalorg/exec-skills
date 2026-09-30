---
name: daily-summary
description: End-of-day summary for a team member. The person starts it ("run my daily summary") and can walk away while Claude reads the day's meeting notes, email (inbox and sent), calendar, and task tracker, checks yesterday's open blockers, and drafts a summary with only the missing questions at the top. The person answers, says "good," and Claude posts the approved summary. Also offers a daily reminder around 5 pm local time to start it. Use when someone asks for their daily summary, end-of-day update, or status update, or to set up the daily reminder. Part of team-radar, and useful on its own.
---

# Daily Summary

Most status updates are short headlines written from memory. This skill
writes the update for the person, from what actually happened today. The
person only answers what Claude could not find, and approves it.

**Goal: about 3 minutes of the person's time.** They start it, walk away,
and come back to a draft and a few questions.

## Before the first run: settings and the reminder

On the first run, check what is needed and ask only for what is missing:

1. **Connections:** email, calendar, task tracker (for example JIRA, GitHub
   Issues, Asana, or Monday.com), and team wiki (for example Confluence,
   Notion, or an internal wiki). Test each one ("I can see today's 4
   meetings"). If one is missing, explain how to connect it, or point to
   SETUP.md.
2. **Team settings:** look in the team wiki for a page called **team-radar
   settings**. It says where summaries are posted (the team-agreed
   location), where private notes go, and any team rules. If there is no
   such page, ask the person where to post their summary.
3. **Time zone:** take it from the person's calendar settings. Confirm it.
4. **Offer the daily reminder:** "Would you like a reminder to run this each
   workday, around 5 pm your time?" If yes, create a scheduled task, using
   this Claude environment's scheduling feature, with a push notification,
   on weekdays at about 4:55 pm in their time zone. The reminder only says:
   "Time for your daily summary. Open Claude and say: run my daily
   summary." It does not run the summary itself. If scheduling is not
   available, suggest a repeating calendar reminder instead.

## Step 1: Start with yesterday's open items

Read the person's last few approved summaries at the team-agreed location.
For every open blocker, check the person's **sent email**:

- **If no request was sent** to clear the blocker, put it at the very top:
  "You noted on [date] that you need [thing] from [person]. I don't see a
  request. Here is a draft." Draft it with the **email-draft** skill.
- **If a request was sent** but there is no answer, note how many days it
  has been waiting.

Never say a request was not sent without checking sent email first.

## Step 2: Read today's information

Tell the person: "This takes a few minutes. You can step away. I'll have a
draft and a few questions when you come back."

Then read, for today only:

- **Meeting notes** from the AI note-taker (for example Notion AI, Otter.ai,
  Fireflies, or Zoom AI Companion). Pull out the key points. Link to the
  full notes. Do not copy them.
- **Email,** inbox and sent: requests, replies, promises, delivered work.
- **Calendar:** which meetings happened, and which had no notes.
- **Task tracker:** tickets the person created, moved, commented on, or
  closed today.

Never read direct messages or anyone else's email.

## Step 3: Draft the summary

Match what you found to the open items from Step 1. Suggest a due date for
any request that does not have one, and mark it "suggested."

Use this order: what needs action first, what is settled last. Leave out
empty sections.

1. **Needs a decision:** what, from whom, by when
2. **Waiting on:** who, for what, since when (and how many days)
3. **Dates agreed or changed,** and why
4. **Decided:** what, by whom, and whether it changes an earlier decision
5. **Finished:** with a link to the proof
6. **Private notes:** kept separate, never posted to a ticket

## Step 4: Ask only what is missing

Put the questions **at the top** of the draft, before the summary. Ask only
about gaps or unclear points, in one short list. Be specific: "The client
asked for the Q3 file. Who is sending it, and by when?"

Always add these two questions:

- Did a client ask for anything in a **direct message or a call with no
  note-taker** today?
- For meetings with no notes ([list them]): upload your notes, or confirm
  there is nothing to add. Use the **meeting-notes-capture** skill for
  these.

## Step 5: Revise until "good"

Update the draft with the person's answers and show the new version. Repeat
until they say **"good"** (or "approved," "looks good"). If a reply is
unclear, ask. Do not guess.

## Step 6: Post the approved summary

Only after "good":

- Post the summary to the **team-agreed location**.
- Add the facts to the right **tickets** in the task tracker, as comments
  or updates. Show the list of ticket changes first, and make them after
  the person confirms.
- Save **private notes** to the private team wiki space only.
- Confirm what was posted, with links.

**Test mode:** if the team settings say the team is in test mode, show
what would be posted, but do not post or change anything.

## Rules

- **The person approves everything.** Nothing is posted before "good."
- **Draft, never send.** Emails are drafts the person sends.
- **Never invent anything.** No made-up names, dates, or promises. If
  unsure, ask, or use a visible placeholder like `[date?]`.
- **Private notes stay private.** Opinions about people and internal
  politics never go in tickets, which clients may see.
- **Plain English.** The person may speak English as a second language, be
  new to the team, or be new to a tool. Short sentences, common words, no
  idioms or jargon.
- **Check before saying something.** Check sent email before saying a
  request was not sent.
