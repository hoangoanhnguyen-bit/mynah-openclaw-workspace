# Personal AI Workflows for Real Life

Draft Google Slides deck for Oanh / Paper & Pixel Workshop 1.

Positioning note: learning/homework examples can live inside the adult personal-workflows deck, but do **not** market this as a separate kid/family AI track. If people want a kid-focused AI class, warmly point them to Xuan’s husband / Experience AI.

## Slide 1 — Personal AI Workflows for Real Life
Turn life-admin and learning chaos into reusable AI assistants — no coding.

By the end, you will have one assistant you can actually use this week.

## Slide 2 — A real-life admin problem, not a tech demo
- The weekly fruit group-buy is the motivating example: WhatsApp orders, names, quantities, payment, delivery slots — one giant scroll
- I built an assistant to do the boring parts
- Today: the same workflow pattern, applied to your real life-admin or learning task

Notes: This fixes the earlier implication. The group buy did not teach Oanh to build AI assistants; it revealed a good workflow-shaped problem.

## Slide 3 — The stuff apps cannot solve
- School updates buried in WhatsApp
- Birthday party logistics for 12 kids
- Meal planning around picky eaters
- Homework and revision plans that need encouragement, not just answers
- Adults pursuing hobbies or subjects of interest
- Travel research scattered across 17 tabs
- “Did I already reply to that email?”

These are not lazy problems. They need judgment. That is exactly where AI shines.

## Slide 4 — App vs AI workflow: which one fits?
Good app problem:
- Same inputs every time
- Clear buttons & forms
- Strict logic
- Many users, same flow
- Example: expense tracker

Good AI workflow problem:
- Messy text, screenshots, voice notes
- Rules have exceptions
- Output needs judgment or tone
- Just you, your family, or your child
- Example: school email triage, meal planning, study coach

AI bot / automation — not covered today:
- Connects directly to tools
- Reads/writes Sheets or Calendar
- Sends messages or reminders
- Runs on a schedule
- Needs permissions + safeguards
- Example: fruit order bot
- Workshop 2 territory

## Slide 5 — What AI can produce beyond answers
Messy input → Structured table → Checklist / draft / plan → Human-approved next step

- School email → deadline + packing checklist + calendar text
- Family constraints → meal plan + grocery list + prep schedule
- Homework topic → explanation + quiz + hints-first practice
- Hobby/interest → learning path + practice plan + resources
- Messy group chat → clean table + draft message + questions to clarify

## Slide 6 — Worked example · 01: Meal planning
This week’s input:
- Need 3 dinners this week
- Late work night Wednesday

Context:
- Family of 3
- Budget around $80
- Son dislikes broccoli
- Pantry has rice + eggs

Rules:
- Weeknight meals under 30 min
- Use pantry items and leftovers where possible

Ask:
- Make a meal plan + grocery list + prep steps
- Flag assumptions

Output:
- Egg fried rice + cucumber + rotisserie chicken
- Salmon rice bowls + edamame
- DIY wraps using leftover chicken + eggs
- Grocery list by section
- Prep: cook extra rice, boil eggs, chop veg

## Slide 7 — Meal planning: sample output
- Mon: noodles + rotisserie chicken + cucumber
- Wed: sheet-pan salmon, rice, edamame
- Fri: DIY wraps using leftovers
- Grocery list by section
- Sunday prep: cook rice once, chop veg in one batch

## Slide 8 — Worked example · 02: School logistics
This week’s input:
- Messy WhatsApp announcement: pick-up time, consent form, what to pack, assembly schedule — all in one paragraph

Context:
- Child is in P4
- School usually sends logistics by WhatsApp

Rules:
- Only use dates/details from the source
- Flag anything uncertain

Ask:
- Extract action items, deadlines, packing list, calendar text, and draft reply

Output:
- Action: submit consent form by Thu 5pm
- Pack: PE kit, water bottle, library book
- Calendar: “Class assembly — Fri 9am, Hall”
- Ask teacher: Is parent attendance required?
- Draft reply ready to copy-paste

