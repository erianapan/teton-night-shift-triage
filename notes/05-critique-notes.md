# Critique notes from the working session

These are the notes I wrote while testing each version, in the order I wrote them, lightly tidied for spelling. They are here because the reasoning is more useful than the result, and because the first version was wrong in a way worth showing.

Each round: I built it, read it as the care assistant rather than as its designer, wrote the note, changed it.

---

### After round 1

> Too many lines of notifications. I do not understand the urgency of the critical. Do I need as a nurse to go to the patient or not? What does watch mean, same questions on urgency and my actions?
>
> I also first see the events per hour graph. Why? It is not helpful to me as a nurse. I need to see what immediate action I must take, or what next action, or whom to alert. This graph is only nice to see at the end of a hard day or night, not centre focus when I try to care for people.

**Changed:** sections renamed for the action instead of the alarm. Severity words deleted. The flat list of 200 events replaced by two rooms needing a person, a six-room round checklist, and four folded lines. The chart moved to the bottom, folded, labelled for the handover meeting.

---

### After round 2

> In the Go now room card, write first the room number, then the reason, "Possible fall", then the name of the person. Next to her name have a short pill tag that states if she is a high fall risk. No "Movement pattern matched a fall, 94% confidence, and nothing has moved since" text. This is data for not this view, that I just have to see and act on in seconds. Maybe good for the next round list.
>
> In the next round list, where you have "Out of bed 03:06", make it into a last out of bed plus timestamp.
>
> Sort the round by priority of patient severity or something most likely needing my attention, then coordinate by corridor setup. Mark more severely status like High fall risk versus Check she settled. Name first, then status to notice, then the event, the first two in two separate lines, the third on the right side of the list item, so I can focus more on the person plus action to take.
>
> What am I supposed to do with this "If you cannot get there, night coordinator Mette, 4412"? Not practical in every card. Tell me its purpose and I will say where it goes.

**Changed:** card order became room, reason, person with a risk pill, and the explanatory sentence was deleted. Round list sorted by resident risk first, then corridor order. Status became a filled chip. The right side reads as a state, "Last out of bed 03:06". The escalation line came off every card and was deliberately left unplaced until it was clear what job it was doing.

---

### On the escalation line

It was doing three jobs at once, which is why it read as clutter:

1. saying who else is on the floor
2. offering to hand this job to somebody else
3. escalating past the floor entirely

Different frequencies, different homes. The first became a permanent colleague strip under the header. The other two became two concepts, built side by side so they could be compared rather than argued about.

---

### After round 3

> I need an Alert Jonas button top right for emergency.
>
> Once I click on Alert Jonas, I want the button to go back to Undo, but the Jonas alerted card row to stay as is, so I can reverse my action if I click by accident.
>
> Put a sticky button at the top to alert Jonas, having the rest of the screen scroll behind it. Then give me two concepts for where to call the night coordinator for extra help.

**Changed:** Alert Jonas became sticky at the top. One tap sends it, and the button becomes a permanent Undo rather than a six-second window, because a mistaken tap should stay reversible for as long as the alert is open. Two escalation concepts built and switchable.

---

### After round 4, and the note that mattered most

> Make these clickable and have them be direct phone calls opening my phone and automatically calling. I do not want to need to dial, press call, then hear the dial tone.
>
> I like the yellow Need more help here button, but it is very hidden. Change the Get more help button at the bottom of the screen to the yellow version only when I have already alerted Jonas, so that I can ask for more help directly.
>
> **In card 1, when the event is super urgent, as a nurse I would not take the time to confirm I am going by clicking the button. So is there a way from Teton's systems to see me and show to my colleague that I am there, or that it is taken care of?**

**Changed:** the bottom bar turns yellow and becomes "Need more help" once a colleague is alerted, and he drops off the ladder inside it since he is already coming. Contacts became tappable with the number set large enough to read at arm's length.

And the last question produced the change the whole prototype now turns on. The answer is yes: Teton's sensor reconstructs the room in 3D about ten times a second and identifies where people are, and cross-room tracking already supports counting staff visits. The building can see the nurse walk in.

So the acknowledgement tap stopped being load-bearing. Walking into the room marks the alert attended with nothing tapped, the card says so, and the wall screen and the other phone show the room as covered. "I am going" survives, demoted, for the thirty seconds while you are still walking.

---

### Two platform details found along the way

- On iPhone, tapping a phone number always shows a system confirmation before dialling, and no app can skip it. On Android an app with call permission can dial straight through. So "one tap, no dial tone" is achievable on Android and is one tap plus a system confirm on iOS.
- A published web prototype cannot place a call at all, and a phone link navigates the frame away and blanks the page. So the prototype demonstrates the moment before the call instead, with the room and resident already attached to it.
