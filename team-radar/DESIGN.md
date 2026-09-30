# team-radar: design

A tool for leaders who manage a team that delivers work for others. It works for agencies and consulting firms with outside clients, and for in-house teams (for example, engineering, analytics, or marketing) who deliver work to people inside their own company.

It tracks every request from the day it is made. It finds late work and silence early. It drafts the follow-up emails. It gives the leader one page that shows what needs them. Each team can give its own version a name.

**Status:** v1.1, 2026-09-29. Reviewed by the owner. Built so far: meeting-notes-capture and daily-summary.
**Owner:** Kelly Wortham

**Words used in this document:**

- **Client:** anyone the team delivers work for. For an agency or consulting firm, this is an outside client. For an in-house team, it is an internal stakeholder, such as another department or a product owner.
- **Request:** anything a client (or the leader, or a stakeholder) asks the team to do or deliver.
- **Owner:** the team member responsible for a request.
- **Blocker:** something the owner needs from someone else before they can continue.
- **Escalate:** send an item to the leader so they can help.
- **Task tracker:** where the team tracks its work, for example JIRA, GitHub Issues, Asana, or Monday.com.
- **Team wiki:** where the team shares knowledge and notes, for example Confluence, Notion, or an internal wiki.
- **Chat:** the team's chat tool, for example Slack or Microsoft Teams.
- **AI note-taker:** a tool that joins meetings and writes notes, for example Notion AI, Otter.ai, Fireflies, or Zoom AI Companion.

## Contents

