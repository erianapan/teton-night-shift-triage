# Assumptions, and what I would want from one night on site

## What the prototype assumes Teton already has

All of this is published.

- Per-room fall detection with a confidence value, and pseudonymised clip replay
- Bed-exit and stillness events
- Respiration while the resident is stationary
- Per-resident fall risk, reassessed daily from 21 signals, with staff override
- Staff detected as people in rooms, enough to count staff visits
- All sensors calibrated into one facility-wide coordinate frame, with live occupancy
- A resident-initiated call channel, E-Call

## What it assumes Teton would need to add

Marked in the prototype footer as well.

- **Named staff position.** So the screen can say "Jonas, room 07" rather than only "a colleague is somewhere on the floor". Most likely resolved by the phone on shift rather than by the ceiling.
- **Staff-to-staff assist.** The Alert Jonas button. Nothing published suggests this exists.
- **Shared attendance state** across the phone, the wall screen and the other phone, so presence in a room suppresses the alert everywhere at once.

## What I got wrong on purpose, and left in

The synthetic night deliberately contains the cases that break layouts, because a prototype with tidy data proves nothing:

- three residents who fired nothing at all, which is either a settled night or a dead sensor and the screen cannot tell which
- one resident with a 40-event stretch between 02:00 and 05:00, who buries everybody else in a chronological view
- two events whose sensor reading dropped out
- one record with no room number
- a 28-character name

## What one night shift would tell me

This is the part the prototype cannot do. The whole design above is reasoning from published numbers, and reasoning is the weakest evidence available in a field where the user is tired, interrupted and holding something in one hand.

**On attention**
- How many times does the phone actually come out of the pocket in an hour, and what fraction of those were worth it?
- When an alert arrives while they are already in a room with a resident, what happens to it? My guess is it is ignored and never comes back, which would mean the whole "Go now" model has a hole in it.
- Is the phone even the primary surface at night, or is the wall screen doing more of the work than the product assumes?

**On trust**
- Which alert types have they stopped believing, and when did that happen? A product can lose credibility in a week and never get told.
- Do they know fall risk is recalculated daily? If the number changes and nobody notices, the tuning is invisible and therefore worthless.
- What do they do when they disagree with the system?

**On the handover**
- Who actually reads the shift review, and when? If nobody opens it, folding it away costs nothing and the morning meeting needs a different artefact entirely.
- What gets written down twice, once in the care system and once in Teton?

**On the three quiet residents**
- How would they find out a sensor had failed? If the answer is "we would not", that is a product gap worth more than any alert tuning.

**On language**
- The floor staff I would be observing in Denmark may not be working in English. My Danish is beginner level, so for Danish sites I would plan observation with a colleague or an interpreter rather than pretend otherwise, and lean on what I can see rather than what I can overhear.

## One thing I would measure that is not currently measured

Alerts per resident per day is a product metric. The staff-facing version is **how many times the phone interrupted you, and how many of those were worth the walk**. The second number needs the nurse to tell you, once, at the end of a shift, in one tap. Which is itself a small design problem, and probably a better first project than anything in this prototype.
