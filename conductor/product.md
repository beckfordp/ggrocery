# Product Guide — gGrocery

## Context
gGrocery is an application on the Gluon platform; the platform's own docs live in
gluon's `docs/`. gGrocery's decisions are in [`../docs/adr/`](../docs/adr/).

## What this app does
Grocery delivery: customers book a one-hour delivery slot and shop a weekly basket;
pickers pick it in store, substituting by the customer's rules; drivers deliver within
the slot and settle substitutions at the door; the customer pays for what was delivered.
See [`../docs/primer.md`](../docs/primer.md).

## Users
Six personas ([`../docs/personas.md`](../docs/personas.md)): Priya and George
(customers), Grace (store operations), Marek (picker), Sam (driver), Lin (support).

## Scope
The [story map](../docs/story-map.md) is the plan: R0 walking skeleton, R1 real slots, R2
real substitutions, R3 trust and care. Stories in
[`../docs/user-stories.md`](../docs/user-stories.md); each becomes a track here or in a
service repo.

## Services
Decided as the stories start, under gGrocery's
[reuse rule](../README.md#reuse-is-harvested).

## Goals
- Show gluon as a substrate: gGrocery built from its services, tools, libraries and ways
  of working.
- A demo that runs end to end in the sandbox and on the laptop, like gshop.
