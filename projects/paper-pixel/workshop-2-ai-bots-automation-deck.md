# Workshop 2 Deck Content — From AI Workflow to AI Bot

Purpose: content-first outline for Claude to turn into visually polished slides.

Positioning:
- Workshop 1 = personal AI workflows with Projects/Gems/Custom GPTs. Human copy-pastes between AI and tools.
- Workshop 2 = connected AI bots/automations. AI can read/write selected tools, run from triggers/schedules, and ask for approval before risky actions.
- Do **not** promise attendees will build a production bot from scratch in 2 hours unless there is a controlled template/tool environment.
- Best promise: attendees leave with a bot spec, permission map, safety checklist, and one small demo of how a workflow becomes a connected automation.

Recommended title:
**From AI Workflow to AI Bot**

Subtitle:
Connect AI to the tools you already use — safely.

---

## Slide 1 — From AI Workflow to AI Bot

Connect AI to the tools you already use — safely.

Today’s focus:
- Google Sheets
- Calendar
- Telegram / WhatsApp-style messaging
- scheduled reminders / recurring tasks
- human approval where it matters

Speaker note:
This is not “prompting harder.” This is about giving AI limited, careful access to systems.

---

## Slide 2 — Workshop 1 vs Workshop 2

Workshop 1: AI as thinking partner
- Helps think, parse, draft, summarise
- You copy-paste between AI and tools
- No setup / no code
- Best for judgment-heavy personal workflows

Workshop 2: AI as connected operator
- Reads/writes selected tools directly
- Runs from triggers or schedules
- Can update records / prepare reminders / draft messages
- Needs permissions, safeguards, and testing

Key line:
- Workshop 1 gets the workflow right.
- Workshop 2 connects it to tools.

---

## Slide 3 — What we are building toward

A practical assistant that can:
1. Receive messy input
2. Read relevant context
3. Apply rules
4. Draft or update structured output
5. Ask for approval when needed
6. Run again next week

Example outputs:
- update a Google Sheet draft tab
- prepare a calendar event
- draft a group message
- send a reminder after approval
- flag missing info or risks

---

## Slide 4 — The bot mental model

Trigger → Input → Context → Tool access → Decision → Action → Log / review

Example:
- Trigger: Friday seller list arrives
- Input: WhatsApp fruit list
- Context: spreadsheet structure + group rules
- Tool access: Google Sheets
- Decision: parse items + fill rows
- Action: update draft tab
- Log/review: human checks before sharing

Key line:
A bot is a workflow with **tool access, memory, and guardrails**.

---

## Slide 5 — What bots are good for

Good bot tasks:
- repeat often
- have a clear source of truth
- involve structured records
- benefit from drafts/checklists
- have clear approval points
- are annoying enough to justify setup

Examples:
- group order spreadsheet
- payment reconciliation
- calendar/event assistant
- inbox triage summary
- recurring research scan
- ticket/reminder tracker

---

## Slide 6 — What bots are bad for

Bad first bot tasks:
- high-stakes decisions with no review
- unclear rules
- one-off tasks
- messy permissions / private data
- tasks where mistakes are expensive
- fully autonomous messaging/payment flows

Rule of thumb:
If you cannot describe the workflow manually, do not automate it yet.

---

## Slide 7 — Worked example 1: fruit group-buy assistant

Use case:
- weekly fruit list from seller
- neighbors order in spreadsheet
- final seller order
- payment reconciliation

Bot jobs:
1. Parse seller list into clean rows
2. Update weekly Google Sheet draft
3. Flag rows that do not fill boxes
4. Prepare final seller message
5. Track paid/unpaid confirmations

Human stays in control:
- approve item list
- approve final order
- approve reminders

---

## Slide 8 — Fruit bot: system map

Input:
- seller WhatsApp list
- payment screenshots
- neighbor orders

Context:
- spreadsheet structure
- names / columns / aliases
- box-fill rules
- condo delivery split rules

Tools:
- Google Sheets
- messaging draft surface

Output:
- updated sheet
- final seller order draft
- paid/unpaid status
- reminder drafts

