# User Stories — R0, walking skeleton

From the [story map](./story-map.md), release R0: one seeded store, one picker, one van;
a weekly shop goes from slot to doorstep, with a substitution on the way. Personas:
[personas.md](./personas.md).

Status: draft, first pass. Which service does each task is decided as the stories start;
open questions that change them are in [open-questions.md](./open-questions.md). R1–R3
are written from the map once R0 is under way.

## US-1 — Seed a store world
As the platform, the skeleton starts with a store's range, a grid of slots, one delivery
area, one picker and one van seeded, so every side can be exercised before store
operations has screens.
- Seeded data, not features: no staff sign-in, slots always open to their capacity.
- The area is a set of seeded postcodes (open question 8).

### Tasks
- [ ] US-1.1: seeded range: products with names, prices and aisles; some sold by weight
- [ ] US-1.2: seeded slots: one-hour slots over the next week, a fixed capacity each
- [ ] US-1.3: one delivery area of seeded postcodes
- [ ] US-1.4: one picker and one van with a driver, always on shift

## US-2 — Check my postcode
As a customer (Priya), I enter my postcode and learn whether gGrocery delivers there,
so I don't build a basket that can't reach me.
- Outside the area: told so, no slots shown.

### Tasks
- [ ] US-2.1: is a postcode in the delivery area

## US-3 — Book a slot
As a customer, I see the slots with space and reserve one, so I know when my shop will
arrive before I fill the basket.
- Full slots are shown as full, not hidden.
- A reservation holds one place in the slot's capacity (open questions 1 and 2).

### Tasks
- [ ] US-3.1: slots for the coming week, with space left
- [ ] US-3.2: reserve a slot; capacity goes down by one

## US-4 — Find products
As a customer, I browse the range by aisle, so I can find what I usually buy.
- Weighed items show a price per kg and an estimated price per item.

### Tasks
- [ ] US-4.1: products by aisle, with prices

## US-5 — Fill a basket, with substitution choices
As a customer (George), I add items, change quantities, remove them, and say for each
whether a substitute is allowed, so I get what I want or nothing.
- Default: substitute allowed; the customer can refuse per item.

### Tasks
- [ ] US-5.1: add, change quantity, remove
- [ ] US-5.2: allow or refuse a substitute per basket line

## US-6 — Check out
As a customer, I pay with a saved test card and my reserved slot is booked with the
order, so the shop is on its way.
- Payment is taken for the estimated total (held-then-charged is R2; open question 5).

### Tasks
- [ ] US-6.1: checkout creates the order for the reserved slot, with a delivery charge
- [ ] US-6.2: payment for the estimated total

## US-7 — Pick an order
As a picker (Marek), I get the slot's orders as a pick list and work through it, marking
each line picked, substituted or missing, so the order leaves the store as complete as
the shelf allows.
- Out of stock and substitute allowed: the picker records what was picked instead.
- Out of stock and substitute refused: marked missing.

### Tasks
- [ ] US-7.1: the slot's orders as a pick list
- [ ] US-7.2: mark a line picked
- [ ] US-7.3: substitute a line, or mark it missing, by the customer's choice
- [ ] US-7.4: mark the order packed

## US-8 — Deliver the slot
As a driver (Sam), I see the slot's orders in drop order and mark each delivered, so the
customer gets their shop and the order can be settled.

### Tasks
- [ ] US-8.1: the slot's packed orders, in drop order
- [ ] US-8.2: mark an order delivered

## US-9 — Pay for what came
As a customer, I'm charged for what was picked, not what I ordered, so missing items
cost me nothing.

### Tasks
- [ ] US-9.1: final charge from the picked lines; missing lines not charged

## US-10 — Hear what changed
As a customer (George), I'm told by email about substitutions and missing items, and when
the order is delivered, so nothing at the door is a surprise.

### Tasks
- [ ] US-10.1: email listing substitutions and missing items once the order is packed
- [ ] US-10.2: email when delivered, with the final charge

## US-11 — Look up an order
As support (Lin), I see an order and its timeline: ordered, picked, substituted,
delivered, charged; so I can answer a customer.

### Tasks
- [ ] US-11.1: order timeline for support
