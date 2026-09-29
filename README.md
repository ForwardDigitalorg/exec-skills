Exec Skills

A collection of Claude Skills for executive project management and communication. Currently just email, more may be added later.

What's a skill?

A skill is a small folder with a set of written instructions inside it (a file called SKILL.md) that teaches Claude how to do a specific kind of task the way we actually want it done, not just the generic default way. Once a skill is added to someone's Claude setup, Claude reads it automatically whenever it's relevant, no need to re-explain the approach every time.

Each skill lives in its own folder in this repo. To use one, copy that folder into wherever your own Claude setup reads skills from (see "Using a skill" below).

What's in this repo
email-review/

Reviews any email draft, a new one or a reply, and marks it up with numbered suggestions, similar to how the old "Just Not Sorry" plugin used to underline self-undermining phrases like "I'm sorry but" or "just" and explain what to say instead. It never silently rewrites the email: the original stays intact, each flagged spot gets an explanation and a suggested alternative, and the author decides what to accept. It flags things like hedging language, jargon, unnecessary wordiness, a buried main point, and weak scannability. Every review ends with a clean version showing what the email would look like if every suggestion were accepted, so it's easy to see the whole picture, but that combined version always comes after the marked-up original, never in place of it. This applies broadly, to any email, not just one topic or client.

It's built on two real frameworks, not a one-off style preference:

Alignment and Attunement, from Kelly's Executive Communications training (Margaret Keys' framework, which Kelly has taught for years). Alignment is about the message itself: right content, right room, right time, no buried surprises. Attunement is about the audience: bringing your own authority while genuinely meeting the reader where they are, not talking down to them and not going over their head either.
PULSE's "Anatomy of an Action-Based Email" (DoubleGemini, Prasanth Nair), an 8-step structure covering tone, an action-oriented subject line, an up-front "Launch" (the one thing the reader most needs to know, stated before the background), scannable formatting, and a sign-off matched to the situation.

The specific instructions in email-review/SKILL.md, when to keep versus change a subject line on a reply, writing the headline last but placing it first, when a technical term should get its own clearly labeled line instead of being cut, are all applications of those two frameworks, drawn from the same training Kelly already gives on executive communication and email etiquette.

Using a skill
Download or copy the skill's folder (for example, email-review) from this repo.
Place that folder into the location your Claude setup reads skills from. In Claude Code, that's typically a .claude/skills/ folder, either inside a specific project or in your home directory if you want it available everywhere.
That's it. Claude will pick it up automatically and use it when a task matches what the skill describes, you don't need to invoke it by name.
Adding a new skill

Create a new folder in this repo named after the skill, with a SKILL.md file inside describing what it should do and when Claude should use it. Keep it in plain language, explain the reasoning behind each instruction rather than just listing rules, that's what makes a skill generalize well instead of only working for the one example it was built from. Keep new additions in the executive communication space, writing, reviewing, or preparing for high-stakes conversations, so the repo stays focused rather than becoming a catch-all.