Approval:
- Oanh checks before seller/order/reminder messages go out

---

## Slide 9 — Fruit payments: exact-match automation

Job:
Reconcile payment screenshots against weekly fruit sheet.

Trigger:
Oanh forwards payment screenshot.

Inputs:
- screenshot
- weekly sheet totals

Context:
- payer names / aliases
- current week tab

Tools:
- Google Sheets

Output:
- mark paid if person + amount match exactly
- flag mismatch if not exact

Approval:
- ask before changing ambiguous rows

Failure modes:
- wrong payer
- wrong week
- partial payment
- duplicate screenshot

---

## Slide 10 — Worked example 2: calendar/event assistant

Use case:
- discover interesting Singapore cultural events
- summarise why relevant
- check conflicts
- add to calendar if approved
- remind to buy tickets

Bot jobs:
1. Scan selected event sources
2. Extract event details
3. Summarise why it fits
4. Check calendar conflicts
5. Ask: “Add to calendar?”
6. Create event + ticket reminder after approval

Human stays in control:
- choose events
- approve calendar adds
- buy tickets manually

---

## Slide 11 — Calendar bot: system map

Input:
- event page / listing
- calendar availability

Context:
- target calendar
- preferences / taste profile
- conflict rules
- reminder preferences

Tools:
- web reader
- Google Calendar

Output:
- event summary
- conflict warning
- proposed calendar event
- ticket reminder

Approval:
- ask before adding
- warn about conflicts

Failure modes:
- wrong date/time/timezone
- duplicate event
- sold-out event
- event changed after listing

---

## Slide 12 — Worked example 3: recurring research scan

Use case:
- weekly job search scan
- travel price monitoring
- earnings-risk watchlist
- fresh event discovery

Bot jobs:
1. Run on schedule
2. Search specific sources
3. Filter against your preferences
4. Return short ranked summary
5. Save or notify only when useful

Key design point:
Good bots reduce noise. They do not dump everything they found.

---

## Slide 13 — The stack: what tools can connect

Common tools:
- Google Sheets
- Google Calendar
- Gmail / email summaries
- Telegram / WhatsApp-style chat
- Notion / docs
- websites / public sources
- files and screenshots
- scheduled jobs

Important:
- Each tool needs permission
- Permissions should be as narrow as possible
- Start with read-only when you can

---

## Slide 14 — Permissions: the boring part that matters

Three permission levels:
1. Read-only — safest first step
2. Draft/write to private workspace — useful middle ground
3. External action — highest risk

Examples:
- Read Sheet → OK
- Write draft tab → usually OK
- Send WhatsApp message → ask first
- Delete data → explicit approval only
- Make payment → no

Key line:
The more external the action, the more human approval you need.

---

## Slide 15 — Human-in-the-loop design

Do not ask:
“Can the AI do it?”

Ask:
“Where should the human approve?”

Approval points:
- before sending messages
- before changing important records
- before deleting anything
- before calendar invites to others
- before financial decisions

Useful pattern:
AI drafts → human reviews → AI executes only if approved.

---

## Slide 16 — Bot design template

For any bot, define:

1. Job — what recurring task does it help with?
2. Trigger — manual, scheduled, new file/message, webhook?
3. Inputs — what does it read?
4. Context — what stable rules/preferences does it need?
5. Tools — what can it access?
6. Outputs — what should it produce?
7. Approval — what must it ask before doing?
8. Failure mode — how will you know it broke?

---

## Slide 17 — Permission map

For your bot idea, mark each action:

Green:
- read
- summarise
- draft

Yellow:
- write to private draft area
- update non-critical records

Red:
- send messages
- delete data
- invite others
- spend money
- change official records

Design rule:
Green can be automated sooner. Red needs human approval.

---

## Slide 18 — Implementation paths

Option A: No-code / low-code automation
- Zapier / Make / Airtable automations
- easier to start
- limited flexibility
- costs can grow

Option B: AI platform assistants / GPT actions
- good for prototypes
- tool permission model varies
- may be hard to productionise

