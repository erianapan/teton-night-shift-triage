# Design log

Four rounds. Each one is the same loop: build it, read it as the nurse instead of as the designer, write down what is wrong, change it.

The useful part of this document is not the final screen. It is the first version, which was wrong in an instructive way.

---

## Round 1: the version that looked like a product and failed as a tool

**What it was.** A chronological list of every event in the night, about 200 cards. Above it, a bar chart of events per hour. Each card carried a severity label: Critical, Watch, Routine. A toggle collapsed repeated events from the same resident, which cut the card count roughly in half.

**What was wrong with it**, reading it as a care assistant rather than as its author:

1. **Too many lines.** Collapsing repeats is not a fix, it is a smaller version of the same mistake. The screen still presented the night as a feed to be read.
2. **"Critical" did not answer the question.** The only question is whether to walk to the room. Critical does not say. Watch says even less. Both require a translation at the worst possible moment.
3. **The chart was the first thing on screen.** It is the most attractive element and the least useful one. Events per hour is a question for the end of a hard night, not for the middle of one. Putting it at the top made the screen about the data instead of about the people.

The third was the real lesson. The chart went in because it was satisfying to build, which is a reason that belongs to the designer and not to the user.

---

## Round 2: ordered by what you do next

**What changed.**

- Three sections named for the action, not the alarm: **Go now**, **On your 04:00 round**, **Later**. Critical and Watch deleted.
- The flat list went away. Two rooms needing a person now, a six-room checklist for the next round in corridor order, four folded lines for the rest, and the full log closed at the bottom.
- The screen shows the night only up to 03:12, because at 03:12 you have not had the rest of it yet. Urgent alerts older than forty minutes are marked as already attended, with a one-line count.
- The chart moved to the bottom, folded, labelled "Shift review, for the morning meeting".
- Every urgent card stated why it deserved the walk, and carried an escalation contact.

**What was still wrong.**

1. The card read name first, then event, then an explanatory sentence. At speed you need **where**, then **what**, then **who**.
2. The explanation ("Movement pattern matched a fall, 94% confidence, and nothing has moved since") is data to read, not an instruction to act on. It belongs somewhere you have time.
3. The round list was sorted purely by corridor order, which treats a high-fall-risk resident the same as a routine check.
4. Status text was too quiet. "High fall risk" and "check she settled" looked the same.
5. The escalation line sat on every single card and was not practical anywhere.

---

## Round 3: readable in seconds

**What changed.**

- Go now card order became **room number, reason, person with a risk pill**. The explanatory sentence was removed entirely.
- The round list sorts by resident risk first, then corridor order, so the route is walked once but the person most likely to need you is first.
- "High fall risk" became a filled chip instead of grey text.
- Round rows put the person on the left over two lines, name then status, and the location and event right-aligned, so the eye lands on who and what to do.
- The right side reads as a state rather than as an event that fired: **"Last out of bed 03:06"**, not "Out of bed 03:06".
- **Alert Jonas** became a sticky button at the top of the screen. One tap, and it becomes a permanent Undo rather than a six-second window, because a mistaken tap should stay reversible for as long as the alert is open.
- The escalation line came off the cards and was deliberately left unplaced.

**On the escalation line.** It was doing three jobs at once, which is why it felt like clutter: saying who else is on the floor, offering to hand this job to someone else, and offering to escalate past the floor entirely. Those have different frequencies and different homes. The first became a permanent colleague strip under the header. The other two became the two concepts in round 4.

---

## Round 4: escalation, and the tap that should not exist

**What changed.**

- **Two escalation concepts, both built**, switchable at the bottom of the prototype, so they could be compared rather than argued about.
  - *Concept A*: one permanent entry at the bottom of the screen opening a ladder of contacts in order of distance: colleague, night coordinator, on-call nurse, ambulance. Always in the same place, thumb height, findable without reading. Costs: the call carries no context.
  - *Concept B*: escalation inside the job you already took. Taking a job keeps the card in a "you are on your way" state offering "Need more help here", which calls the coordinator with the room and resident already attached. Costs: it only exists where an alert already exists.
- The bottom bar **turns yellow and changes to "Need more help" once a colleague has been alerted**, and he drops off the ladder inside, since he is already coming.
- Contacts became tappable, with the number large enough to read at arm's length.

**And the change that matters most.**

The question that produced it: at 03:00, with a possible fall on screen, no nurse is going to stop and tap a button to confirm she is going. So can the system see her instead?

It can. Teton's sensor reconstructs the room in 3D about ten times a second, identifying where people are, and cross-room tracking already supports counting staff visits. The building knows when a second person walks into room 05.

Acknowledgement buttons exist because alerting systems are blind. This one is not. So:

- Walking into the room marks the alert **attended**, with no tap. The card says "You are in the room. Seen at 03:13, nothing tapped", and tells you the wall screen and your colleague now show the room as covered.
- An attended card stops counting as waiting and sinks to the bottom of Go now, rather than disappearing, because vanishing while you are standing in the room is wrong.
- "I am going" stays, demoted, for the thirty seconds while you are walking. Intent and arrival are two different facts. Only the first needs a thumb.
- Presence marks an alert **attended**, never **resolved**. The person who walked in might be a relative, or a resident who wandered. Resolution still needs a human.

---

## What I would change next

- Resident call button and building-detected alert currently look identical on the card. One is a person asking and one is a machine noticing. They should not read the same.
- Concept A and Concept B are not really alternatives. B is the better fix and A is the floor underneath it for everything not attached to an alert.
- The round checklist has no memory of the previous round, so a resident checked at 02:00 and quiet since looks the same as one never checked.
- Nothing here has been in front of a care assistant. Everything above is reasoning, and reasoning is the weakest form of evidence in this field.
