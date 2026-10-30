# The handover dashboard

**[Open the dashboard](https://erianapan.github.io/teton-night-shift-triage/dashboard.html)** · made for a large touchscreen or tablet at the nurses' station.

## Who uses it

The night team and the incoming day team, together, at the morning handover on one floor. On the night shown, Sofie, Jonas and Mette hand over at 07:45 to Hanne, the head nurse, Mikkel and three care assistants. The screen is shared, so the page shows no counts per person.

## Why it exists

The phone screen is built for the next sixty seconds of a night shift, and it leaves the review out on purpose. In the notes for that prototype I wrote that the hourly chart and the patterns belong to the handover meeting, not the corridor. This page is that handover. It answers three questions: how heavy was the night, which residents need watching today, and did anyone wait too long for help.

## How it is read

Top to bottom, in the order a handover conversation goes:

1. Today's staff, then last night's staff. These never change, so they sit above a line.
2. A switch for Last night, Week and Month. Everything below the line follows it.
3. How heavy the night was: every alert by hour, grouped the way the phone groups them (Go now, Next round, Later).
4. Four figures: median time to reach the room, urgent alerts, help called from outside the floor, and alerts per resident, each set against what is usual for this floor.
5. Residents at risk today. Residents with a high fall risk are always on the list. Anyone else joins after a fall, a silent sensor or an unusual night. Every column sorts.
6. When someone needed us: one bar per urgent alert, in the hour it fired, showing the time until someone walked into the room.

## How it builds on the phone prototype

It uses the same floor, the same 20 invented residents, the same event types, the same staff and the same night: the 03:10 fall in room 05, Jonas asking for help in room 07, and Gudrun's call in room 11 that waited eleven minutes behind both. The synthetic data is extended to 60 nights so the week and month views have something to compare against.

Two decisions carry straight over. The phone sorts alerts by what staff should do rather than by severity, and the dashboard counts them the same way. The phone lets the room sensor mark an alert as attended when a nurse walks in, with no tap, and the dashboard uses that same moment to measure response time. So the number says when someone reached the resident, not when someone remembered to press a button.

Anything that depends on something Teton has not published is marked Proposed on the page: knowing which colleague entered a room, the colleague-assist call, and closing notes written at the bedside.

## What is left out

A second version for the head nurse, with weekly and monthly patterns for planning, was scoped and not built. The Details button on each resident row leads nowhere yet. That page would hold the resident's night-by-night history.