Option C: Custom lightweight bot
- more setup
- most flexible
- best for repeated workflows with private rules

Recommendation:
Prototype manually first, then automate the painful recurring parts.

---

## Slide 19 — Live demo option A: Google Sheet assistant

Demo goal:
- AI reads messy input
- updates a draft Google Sheet tab
- flags missing info

Steps:
1. Show messy input
2. Show target sheet
3. Run assistant
4. Review generated rows
5. Approve / edit

Safety:
- write to draft tab, not live final tab

---

## Slide 20 — Live demo option B: calendar assistant

Demo goal:
- AI extracts event details
- checks calendar conflicts
- drafts event
- asks before adding

Steps:
1. Paste event page/link
2. Extract title/date/time/location
3. Check target calendar
4. Show proposed calendar event
5. Add only after approval

Safety:
- no external invites
- no ticket purchase

---

## Slide 21 — Common failure modes

1. Wrong source of truth
- Fix: define which sheet/calendar/file wins

2. Silent failure
- Fix: logs + healthchecks + notifications

3. Over-permissioned bot
- Fix: least privilege, read-only first

4. Ambiguous names/amounts
- Fix: aliases, exact-match rules, ask on uncertainty

5. Bot sends too much
- Fix: summaries, thresholds, “only notify if useful”

6. Automation before workflow is stable
- Fix: run manually 2–3 times first

---

## Slide 22 — Safety checklist

Before turning on a bot:
- Does it have the minimum permissions needed?
- Can it explain what it is about to do?
- Does it ask before external actions?
- Is there a log of what happened?
- Can you undo the change?
- What happens if the input is ambiguous?
- Who gets notified if it fails?

Key rule:
Automate drafts first. Automate actions later.

---

## Slide 23 — Hands-on: design your bot

Pick one workflow from Workshop 1.

Fill the bot design template:
- Job
- Trigger
- Inputs
- Context
- Tools
- Outputs
- Approval points
- Failure modes

Then decide:
- Should this be a bot yet?
- Or should it stay a Project/Gem for now?

---

## Slide 24 — Hands-on: permission map

For your bot idea:
1. List every action the bot might take
2. Mark each action green / yellow / red
3. Decide where human approval is required
4. Identify the safest first version

Useful first versions:
- read-only summary
- draft-only helper
- write to scratch tab
- ask before external action

---

## Slide 25 — Takeaway

A good bot is not “AI doing everything.”

A good bot:
- knows the job
- has narrow context
- has limited permissions
- drafts before acting
- asks when uncertain
- leaves a trail

Start with the smallest useful automation.

---

## Slide 26 — Next step / homework

Before building your bot:
1. Run the workflow manually 2–3 times
2. Save examples of good input/output
3. Identify the real source of truth
4. Decide what requires approval
5. Pick the smallest first tool connection

Optional:
Bring your workflow spec to a clinic / follow-up session.

---

# Notes for Claude slide generation

Visual direction:
- Use the same visual language as Workshop 1.
- Make Workshop 2 feel like a natural sequel, not a separate technical bootcamp.
- Use diagrams for system maps and permission levels.
- Use red/yellow/green for permission map.
- Keep “human approval” visually prominent.

Suggested live examples to choose from:
1. Fruit group-buy payment reconciliation — strongest personal proof, concrete Sheets example.
2. Cultural events calendar assistant — good Calendar + approval example.
3. Recurring research scan — shows scheduled automation and concise notifications.

Avoid overlap with Workshop 1:
- Do not re-teach Projects/Gems in depth.
- Do not spend too long on prompt basics.
- Reference Workshop 1’s Input / Context / Rules / Output / Human model, then extend it with Trigger / Tools / Logs.

Avoid overpromising:
- Do not imply attendees will fully build production bots in 2 hours unless there is a controlled template/tool environment.
- Better promise: they leave with a bot spec, permission map, and one small working/draft automation demo.

Potential landing-page promise:
“You’ll learn how to turn a useful AI workflow into a safe automation — and where not to automate yet.”
