# The domain in one sitting

A grocery order is a promise made days ahead and kept in a single hour: the right food,
fresh and cold where it should be, at the door inside the slot. Between the promise and
the door, the shelf gets a vote. Items run out, chicken weighs what it weighs, and the
customer's rules decide what stands in for what's missing.

As a page: [diagrams/primer.html](./diagrams/primer.html).

## How it differs from gshop

gshop is gluon's e-commerce exemplar: browse, basket, checkout, pick and ship. A grocery
delivery service looks the same until three things bite.

| | gshop | gGrocery |
| --- | --- | --- |
| **Delivery** | Shipped when ready | Booked into a one-hour **slot** before shopping; each slot has a capacity, and a **reservation** holds a place in it while the basket fills, then lapses |
| **Out of stock** | Can't be ordered | Found at the pick; each basket line carries a **substitution rule** (no substitute, anything similar, a chosen alternative), settled at the door |
| **Price** | Known at checkout | Settles late: weighed items and substitutions mean the card is **held** for an estimate and **charged** for what was delivered |

## The sides

| Side | Wants |
| --- | --- |
| **Customer** | The whole week's shop in one delivery, at a time they're home, with nothing important missing. Judges the service by what's substituted and how. |
| **Store operations** | Sets the range and prices, and how many orders each slot can take from the pickers and vans on shift. |
| **Picker** | Walks the store with a pick list in aisle order, weighs, substitutes by the customer's rules, and packs by temperature. |
| **Driver** | Runs a van route of drops within the slot, settles substitutions at the door and checks ID for age-restricted items. |

## Where the money goes

An illustrative weekly shop. Real grocers' figures vary; slot charges from free to about
£7 and minimum baskets around £40 are common.

| Line | When | Amount |
| --- | --- | ---: |
| Basket, estimated: 42 items, 4 of them weighed | Checkout | £84.60 |
| Delivery, Thursday 18:00–19:00 (peak) | Checkout | £3.50 |
| **Estimated total** | Checkout | **£88.10** |
| *Held on the card: the estimate plus 10% for weights and substitutions* | Checkout | *£96.91* |
| Chicken thighs weighed 1.12 kg, estimated 1.00 kg | Pick | +£0.84 |
| Fresh basil out of stock, no substitute allowed: missing | Pick | −£0.85 |
| Oat milk 1 L out; 2 L substituted at the 1 L price | Pick | £0.00 |
| Paneer substituted with tofu; rejected at the door | Door | −£2.10 |
| **Charged after delivery** | After the door | **£85.99** |

The rest of the hold is released. A basket under the minimum pays a small-basket charge
or can't be checked out.

## An order's life, against the slot

1. **Mon — slot reserved** (customer). Thursday 18:00–19:00 has space; it's held for the
   customer for a couple of hours while they shop.
2. **Mon — basket built** (customer). Each line gets a substitution rule; weighed items
   are priced at an estimate.
3. **Mon — checked out** (customer). Over the minimum basket; the card is held for the
   estimate plus a margin; the slot is booked.
4. **Tue–Wed — amended** (customer). Items added or removed, even the slot changed,
   until the cutoff the night before.
5. **Thu 10:00 — pick list released** (picker). The slot's orders, merged and sorted into
   aisle order, split into ambient, chilled and frozen totes.
6. **Thu — picked** (picker). Weighed items priced at the scale; an empty shelf means a
   substitute by the customer's rule, or missing.
7. **Thu 17:15 — loaded** (driver). Totes go on the van in reverse drop order, cold kept
   cold.
8. **Thu 17:30 — told what changed** (platform). Substitutions and missing items, and a
   narrower arrival time, before the van arrives.
9. **Thu 18:20 — at the door** (driver). Substitutes accepted or handed back; ID checked
   for alcohol; signed for.
10. **Thu 19:00 — charged** (platform). For what was delivered, at actual weights; the
    rest of the hold released; receipt sent.
11. **Later — put right** (support). Damaged, short-dated or missing items refunded.

## Where it goes wrong

| What happens | Usual handling |
| --- | --- |
| The slot the customer wants is full | Show the nearest slots with space; some grocers offer a waitlist |
| The reservation lapses before checkout | Slot released for others; basket kept; customer books again |
| An item is out of stock at the pick | Substitute by the customer's rule, or mark it missing; missing items aren't charged |
| A substitute costs more than the original | Usually charged at the original's price |
| Customer rejects a substitute at the door | Driver takes it back; not charged |
| Weighed item comes out heavier or lighter | Charged at actual weight, often within a tolerance |
| No ID, or under age, for alcohol | Age-restricted items go back on the van; not charged |
| The van is running late | Customer told with a new time; a missed slot may earn a voucher |
| Nobody home | Wait a few minutes, call; chilled and frozen go back; delivery charge usually kept |
| Damaged or short-dated item found after delivery | Support refunds the item, often without a return |

## Words the domain uses

- **Slot**: a delivery window, usually an hour, on a given day. Priced by demand: peak
  evenings cost more.
- **Slot reservation**: a place in a slot held for one customer for a short time while
  they shop; it lapses unless they check out.
- **Capacity**: how many orders a slot can take, set by vans, drops per route and
  pickers on shift.
- **Cutoff**: the last moment an order can be amended, typically the night before the
  slot.
- **Amend**: changing a booked order (items, quantities, even the slot) before the cutoff.
- **Substitution rule**: what the customer wants if an item is out: no substitute,
  anything similar, or a chosen alternative.
- **Substitute**: the item picked in place of one that's out of stock; accepted or
  rejected at the door.
- **Pick list (pick walk)**: a slot's orders merged into one route through the store, in
  aisle order.
- **Tote**: the crate an order is packed into; one per temperature zone, often several per
  order.
- **Temperature zone**: ambient, chilled or frozen. Kept apart from pick to door.
- **Weighed item (catch weight)**: sold by weight, priced at an estimate until it's on the
  scale: meat, fish, loose fruit.
- **Drop**: one delivery on a van route.
- **Minimum basket**: the smallest order that can be checked out, or that avoids a
  small-basket charge.
- **Age-restricted item**: alcohol and the like: ID checked at the door, handed back if it
  fails.
- **Short-dated**: close to its use-by date. Grocers promise a minimum life on delivery.
