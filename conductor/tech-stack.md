# Tech Stack — gGrocery

- **Services:** Rust, from gluon's `tools/rust-service-template` and `lib/gluon-rs`, as
  the platform's Rust ports (axum, sqlx and Postgres, Kafka with the Debezium outbox).
  Each its own repo under `services/`, with its own conductor and tech stack.
- **gluon services:** used as they are or copied as `gg-` services
  ([reuse](../README.md#reuse-is-harvested)).
- **Frontends:** React, TypeScript and Vite, as gshop (gluon ADR 0006). Each its own repo
  under `frontends/`.
- **Runtime:** gluon's Kubernetes setup (Helm chart `infra/k8s/gluon`); gluon-kube in the
  sandbox, OrbStack on the laptop. gGrocery runs in its own cluster, `ggrocery-local`, as
  gshop runs in `gluon-local`. gluon-kube serves only `gluon-local` today, so a
  configurable cluster name is a change request to gluon-kube; namespaces, for several
  apps at once, come later.
- **Acceptance:** Playwright BDD, as gluon's `tests/acceptance` (gluon ADR 0023).
- **This repo:** documentation; no code of its own yet.
