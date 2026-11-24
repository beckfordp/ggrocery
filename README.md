# gGrocery

A grocery-delivery application: customers book a delivery slot and shop, pickers pick in
store, drivers deliver in the slot. An application built on the Gluon platform as its own
repo; gshop, the exemplar the platform grew with, stays inside gluon.

Status: discovery. The domain, personas and story map are drafted; how gGrocery uses
gluon, its services and its frontends come next.

## Start here
- [Primer](./docs/primer.md): the domain in one sitting
  ([as a page](./docs/diagrams/primer.html)).
- [Personas](./docs/personas.md): the six people gGrocery serves.
- [Story map](./docs/story-map.md): the backbone and the release slices (R0–R3).
- [User stories](./docs/user-stories.md): the walking skeleton (R0) as stories.
- [Open questions](./docs/open-questions.md): what isn't decided yet.
- [ADRs](./docs/adr/): gGrocery's own decisions (none yet).

## What makes it more than gshop
gGrocery is e-commerce, as gshop is, with two differences that run through everything:

- **Inventory gets time-slot reservations.** Delivery is booked into one-hour slots with
  a capacity; a reservation holds a place in a slot while the customer shops.
- **The cart gets substitution rules.** Each basket line says what may stand in for it
  when it's out of stock at the pick; the customer settles substitutes at the door.

The [primer](./docs/primer.md#how-it-differs-from-gshop) has the detail, and a third
consequence: the price settles late.

## gluon as the substrate
gGrocery builds on what gluon already has rather than starting again:

- **Services:** gluon's Rust services (`services/*-rs`: user, payment, notification,
  order, catalog, cart, inventory, fulfilment).
- **Tools:** `tools/rust-service-template` for new services; `tools/gluon-kube` to run
  them in the sandbox.
- **Libraries:** `lib/gluon-rs` (HTTP, persistence, events, telemetry, testing).
- **Ways of working:** Conductor and its `workflow.md`, gluon's user-story format, ADRs,
  the contract harness (`tests/contract`) and the Playwright acceptance suite
  (`tests/acceptance`), the sandbox's export and save.

## Reuse is harvested
1. **As is** where a gluon service fits: gGrocery runs its own instance of it.
2. **Copied** where it needs changes: gGrocery copies the service into `services/` with a
   `gg-` prefix (`gg-inventory-service-rs`) and changes its own copy.
3. **Folded back** where a change is generic: gGrocery raises a change request in that
   service's gluon backlog (`services/<service>-rs/conductor/tracks.md`, `## Backlog`,
   "CR from ggrocery: …"), to be taken into the gluon service later.

Using as is and copying pull against each other: a copy is quick and free to change but
drifts from gluon; as is keeps one service but constrains gGrocery. Where the line falls
is open, to be settled here.

## Layout
```
ggrocery/
├── conductor/      product, tech stack, workflow, tracks
├── docs/           primer, personas, story map, user stories, open questions, ADRs
├── services/       gGrocery's services, own and gg- copies, each its own repo (gitignored here)
└── frontends/      gGrocery's frontends, each its own repo (gitignored here)
```

gGrocery lives in gluon's checkout at `apps/ggrocery`, its own repo, gitignored by gluon.

## License
MIT, as gluon: [LICENSE](./LICENSE). Every file in gGrocery and its service and frontend
repos that takes a comment starts with `SPDX-License-Identifier: MIT` in that comment,
after any shebang or doctype: Rust, TOML, YAML, Dockerfiles, shell, Python, SQL,
TypeScript, HTML (`// …`, `# …`, `-- …`, `<!-- … -->`). Markdown, JSON, lockfiles,
`.gitignore` and `LICENSE` don't take one. Nor do copied third-party files (they keep
their own licence, named in a NOTICE beside them) or generated and captured output. Each
repo carries its own `LICENSE`.

## In the sandbox
gluon's sandbox export carries gGrocery (`bin/lib/sandbox.py`, `SHARED_REPOS` and
`SANDBOX_REPOS`); from gluon on the laptop:

```sh
bin/sandbox-export --app ggrocery     # ggrocery-gluon.tar.gz: no Scala, no plans
```

`bin/sandbox-save` in the sandbox brings gGrocery's commits back.
