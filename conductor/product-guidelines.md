# Product Guidelines — gGrocery

## Language
Use the domain's words ([primer glossary](../docs/primer.md#words-the-domain-uses)):
slot, slot reservation, capacity, cutoff, amend, substitution rule, substitute, pick
list, tote, weighed item, drop. The same word in stories, APIs, events and UI.

## Stories
- The [story map](../docs/story-map.md) is the source; a story that changes the map
  changes the map first.
- Stories are written per release slice, in gluon's `docs/user-stories.md` format
  (US-N, tasks naming the service).

## Reuse
- [Reuse is harvested](../README.md#reuse-is-harvested): gluon services as they are where
  they fit; a `gg-` copy where gGrocery needs changes; generic changes raised as change
  requests in the gluon service's backlog.

## Repo hygiene
- Commits: `<type>(<scope>): <description>`, one line.
- Never commit `.idea/` or `.claude/`.
