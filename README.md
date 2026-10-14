# Night Shift Triage

A design study for Teton, by Eriana Panopoulou.

**[Open the prototype](https://erianapan.github.io/teton-night-shift-triage )** · works best on a phone, screen dimmed.
**[Read the problem framing](https://erianapan.github.io/teton-night-shift-triage/problem-framing.html)** · the brief, the people, and the eight statements it was built against.
**[See the system flow](https://erianapan.github.io/teton-night-shift-triage/system-flow.html)** · where the data comes from, and where it goes.

---

## What this is

A working prototype of the alert screen a care assistant carries during a night shift on one floor of a care home. It runs in a browser, with one night of synthetic data at the alert volume Teton has published. It is not Teton's product, it uses no Teton data, and every resident in it is invented.

I built it to answer a question I could not answer by reading: what does this product feel like at 03:12, when you are one of two people on a floor of twenty residents.

## Why this question

Teton's own post introducing Optimized Alerts reports that sites were averaging **24.6 notifications per resident per day**, and that the new alerting brought this to **11.7**, a 52% reduction, with sensitivity tuned per resident across 21 signals reassessed daily.

Read the remaining numbers rather than the headline. Still almost twelve alerts per resident per day. Around 40% of residents with no fall-prevention alerts at all. No published figure for what share of alerts are false, and no measure of staff trust or fatigue.

Twelve alerts per resident, twenty residents, two staff. The design constraint is not detection accuracy. It is how much of a night nurse's attention the product is allowed to spend, and on what.

## The one thing to look at

Most alerting products make the user confirm an alert, because the system is blind and the tap is the only evidence anyone responded. Teton is not blind. Its sensor reconstructs the room in 3D roughly ten times a second and identifies where people are, and cross-room tracking already supports counting staff visits.

So the room can see the nurse walk in. **The acknowledgement tap should not be load-bearing.**

In the prototype, press *Simulate: you walk into the top room*. Nothing is tapped on the card. It changes to "You are in the room. Seen at 03:13, nothing tapped", stops counting as waiting, and tells you that your colleague and the wall screen now show the room as covered. "I am going" survives, demoted, for the thirty seconds while you are still walking, because intent and arrival are two different facts and only the first needs a thumb.

Two limits worth stating. The sensor sees a person, not a named person, so identity most likely comes from which phone is on shift. And presence should mark an alert **attended**, never **resolved**, because the person who walked in might be a relative.

## A short tour

| Try | What it shows |
| --- | --- |
| Read the top of the screen | Three sections named for what you do: Go now, On your 04:00 round, Later. No severity words to translate |
| Look at a Go now card | Room, then reason, then person with a risk pill. Nothing to read before acting |
| *Simulate: you walk into the top room* | Presence replacing the acknowledgement tap |
| *Alert Jonas*, top right | Sticky, one tap, and the button becomes a permanent Undo |
| *Get more help*, bottom bar | Escalation. Turns yellow once Jonas is alerted, and he drops off the ladder |
| *Concept A / Concept B* | Two placements for escalation, built so they can be compared rather than argued about |
| *Show a quiet night* | The night where nothing is wrong, which is most nights and which most monitoring products never design |
| Open *Shift review* at the bottom | The hour chart, folded away, labelled for the handover meeting |

## What is in here

- `index.html` — the prototype. One file, no build step, no dependencies. Open it in a browser.
- `problem-framing.html` — the brief, the people awake at 03:00, the problem statement, five principles and eight user stories, each traced to the decision it produced
- `system-flow.html` — the drawn system flow: one fall in room 05 traced through the sensors, the platform and every screen, and back in through the door
- `notes/01-problem.md` — the alert volume problem, from Teton's published figures
- `notes/02-design-log.md` — four rounds of critique and what changed each time
- `notes/03-system-context.md` — how this screen connects to the sensors, the wall screen, Samwise and E-Call
- `notes/04-assumptions-and-questions.md` — what it assumes Teton has, what it assumes they would need, and what I would want from one night shift on site
- `notes/05-critique-notes.md` — the notes I wrote while testing each version, in the order I wrote them

## How it was made

HTML, CSS and JavaScript in a single file, no framework, iterated over an afternoon. Each round went the same way: build it, read it as the nurse rather than as the designer, write down what was wrong, change it. `notes/02-design-log.md` is that record, including the version where I put a chart at the top of the screen and then removed it.

I used Claude as a pair for the code, the way Teton's own repositories are set up to be worked on. The design decisions, the critiques and the sequence of changes are mine.

## Honest notes

- Synthetic data throughout. The volume is calibrated to Teton's published rate and the night deliberately includes real mess: three residents who fired nothing at all, one resident with a 40-event stretch from 02:00, two dropped sensor readings, one record with no room, and a name long enough to break a layout.
- Everything about Teton here comes from public sources: the careers posting, the engineering blog, and the open-source `teton-ai/smith` repository. Nothing is insider knowledge.
- Where the design assumes something Teton does not publish, the assumption is marked, in the prototype footer and in `notes/04`.
