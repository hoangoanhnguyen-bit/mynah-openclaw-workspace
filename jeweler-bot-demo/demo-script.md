# Jeweler Bot Demo Flow

## Demo framing

“This is just a mockup using fake client projects. The idea is not to add a complicated new system. It’s to create one simple place where active jobs, promises, deadlines, and client follow-ups are visible.”

## Show the tracker

Open `client-project-tracker-template.csv` and point out:

- Client / channel
- Project type
- Current status
- Promised next step
- Client deadline
- Next follow-up date
- Risk level
- Draft client update

Say:

“The key column is not the AI column. The key column is *Next Follow-Up Date*. That’s what stops clients from chasing you first.”

## Demo 1 — Daily triage

Ask the assistant:

> “Look at this project tracker. What needs attention today? Prioritize anything overdue, red, or client-facing.”

Expected assistant output:

- Rachel — RED — follow up on pendant design; production slot may slip.
- Mrs Tan — AMBER — confirm workshop timing for ring resizing.
- Mr Lee — AMBER — supplier quote pending; send holding update.
- Sophie — AMBER — ready for pickup; send collection reminder.

## Demo 2 — Turn messy notes into tracker entries

Say:

“Instead of manually filling every column, you can paste rough notes.”

Example note:

> “Joanne WhatsApped asking whether her sapphire earrings can be done before her anniversary dinner on 18 June. Need to check with supplier on stone matching. I told her I’d update her tomorrow.”

Ask assistant:

> “Turn this into a project tracker row with risk level and draft reply.”

Expected structured output:

- Client: Joanne
- Channel: WhatsApp
- Project type: Custom order
- Item: Sapphire earrings
- Current status: Need supplier confirmation on stone matching
- Promised next step: Update client tomorrow
- Client deadline: 18 June
- Next follow-up: tomorrow
- Risk: Amber
- Draft reply: “Hi Joanne, I’m checking with the supplier on matching sapphires and will update you tomorrow. Since your anniversary dinner is on 18 June, I’ll flag timing clearly before we proceed.”

## Demo 3 — Draft calming client replies

Ask:

> “Draft a warm but professional WhatsApp update for Mrs Tan. She is anxious because she needs the resized ring by Friday, but the workshop has only said maybe Thursday.”

Expected answer:

> “Hi Mrs Tan, just a quick update — I’ve checked with the workshop and they’re currently expecting the resizing to be ready around Thursday. I know you need it by Friday, so I’ll monitor it closely and confirm again tomorrow. I don’t want to leave you waiting without updates.”

## Demo 4 — Weekly owner view

Ask:

> “Which projects are at risk of becoming angry-client situations?”

Expected answer:

- Rachel: no client decision yet, production deadline may slip.
- Mrs Tan: emotionally urgent deadline, supplier uncertainty.
- Mr Lee: waiting on supplier quote; needs holding update.

## Close

“The point is not to automate your whole business. It’s to make sure every promise has a reminder, and every client gets updated before they feel ignored.”

## Price bridge

“My minimum to set this up properly is S$1,200. That covers mapping your workflow, setting up the tracker, configuring the assistant prompts, testing it with 5–10 real projects, training you, and adjusting it over two weeks. If it prevents even one angry custom-order client or saves a few hours of follow-up stress each week, it should pay for itself.”
