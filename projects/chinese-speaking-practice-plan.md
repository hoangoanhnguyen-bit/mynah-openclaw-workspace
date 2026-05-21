# Chinese Speaking Practice Plan for Oanh

_Last updated: 2026-05-21_

## Context

Oanh took 3 years of Chinese in college and used to be able to write essays and communicate in Chinese. She has forgotten a lot after years without practice. She built Ink Radicals to relearn Chinese characters and wants to practice speaking too.

Constraints:
- No time/desire for formal classes.
- Hard to practice in daily life in Singapore because people switch to English when she hesitates.
- Friends/neighbors offered, but topics are awkward and she feels self-conscious faltering in front of people she knows.
- A bot may be safer because it is patient, nonjudgmental, always available, and can stay in Chinese instead of switching to English.

## Thesis

A bot is a good fit if it behaves like a gentle conversation partner, not a teacher correcting every sentence.

Goal:

> Rebuild spoken Mandarin fluency through low-pressure, recurring micro-conversations that stay mostly in Chinese but provide just enough support to prevent frustration.

## Practice modes

### 1. Daily life chat

Short 5-10 minute conversations about ordinary things:
- what Oanh ate
- kid/family logistics
- weather
- errands
- work frustrations
- books/shows/events
- weekend plans

Purpose: rebuild recall for everyday vocabulary.

### 2. Topic cards

The bot suggests a small topic with 5 starter words and 2-3 questions.

Example topics:
- ordering food
- describing what she ate or wants to eat
- describing a concert/play
- talking about music, instruments, composers, performers
- planning a trip
- telling a travel story
- telling a childhood or college story
- Singapore daily life

Avoid defaulting to tech/app topics; Oanh does not think she can talk about tech comfortably in Chinese right now.

### 3. Repair practice

When Oanh gets stuck, the bot gives:
- the missing word in Chinese + pinyin + English
- a simple sentence frame
- then asks her to try again

Avoid long grammar lectures unless asked.

### 4. Shadowing / repeat-after-me

Bot gives 2-4 natural sentences. Oanh repeats by voice. Bot can optionally correct pronunciation or tone if audio tooling supports it.

### 5. Code-switch guardrails

Bot should not immediately switch to English. Use graded support:
1. Chinese only.
2. Chinese + pinyin for one key word.
3. Chinese + short English gloss.
4. English explanation only if Oanh asks or is clearly stuck.

### 6. App-builder Chinese

Practice explaining Oanh's AI apps in Mandarin:
- Ink Radicals
- StencilCV/Reso
- Paper & Pixel playbook
- Plinthica
- child-led games

This connects language practice with her real interests and job narrative.

## Possible OpenClaw implementation

Created skill: `skills/chinese-speaking-practice/SKILL.md`.

Start simple in Telegram:
- Oanh sends text or voice notes.
- Mynah replies in mostly Chinese, with pinyin/glosses as needed.
- Use short prompts and keep sessions under 10 minutes.

Potential next steps if useful:
- Add TTS/audio responses for listening practice.
- Add speech-to-text / voice-note transcription if available or via plugin.
- Create a dedicated Chinese-practice skill.
- Schedule optional 5-minute practice reminders.
- Track recurring vocabulary in a small file.

## Bot persona

- Patient conversation partner.
- Does not embarrass Oanh.
- Does not overcorrect.
- Stays in Mandarin by default.
- Corrects one or two high-value things at a time.
- Celebrates successful communication, not perfection.

## First pilot

Try 5-10 minute sessions, aiming for daily practice but treating 3x/week as success.

Time-of-day plan: Monday, Tuesday, and Friday around 9:45am Singapore time, after kid gets on the bus, then bike ride + shower, before office commute. A cron reminder is set for 9:45am Asia/Singapore on Mondays, Tuesdays, and Fridays.

Anchor: post-bike/shower window, not "formal class time".

Session format:
1. Warm-up question in Chinese.
2. Oanh answers by text or voice.
3. Bot replies naturally and asks a follow-up.
4. If there are mistakes, bot gives only 1-2 corrections.
5. End with 3 useful words/phrases from the conversation.

## Open questions

- Does Oanh want simplified or traditional characters?
- Mainland Mandarin, Singapore Mandarin, or Taiwan-style Mandarin preference?
- How much pinyin support is useful?
- Voice notes or text first?
- Does she want correction during the conversation or only at the end?
