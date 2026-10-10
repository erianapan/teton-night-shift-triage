# The problem this screen is trying to solve

## The numbers Teton published

From [Introducing Optimized Alerts](https://www.teton.ai/blog/introducing-optimized-alerts), April 2026:

| | Before | After |
| --- | --- | --- |
| Notifications per resident per day | 24.6 | 11.7 |
| Residents covered by fall-prevention alerts | 50% | ~60% |

Sensitivity is tuned per resident, on fall risk reassessed daily from 21 signals, adjusted for time of day, mobility aid use and health trend, and staff can override it.

That is a serious piece of work and the reduction is real. What interests me is what the post does not claim.

- Roughly **11.7 alerts per resident per day still fire**, and no figure is given for how many are false.
- About **40% of residents still have no fall-prevention alerts**.
- Effects on staff trust and alarm fatigue are asserted, not measured.
- The evidence is 5 beta departments, 218 residents, 24 to 43 days.
- Per-resident tuning is well developed. Per-facility configuration is barely described.

## What the numbers mean on a floor

Twenty residents at 11.7 alerts each is around 234 events in twenty-four hours, and Teton's own material says the night carries more of them. Two staff on the floor.

If every event is a line in a list, the product has produced a second job: reading the product. A night assistant does not have a reading job. They have a walking job, and the phone is supposed to decide where they walk.

So the question this screen asks is not "how do we show the alerts". It is:

> How much of this person's attention is the product allowed to spend, and what does it buy with it?

## Three failures that follow from getting this wrong

**1. The list of everything.** A chronological feed of events is the honest representation of the data and the wrong representation of the job. It spends attention per event rather than per decision. One restless resident can bury a fall.

**2. Severity words that need translating.** "Critical" and "Watch" describe the alert. They do not answer the only question being asked, which is whether to stand up. A severity label forces a translation step at exactly the moment nobody has one to spare.

**3. The analysis that belongs to the morning.** Hourly charts, trends and distributions are valuable, and they belong to the handover meeting and the manager, not to the corridor. Putting them first makes the screen about the data rather than about the resident.

The prototype is built against those three.

## What would test it

None of this is validated. It is reasoning from published figures, and the honest next step is a night shift on site. `notes/04-assumptions-and-questions.md` lists what I would try to find out.

Sources: [Introducing Optimized Alerts](https://www.teton.ai/blog/introducing-optimized-alerts) · [The Care Plan Describes Last Month's Resident](https://www.teton.ai/blog/the-care-plan-describes-last-months-resident) · [Teton](https://www.teton.ai/)