- [1. The problem](#1-the-problem)
- [2. What it does](#2-what-it-does)
- [3. Rules we follow](#3-rules-we-follow)
- [4. Where the information comes from](#4-where-the-information-comes-from)
- [5. What we track for each request](#5-what-we-track-for-each-request)
- [6. When it runs](#6-when-it-runs)
- [7. Reminders and escalation](#7-reminders-and-escalation)
   - [When we are waiting on someone else](#when-we-are-waiting-on-someone-else)
   - [High priority](#high-priority)
   - [When no one on the team has acted](#when-no-one-on-the-team-has-acted)
   - [Health colors](#health-colors)
   - [Who decides what goes to the leader](#who-decides-what-goes-to-the-leader)
   - [Closing a request](#closing-a-request)
- [8. Drafted emails](#8-drafted-emails)
- [9. The leader's view](#9-the-leaders-view)
- [10. Other skills it uses](#10-other-skills-it-uses)
- [11. Settings for each team](#11-settings-for-each-team)
- [12. What must be in place first](#12-what-must-be-in-place-first)
- [13. Build steps and time](#13-build-steps-and-time)
- [14. Open questions](#14-open-questions)

## 1. The problem

Delivery teams are busy. They might not plan ahead or set due dates. They may forget how long ago something was first asked for. Two, four, or six weeks go by. No one feels "blocked," because there is always other work to do.

Meanwhile, the client wonders where their work is. In the end, the client asks the team's leader. When the leader asks the team, the answer is often: "They did not give us what we needed."

Sometimes that is true. Sometimes no one ever asked for it. Without a record of **when the request was made, when the blocker appeared, and when (or if) anyone asked to clear it**, no one can tell which is true.

Status updates do not fix this. Most are short headlines like "worked on X," written from memory at the end of the day, or even at the end of a week or month when time sheets are due. The forms never ask about blockers, decisions, dates, or who the team is waiting on.

This happens in agencies, in consulting firms, and in in-house teams. The client may be a company paying for the work, or a colleague in another department. The problem is the same.

[↑ Back to contents](#contents)

## 2. What it does

1. **Tracks every request from the day it is made.** It finds requests in meeting notes, email, and the task tracker, even if no one thinks they are blocked.
2. **Counts how long each request has been open, and sends reminders on a schedule.** Reminders go first to the owner, with an email already drafted. Only later do they go to the leader. **High-priority requests go to the leader automatically** after a shorter time. The owner does not need to agree.
3. **Replaces manual status updates.** Each day, Claude drafts the update. The person checks it and approves it in about 3 minutes.
4. **Gives the leader one page** that shows what needs them across all projects. One click opens the details.

[↑ Back to contents](#contents)

## 3. Rules we follow

- **Collect first, then ask.** Claude drafts from the day's information. It only asks about what is missing. No forms.
- **The person approves everything.** Nothing goes into a shared system until the person checks it.
- **Each person's own data only.** The tool reads only that person's own email, calendar, and notes. No one reads anyone else's email. Direct messages are never read. If something in a direct message matters, the person adds a short summary.
- **Draft, never send.** Every email is a draft. The person checks it and sends it. Drafts use the **email-draft** skill.
- **Facts and private notes go in different places.** Facts about the work go in the task tracker. Private notes go in the team wiki, in a space only the team can see. Private notes include opinions about people on the client side, time off, and internal politics.
- **Dates show who was waiting on whom.** The record shows who waited on whom, and for how long. This is true for the team and for the client.
- **Plain English in every message.** Team members may speak English as a second language, be new to the team, or be less familiar with a certain tool or task. Clear writing helps everyone. Everything the tool writes to a person uses short sentences and common words. It does not use idioms or jargon. This includes questions, reminders, and field names.
- **Check before saying something.** Check sent email before saying a request was never made. Check for a written decision before saying work has stopped.

[↑ Back to contents](#contents)

## 4. Where the information comes from

| Source | What it gives us | Notes |
|---|---|---|
| Meeting notes from the AI note-taker | Requests, promises, decisions, dates, blockers, notes about people on the client side | The most useful source. Claude pulls out the key points and links to the full notes. It does not copy them. |
| Meeting notes the person uploads | The same, for meetings with no note-taker | See **meeting-notes-capture** ([section 10](#10-other-skills-it-uses)) |
| Email, inbox and sent (for example Gmail or Outlook) | Requests, follow-ups, client replies, delivered work | Sent email shows whether a request was really made |
| Calendar | Meetings, time off | Tells Claude which meetings need notes, and when to plan cover for time off |
| Task tracker | Tickets, status, due dates | Also where facts are saved |
| Team wiki | Past notes, cover plans | Also where private notes are saved |
| Chat (optional) | Team or shared-channel messages | Read only, and only if the company agrees to connect it |

Some things will always be missed: direct messages, hallway talks, and calls with no note-taker. To reduce this, invite the note-taker to every meeting you can. For other meetings, take written notes and upload them ([section 10](#10-other-skills-it-uses)).

[↑ Back to contents](#contents)

## 5. What we track for each request

Everything is built around one thing: the **request**.

| Field | Meaning |
|---|---|
| What | Describe the work as briefly as possible - one line |
| Project / client | Client name or internal |
| Requester | The person who made the request, with a link to where it was made |
| Request date | The date the request was made. The delivery clock starts here, unless Needs approval is checked. Then it starts on the Approval date. |
| Needs approval? | A checkbox. Most work does not need the leader's approval, so it is unchecked by default. The **owner** checks it when the work needs the leader's OK before the team agrees to do it. Once a day, the leader gets **one notice** listing every request waiting for approval, across all projects. |
| Leader decision | Appears only when Needs approval is checked. The leader chooses **Approved** or **Not approved**, directly on their page. **Approved** starts the work. **Not approved** closes the request with a **not-approved** label (see Status). |
| Approval date | Filled in automatically: the date the leader chose **Approved**. The delivery clock starts here. |
| Owner | The team member responsible |
| Proposed due date | Claude suggests it. The owner confirms it. It is marked if not yet confirmed. |
| Waiting on | The person or team we need something from, if any |
| Blocker noted on | The date the problem first showed up in any source |
| Requests to clear | Every date the owner tried to remove the blocker or asked for information needed to continue, with links. Claude fills this in when the request is in email or in the AI meeting notes. The owner adds any others (calls with no note-taker, direct messages). |
| Health | Green, yellow, or red ([Health colors](#health-colors)) |
| Flags | Escalate now · risk to the whole project · holds up other work |
| Status | **Waiting on approval** (only when Needs approval is checked), **Next**, **Now**, **Blocked** (must say why), **Done**, or **Deprioritized** (must say why, and who decided). **Deprioritized** means paused: the request stays open and can be picked up again later. When the leader chooses **Not approved**, the request gets a **not-approved** label and moves to **Done**. Declined work never uses Deprioritized, so the two are never mixed up. (Most task trackers let anyone add a label. A separate "Declined" status can replace the label later, if a tracker admin adds one.) When Done: the **Done date** and the proof (the delivered work, the client's approval, or the owner's confirmation). The dashboards show these steps. The task tracker keeps its own statuses. The team's settings match them to these steps, so nothing in the task tracker has to change. |

If a ticket already exists for the request, Claude links to it. It does not create a second one.

[↑ Back to contents](#contents)

## 6. When it runs

**Every day, at the end of each person's own workday. The person starts it and walks away. Claude does the work. The person needs about 3 minutes.**

The daily run is the **daily-summary** skill ([section 10](#10-other-skills-it-uses)). Many teams work in different time zones, so there may be no shared "end of day." Each person starts it when their own workday ends, by saying something like "run my daily summary." An optional **reminder around 5 pm local time** (a push notification on workdays) tells them when to start it. Then they can step away while Claude works. Claude does steps 1 to 4. The person only does steps 5 to 7.

**What Claude does (automatic):**

0. **Checks yesterday's open blockers first.** If no one asked the other person to clear a blocker, Claude says so at the top and drafts the request ([When no one on the team has acted](#when-no-one-on-the-team-has-acted)).
1. **Reads the day's information:** meeting notes from the note-taker, email (inbox and sent), calendar, and today's task tracker updates.
2. **Finds** requests, updates, decisions, and dates. Matches them to requests it already knows about. Suggests new ones.
3. **Suggests a due date** for any request that does not have one.
4. **Drafts the daily summary.** Then it checks the summary against these questions and marks what is missing:
   - What **needs a decision**, from whom, and by when?
   - Who are you **waiting on**, and since when?
   - Was any **date agreed or changed**, and why?
   - What was **decided**, and by whom? Does it change an earlier decision?
   - What was **finished**? Link to the proof.

   The summary follows the same order: what needs action first, what is already settled last.

**What the person does (about 3 minutes):**

5. **Answers only the missing questions from above.**
6. **Answers two short questions Claude always asks:**
   - Did a client ask for anything in a **direct message or a call with no note-taker** today?
   - For meetings with no notes: please upload your notes, or confirm there is nothing to add.
7. **Checks and approves** the summary. Claude then:
   - saves the facts in the task tracker
   - saves private notes in the team wiki
   - posts the summary to the **team-agreed location** (for example, a team wiki page)

**Better information means less work.** If the note-taker joins every meeting and the task tracker is kept up to date during the day, most days steps 5 and 6 are quick, and step 7 is just "check and approve."

**Every week: Claude drafts. The person needs about 10 minutes.**

Claude drafts the week's priorities, due dates, and health colors for everything the person owns. The person confirms or corrects it.

**First run: connect the tools (guided, about 15 minutes)**

The first time a person runs the tool, Claude checks which connections already work: email, calendar, task tracker, team wiki, and AI note-taker. It walks the person through only the missing ones. Then it runs a short test to prove each one works (for example, "I can see your calendar and today's 3 meetings"). A short **SETUP.md** file in the skill folder is the written backup (see [section 12](#12-what-must-be-in-place-first)).

**One-time setup, for each client or project: about 1 hour**

The first run gives the owner a starting point, instead of an empty list:

1. Claude reads the last **90 days** of email (inbox and sent) and the task tracker.
2. The owner shares the tickets for **one client or project**, plus the related team wiki pages and meeting recordings.
3. Claude writes an **interview**: a list of questions about that client or project. The questions cover open requests, who is waiting on whom, decisions, dates, and anything the sources do not explain.
4. The owner spends **about 1 hour** answering the questions. The answers are saved as a team wiki page under that client or project.

During the test week, these two setup steps are the only new tasks, besides adding the AI note-taker to meetings and checking the daily summaries.

**When something happens:**

- **Time off on the calendar:** about 5 business days before, Claude drafts a cover plan. It lists open requests, where the documents and data are, who to contact in an emergency, and where each piece of work stands.
- **Reminder steps** ([section 7](#7-reminders-and-escalation)).
- **"No request sent" check:** at the start of each person's daily summary ([When no one on the team has acted](#when-no-one-on-the-team-has-acted)).
- **The leader's daily run:** once a day, a scheduled run updates the leader's page and sends the leader one notice with everything waiting for approval and anything newly escalated.

[↑ Back to contents](#contents)

## 7. Reminders and escalation

**The clock starts when the request is made.** It does not wait until someone notices a blocker. Claude works out whether a request is blocked from the record. No one has to say so.

**When the delivery clock starts:**

- **Needs approval unchecked** (most work): on the Request date.
- **Needs approval checked:** on the **Approval date**. Until then, the request is **Waiting on approval**. It is on the leader's "Needs you" list from the first day, and in the leader's daily approval notice. If the leader chooses **Not approved**, the request closes and no clock starts. Time spent waiting on approval never counts against the owner.

### When we are waiting on someone else

"Someone else" can be the client, another team, or a stakeholder. These are the default times, used when there is no due date. Each team can change them.

| When | What is true | What happens |
|---|---|---|
| The next daily summary after the blocker is noted | No request sent yet | Claude reminds the owner and drafts the request, using the **email-draft** skill |
| 3 days after the owner asks | Still blocked | Claude reminds the owner and drafts a follow-up |
| 7 days after | Still blocked | Claude reminds the owner and drafts a follow-up. The request shows as yellow on the leader's page. |
| 10 days after | Still blocked | The leader gets a **check-in** item: talk to the owner, and decide whether to step in |
| 14 days after | Still blocked | The leader gets an **escalate** item, with the full history |

**If there is a due date,** the steps come sooner. The request goes to the leader when the time left is shorter than the work left.

### High priority

Requests marked **High** follow faster steps and go to the leader **automatically**. The owner cannot stop or delay this. They can only add a note.

The clock for these steps starts when the owner asks the other person to clear the blocker.

| When | What is true | What happens |
|---|---|---|
| The next daily summary after the blocker is noted | No request sent yet | Claude reminds the owner and drafts the request |
| 1 business day after the owner asks | Still blocked | Claude reminds the owner and drafts a follow-up |
| 3 business days after the owner asks | Still blocked | The leader gets an **escalate** item automatically, with the full history and the owner's latest note |

If no one on the team has acted on a High request, the owner gets 3 business days from the reminder in their daily summary. Then the leader is told ([When no one on the team has acted](#when-no-one-on-the-team-has-acted)).

- **Who sets High:** the owner, based on what matters most to the client. The leader can change it. It is set when the request is first found, or in the weekly review.
- **Changing the times:** each team can change the 1-day and 3-day steps in its settings (for example, 2 days and 5 days).
- **Too many High items:** if more than about a third of open requests are High, the leader's page shows a warning. At that point, High no longer means anything.
- **Too few High items:** saying nothing is urgent is as risky as saying everything is. The leader's page shows a warning when:
  - an owner or project has open client work but **nothing marked High for 2 weeks or more**, or
  - a request **misses its due date or a promise to a client**, but was never marked High or sent to the leader.

  Silence is a reason for the leader to check in. It does not prove that all is well. This happens often: someone says "no blockers" while a request to someone else has been stuck for weeks.

### When no one on the team has acted

This covers two cases: a request with no team action after half its due time has passed, or a blocker where no one ever asked the other person to clear it.

1. **Check at the next daily summary.** When a person starts their daily summary, Claude first checks whether a request was sent to clear each blocker from before. If not, Claude reminds the owner right then. If someone needs to be asked, the email is already drafted. **The clock starts at that reminder.**
2. The owner has **3 business days** from the reminder to act.
3. After that:
   - **High priority:** the leader is **told**.
   - **Everything else:** it shows on the leader's page as late, like any other late item.

The owner always sees it first and has a fair chance to fix it. Nothing is hidden.

### Health colors

- **Green:** on track.
- **Yellow:** late. Needs a reason, the first date, the new date, and a plan.
- **Red:** off track or blocked. Needs everything yellow needs, plus three flags: risk to the whole project, holds up other work, escalate now.

### Who decides what goes to the leader

Claude suggests it, based on rules: the reminder steps, a missed promise to a client, or anything that changes budget or scope. The owner agrees or disagrees in the daily check. Every "disagree" is recorded. **High-priority items are the exception.** They go to the leader automatically, and the owner cannot stop them.

### Closing a request

A request closes when its ticket in the task tracker is closed (Done) **and** the owner confirms it is done. If there is no ticket, the owner's confirmation is enough. Claude may also notice signs that the work is finished, for example an email from the client confirming they received it, or a status update. When it does, Claude asks the owner to confirm. Nothing closes without the owner confirming.

[↑ Back to contents](#contents)

## 8. Drafted emails

All drafts follow the **email-draft** skill:

- **First request:** a new email. Subject: `Request: [topic]`. The request is the first sentence, in italics.
- **Follow-ups:** replies in the same email thread, with the same subject. Each follow-up says something new: the date of the first request, and what the delay now affects. Never "just following up."
  - **But the subject must match what is true today.** If it does not, use a **new subject line**:
    - **No longer urgent:** remove URGENT, and update or remove the date.
    - **Now urgent:** the deadline is less than 5 business days away, so add URGENT. `URGENT request: sign-off on Q3 budget - deadline 05-Oct`
    - **The deadline has passed, but the discussion continues:** remove the old date. `URGENT request: planning for Q3 - deadline 05-Oct` becomes `Continued: Q3 planning discussion`. If a new deadline is agreed, add it: `Continued: Q3 planning - deadline 20-Oct`.

    A subject with an old date, or URGENT that is no longer true, teaches people to ignore both.
- **Links:** only to things the reader can open. People outside the team get their own ticket, a shared document, or the first email. Never links to the team's internal tools.
- **Voice:** the owner's my-writing-style profile.
- **The tool never sends email.**

[↑ Back to contents](#contents)

## 9. The leader's view

One page, for a leader who needs to act, not read status reports.

```
NEEDS YOU                       most urgent first
  one line each: project · what · what you need to do · by when · why · link
  includes work waiting on your approval
AT RISK (yellow)                one line each, closed until you open it
PROJECTS                        one line each, click to open that project's own page
  Project A   red 2 · yellow 6 · escalate 3   →
GONE QUIET                      no change in 21+ days · nothing marked High in 2+ weeks   →
PEOPLE, next 14 days            time off · cover plan: ready / missing
```

Rules:

- Every line answers: "What do you need from me, by when, and why?" It includes a link. A line that cannot answer this does not belong here.
- **No green items.** Not even counts.
- **Three kinds of "needs you":**
  - *Decide:* the leader makes the call.
  - *Escalate:* the leader talks to someone on the client side (or another team's leader) to unblock it.
  - *Approve:* the owner marked the work as needing approval. The leader chooses **Approved** or **Not approved** right on the page.
- **Counts use the same size of work everywhere:** workstreams (for example, epics and stories), never small tasks. A project with 500 small items and a project with 12 must be comparable.
- **Too many items:** if "Needs you" often has more than about 7 items, that is a warning. The team is sending up things it should decide itself.
- **Too few items:** the opposite is also a warning. If "Needs you" and "At risk" stay empty for weeks while clients are active, the page says so ([High priority](#high-priority)).
- History, time spent, activity, and progress are one click away. They are not on this page.

The page reads from the task tracker and the team wiki.

**Where it lives: a dashboard in the team wiki.** Each part of the page is a filtered view of one list of requests. Claude updates the list every day from the task tracker and the team wiki. The first version is built in Notion. Other wikis can work if they support filtered lists and timelines.

**Timeline (Gantt) views.** Many leaders like Gantt charts, so the page includes a timeline view. In Notion, this is the built-in Timeline view. It updates itself, and every bar can be clicked.

- **One bar for each workstream,** not each task. This is the same size of work as the counts. Each project page has its own timeline. The leader's page shows all projects on one timeline.
- **Bar start:** the Request date, or the Approval date when approval is needed.
- **Grouped by project.**
- **Plan and actual, one above the other:**
  - **Plan timeline:** every item, from start to **due date**, colored by health.
  - **Actual timeline, right below it:** only items that are late, from start to the **Done date** (or today, if not done). Items that are on time do not appear. So this view is also a list of late items.
  - **Days late** is worked out automatically: Done date (or today) minus due date.
  - **Color by days late:** **yellow** for 1 to 5 days late, **red** for more than 5 days late.
  - Every bar in both views can be clicked.
  - Still to check in Notion: whether the Actual bars can take their color from days late. If not, the bar's label shows it instead (for example, "Project A · +14 days late").

A Gantt chart is only as good as its dates. This design fixes that: Claude suggests a due date for every request, and the owner confirms it. So the timeline has real end dates, not empty rows.

[↑ Back to contents](#contents)

## 10. Other skills it uses

- **email-draft** (already built): all drafted emails.
- **my-writing-style** (one for each person): how each person writes.
- **daily-summary** (built): the daily run. The person starts it, walks away, and comes back to a draft summary with only the missing questions. They answer, say "good," and Claude posts it. It also sets up the optional 5 pm reminder.
- **meeting-notes-capture** (built): for any meeting with no note-taker. The person pastes rough notes. Claude pulls out requests, decisions, dates, and blockers, and the person approves them. It pairs with a **10-minute calendar block** after those meetings, which the skill can suggest adding. It is also useful on its own.

[↑ Back to contents](#contents)

## 11. Settings for each team

The tool is the same for every team. Anything specific to one team goes in a separate settings file. The team keeps and controls it:

- The leader's name and role
- Which task tracker, team wiki, and chat tool the team uses
- The projects, and which clients use their own task tracker. (Every client project needs at least one item in the team's own task tracker that links to the client's.)
- Where daily summaries are posted (the team-agreed location), and where the leader's page is
- Reminder times, if different from the defaults, including the High-priority times and who may set High
- Rules for each client's data (for example, no meeting notes stored for a certain client)
- The team list, and the default line added at the end of emails

[↑ Back to contents](#contents)

## 12. What must be in place first

- **Everyone uses the task tracker the same way on every project.** Blocked, due dates, and labels mean the same thing everywhere. If not, the leader's page only works for some projects.
- **Connections** to the task tracker, team wiki, email, calendar, and AI note-taker, for each person. The tool's first run guides each person through these. **SETUP.md** in the skill folder is the written backup. It lists each connection, what it is used for, and links to each tool's own official instructions (not copied steps, which go out of date). Team details, such as which workspace or project to use, go in the team's settings, not in SETUP.md.
- **Each client's data rules are checked** before any meeting notes from that client are stored. For in-house teams, this means checking company policy on recording meetings.
- **A way to run it every day:** each person starts the **daily-summary** skill at the end of their day, with an optional reminder around 5 pm local time. The leader's page and approval notice update in one scheduled run a day.

[↑ Back to contents](#contents)

## 13. Build steps and time

Estimates are in days of work. They are based on a similar tracker already built for one project.

| Step | Estimate |
|---|---|
| This design, checked and reviewed by owner | 3–4 days |
| meeting-notes-capture skill | 1 hour (done: built 2026-09-29) |
| daily-summary skill (the daily run, with the 5 pm reminder) | done: built 2026-09-29 |
| team-radar version 1: daily run, request list, reminder steps, drafted emails | 2–3 days |
| Guided first-run setup and SETUP.md | ½ day |
| Test on the designer's own data | 1 day |
| Test with two volunteers, ideally working for different clients, for 1 week. For the first few days, Claude only suggests and saves nothing. Two people give two kinds of feedback, and the leader's page has more than one project to show. | 1 week total, about 1.5 days of work (a little extra setup for the second person) |
| Leader's page, version 1 | 3–5 days, mostly depending on how consistently the task tracker is used |
| Rollout for anyone who wants it: the volunteers show it to the team | ongoing |

[↑ Back to contents](#contents)

## 14. Open questions

1. **Time tracking.** Should the daily run also draft time entries (for example in FreshBooks, Harvest, or Toggl)? That depends on what the time-tracking tool's connection can do. Not checked yet. Not part of the test.

[↑ Back to contents](#contents)
