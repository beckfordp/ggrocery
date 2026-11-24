# Open questions

Undecided; each is settled by an ADR in [`adr/`](./adr/) before the story that needs it.

1. **What does a time-slot reservation hold?** A place in the slot's delivery capacity,
   stock for that day, or both? Grocers usually don't hold stock per item; the pick finds
   out what's there.
2. **How long is a slot held, and does an open hold count against capacity?** Suggested:
   held for two hours, and yes, it counts, so a full slot is really full.
3. **Capacity: one number per slot, or worked out?** Suggested: one number per slot in
   the skeleton; from vans, drops per route and pickers later.
4. **Substitution rules: per item, per order, or both?** And who picks the substitute:
   the picker on the shop floor, a suggestion from the system, or the customer in
   advance?
5. **Payment: hold at checkout and charge after delivery?** How big a margin over the
   estimate, and what happens when the final total is above it?
6. **Cutoff: how long before the slot, and what can change after it?** Suggested: 22:00
   the night before; nothing changes after it in the skeleton.
7. **One identity with roles, or separate accounts?** Store operations, pickers and
   drivers need sign-in from Release 1.
8. **Geography in the sandbox.** No map tiles or geocoding are reachable. One store, one
   delivery area of seeded postcodes, and drops ordered by a seeded sequence keep routes
   real enough.