## Slide 9 — School logistics: sample output
- Action: submit consent form by Thu 5pm
- Pack: PE kit, water bottle, library book
- Calendar: “Class assembly — Fri 9am, Hall”
- Ask teacher: Is parent attendance required?
- Draft reply ready to copy-paste

## Slide 10 — Worked example · 03: Learning helper
This week’s input:
- Science test on plants next week
- Topics: roots, stems, leaves, flowers
- 10 minutes/day available

Context:
- Child is 9–10
- Goal is understanding, not shortcutting homework

Rules:
- Coach with questions
- Give hints before answers
- Check against class notes

Ask:
- Make a short study plan
- Explain simply
- Quiz one question at a time

Output:
- 4-day study plan, 10 minutes/day
- Kid-friendly explanation
- 6 quiz questions
- Hints before answers
- Parent prompt: “Explain photosynthesis in your own words”

## Slide 11 — Every workflow has these 5 parts
Meal planning example:

Input:
- 3 dinners, late work night, pantry bits

Context:
- Family preferences, budget, schedule

Rules:
- Under 30 min
- No broccoli
- Use leftovers

Output:
- Meal plan
- Grocery list
- Prep steps

Human:
- I check before shopping

The magic is not the prompt. It is reusable context + rules.

## Slide 11 — Learning helper: sample output
From: “Science test on plants next week”

- Study plan: 10 minutes/day for 4 days
- Explain: roots, stems, leaves, flowers in kid-friendly language
- Practice: 6 quiz questions, reveal answers only after I try
- Parent prompt: “Ask me to explain photosynthesis in my own words”

## Slide 12 — The 5-step recipe
1. Pick the job: what repeatable task should this assistant help with?
2. Add context: family rules, constraints, examples, preferences
3. Add rules: always / never / ask me first
4. Choose output: table, checklist, draft, plan, quiz
5. Test with messy input, then refine once

## Slide 13 — The starter instruction template
You are my assistant for [task].

Context: [who/what this is for + recurring details]

Rules:
- Always: [things to always do]
- Never: [things to never do]

Input: I will paste/share [type of input]

Output format: [table, checklist, draft, plan]

Before final answer:
- Flag missing info
- Show assumptions
- Highlight anything needing my judgment

## Slide 14 — Hands-on · Round 1: Pick & draft
1. Pick ONE recurring task
2. Fill in the starter template
3. Do not worry about perfect — we will improve it together

Stuck? Try one:
- Meal planning for the week
- Birthday party for a kid
- School holiday activity ideas
- Homework / study coach
- Reading buddy
- Study quiz maker
- Adult hobby learning plan
- Travel itinerary draft
- Weekly newsletter for a group
- Customer reply drafts for a small business

## Slide 15 — Hands-on · Round 2: Test with real input
1. Set up your template as a Project / Custom GPT / Gem
2. Paste ONE real messy input and run it
3. Note: what worked? What did not?

The room gets quiet here. That is the work happening.

## Slide 16 — Make it reusable
Claude: create a Project
ChatGPT: create a Custom GPT or use Projects
Gemini: create a Gem

What goes in:
- Your context — the stuff that does not change
- Your rules — always / never
- Your output format
- One example that worked

## Slide 17 — Common failure modes — and the fixes
1. Too generic → Add constraints: budget, time, dislikes, pantry
2. Hallucinated dates/numbers → “Only use dates/numbers I provide”
3. Wrong tone → Paste an example of how YOU write
4. Forgets between sessions → Put context in the Project, not the chat
5. Goes too far → “Always show me the draft first”
6. Kids get answers too fast → “Give hints first; do not reveal final answer until I try”

## Slide 18 — Workshop 1 vs Workshop 2
Workshop 1 fits if:
- You want help thinking through messy info
- You are happy to copy-paste between AI and other tools
- Your task is mostly judgment + drafting

Workshop 2 fits if:
- You want AI to read your Google Sheet directly
- You want Telegram/WhatsApp automation
- You want triggers like “every Friday at 6pm”

Honest line: most life-admin tasks are fully solved by Workshop 1.

