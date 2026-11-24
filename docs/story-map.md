# Story map

Jeff Patton's form. The backbone runs left to right in the order the work happens, from
setting up the store to putting things right; each release below it is a thin, usable
path end to end, not a component. Personas: [personas.md](./personas.md). *(seeded)*
marks a stand-in that is seeded data, not a built story. As a page:
[diagrams/primer.html](./diagrams/primer.html#map).

## Backbone

| # | Activity | Who | Steps |
| --- | --- | --- | --- |
| A1 | Run the store | Store ops | Set range and prices · Open slots · Set delivery area |
| A2 | Plan the shop | Customer | Check my postcode · Book a slot · Find products |
| A3 | Fill the basket | Customer | Add to basket · Choose substitutions · Check out |
| A4 | Change my mind | Customer | Amend the order · Cancel |
| A5 | Pick | Picker | Get the pick list · Pick and weigh · Substitute or mark missing · Pack for the van |
| A6 | Deliver | Driver | Load the van · Run the route · Hand over |
| A7 | Settle | Customer | Pay for what came · Hear what changed |
| A8 | Make it right | Support | Look up an order · Refund |

## R0 — Walking skeleton

One seeded store, one picker, one van: a weekly shop goes from slot to doorstep, with a
substitution on the way.

| Step | Stories |
| --- | --- |
| Set range and prices | *(seeded)* Range seeded: products, prices, some weighed |
| Open slots | *(seeded)* Hour slots seeded, a fixed number of orders each |
| Set delivery area | *(seeded)* One delivery area of seeded postcodes |
| Check my postcode | Enter a postcode; told if it's outside the area |
| Book a slot | See slots with space · Reserve a slot |
| Find products | Browse products by aisle |
| Add to basket | Add, change quantity, remove |
| Choose substitutions | Allow or refuse a substitute per item |
| Check out | Pay with a saved test card · Slot booked with the order |
| Get the pick list | The slot's orders as a pick list |
| Pick and weigh | Mark each line picked |
| Substitute or mark missing | Out of stock: substitute or mark missing |
| Pack for the van | Mark the order packed |
| Load the van | *(seeded)* One van, one driver, always on shift |
| Run the route | The slot's orders, in drop order |
| Hand over | Mark delivered |
| Pay for what came | Charged for what was picked |
| Hear what changed | Email: substitutions and missing items · Email: delivered |
| Look up an order | See an order and its timeline |

## R1 — Real slots

Slots are a scarce promise: held, priced, cut off and amendable.

| Step | Stories |
| --- | --- |
| Set range and prices | Staff sign in |
| Open slots | Capacity per slot from vans and pickers · Peak and off-peak slot prices |
| Set delivery area | Delivery area by postcode district |
| Book a slot | Reservation held two hours, then released · Slot full: nearest slots offered |
| Find products | Search |
| Add to basket | Basket kept when a reservation lapses · Minimum basket |
| Check out | Delivery charge by slot · Reservation lapsed: book again |
| Amend the order | Change items until the cutoff · Change the slot before the cutoff |
| Cancel | Cancel free before the cutoff |
| Get the pick list | Pick list released at the cutoff |
| Hear what changed | Reminder before a reservation lapses · Reminder before the cutoff |

## R2 — Real substitutions

Substitutions follow the customer's rules, and the door is where they're settled.

| Step | Stories |
| --- | --- |
| Choose substitutions | Pick a specific substitute · Rules: same brand other size, anything similar, none · A default rule for the whole order |
| Check out | Card held for the estimate plus a margin |
| Pick and weigh | Weighed items priced at the scale |
| Substitute or mark missing | Substitute suggested from the rule · Substitute charged no more than the original |
| Pack for the van | Totes by temperature: ambient, chilled, frozen |
| Load the van | Loaded in reverse drop order, cold kept cold |
| Hand over | Accept or reject each substitute · Rejected items go back on the van |
| Pay for what came | Charged after delivery at actual weights · Rejected and missing items not charged |
| Hear what changed | Substitutions sent before the van arrives |

## R3 — Trust and care

When it goes wrong, it's put right quickly, and the weekly shop gets easier.

| Step | Stories |
| --- | --- |
| Find products | Favourites and previous orders |
| Book a slot | Book my usual slot again |
| Run the route | Running late: customer told, new time |
| Hand over | ID check for age-restricted items · Nobody home: wait, then chilled and frozen go back |
| Pay for what came | Delivery pass: no delivery charge |
| Look up an order | Substitutions, rejections and refunds on the timeline |
| Refund | Refund a missing, damaged or short-dated item · Voucher for a missed slot |

## Later, not sliced yet

Recurring weekly order · Rapid delivery within the hour · Click and collect · Several
stores, nearest one serves · Promotions and multibuys · Loyalty card prices · Dietary
filters and nutrition · Product reviews · Bagless delivery · Slot waitlist