## Slide 19 — Keep the wheel in your hand
- Never auto-send messages or replies
- Never make payments or financial decisions
- Never blindly trust dates, totals, or amounts
- Keep private data out unless needed
- For anything that matters: AI drafts, you approve
- For kids: AI coaches, child thinks, parent checks

## Slide 20 — Before you leave today
Your commitment:
- Save your Project/Gem somewhere you can find it
- Pick ONE day this week to use it
- Send me a “win” or a “fail” — I love both

The hard part is not building it. It is using it next week.

## Slide 21 — Optional example: adult learning / hobbies
Use case: “I want to learn photography / pottery / coding / investing / gardening, but I do not know where to start.”

AI output:
- Beginner-friendly learning path
- 4-week practice plan
- What to buy / borrow / ignore
- Good YouTube/books/courses to compare
- Weekly reflection prompts

Human check: choose what is realistic and enjoyable.

## Slide 22 — Optional example: revision planner
Use case: “Exam in 2 weeks, too much material, child/teen feels overwhelmed.”

AI output:
- Break syllabus into small chunks
- Prioritise weak topics
- Make a daily 20-minute revision plan
- Generate practice questions
- Explain mistakes after the student attempts them

Rule: hints first, answers later.

## Slide 23 — Example · Study quiz maker
This week’s input:
- Spelling list + science notes
- Test Friday
- 15 minutes tonight and tomorrow

Context:
- Child is 9–10
- Short attention span after school

Rules:
- One question at a time
- Hints before answers
- Track weak areas

Ask:
- Turn these notes into a short quiz and coach the review

Output:
- 10 quick recall questions
- Easy / medium / challenge mix
- Quiz one question at a time
- Hints before answers
- Weak topics to review next

## Slide 24 — Example · Curiosity project coach
This week’s input:
- Kid is obsessed with football stats
- Wants to make something this weekend

Context:
- Child likes hands-on projects
- Parent wants it bounded and safe

Rules:
- Keep it child-led
- Suggest options, not a lecture
- Avoid overcomplicated tools

Ask:
- Turn the interest into a small project with steps and choices

Output:
- 3 project levels: easy / medium / ambitious
- Materials or tools needed
- Guiding questions
- Simple weekend plan
- Presentation idea for sharing the result

## Slide 25 — Optional example: reading buddy
Use case: “My child has a book / article / chapter to read and needs help understanding it.”

AI output:
- Ask pre-reading questions
- Explain tricky vocabulary in simple language
- Summarise one section at a time
- Ask comprehension questions
- Help the child support answers with evidence from the text

Rule: do not write the final answer for them.

## Slide 26 — Example · Adult learning / hobbies
This week’s input:
- I want to learn photography
- I only have 30 minutes twice a week

Context:
- Adult beginner
- Limited time
- Wants progress without buying too much gear

Rules:
- Keep it realistic
- Prioritise practice over theory
- Give low-cost options

Ask:
- Make a learning plan I can actually follow for 4 weeks

Output:
- Beginner-friendly learning path
- 4-week practice plan
- What to buy / borrow / ignore
- Resources to compare
- Weekly reflection prompts

## Slide 26 — How to produce the meal plan output
1. Context: family size, budget, dislikes, pantry staples
2. Rules: weeknight meals under 30 min, use pantry items and leftovers where possible
3. This week’s input: number of dinners and schedule constraints
4. Ask: realistic meal plan, grocery list by section, prep steps, assumptions
5. Refine: easier / cheaper / healthier / more kid-friendly

## Slide 27 — How to produce the school logistics output
1. Context: child/class, desired outputs, calendar style
2. Paste messy source: school email / WhatsApp / notice text
3. Rule: only use dates/details in source; flag uncertainty
4. Human check: verify dates, forms, money, and reply needs

## Slide 28 — How to produce the learning / hobby output
1. Context: age/level, goal, time available, confidence, success criteria
2. Input: topic list, notes, textbook photo, interest area, hobby goal
3. Ask for coaching, not answers: explain simply, quiz one at a time, hints first
4. Reflect: what did I miss, what should I practise next?
