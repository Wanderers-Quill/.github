# Wanderers-Quill
> ## PLANED-TO-BE

> A self-hosted, open-source, collaborative worldbuilding suite.  
> No surveillance. No vendor lock-in. Your worlds, your hardware, your rules.

---

## What is this?

Wanderer's Quill is a modular suite of web applications for building and
managing fictional worlds: timelines, maps, wikis, and whatever else a
worldbuilder needs. It is designed to be:

- **Self-hosted** — runs on your own hardware (a Raspberry Pi is enough).
- **Collaborative** — two or more people can edit the same world in real time.
- **Open source** — licensed under AGPL-3.0. Fork it, modify it, share it.
- **Modular** — a shared core with independent frontend modules.
- **Surveillance-free** — no telemetry, no analytics, no third-party tracking.

The project is in early development. The first milestone (v0.1) is a
collaborative timeline module.

---

## Repository map

| Repository | Purpose | Status |
| :--- | :--- | :--- |
| [`core`](https://github.com/wanderers-quill/core) | Shared backend: auth, world-data API, real-time sync (Yjs + Hocuspocus) | In development |
| [`timeline`](https://github.com/wanderers-quill/timeline) | Frontend module for chronological events | Planned |
| [`map`](https://github.com/wanderers-quill/map) | Frontend module for image-based maps | Future |
| [`wiki`](https://github.com/wanderers-quill/wiki) | Frontend module for lore pages | Future |
| [`docs`](https://github.com/wanderers-quill/docs) | Architecture, ADRs, deployment and operations guides | In development |

**Dependency direction:** every frontend module depends on `core`. Frontend
modules never depend on each other. All cross-module data flows through the
`core` API.

---

## Getting started

### For users (self-hosting)

> The v0.1 release is not ready yet. This section will be updated when it is.

Once v0.1 is released, self-hosting will be a single command:

```bash
docker compose up
```

No configuration file required. No external services. The app will start with
SQLite and a generated session secret.

### For contributors

1. Read [`docs/architecture/architecture.md`](https://github.com/wanderers-quill/docs/blob/main/architecture/architecture.md)
   to understand the system.
2. Read [`docs/architecture/invariants.md`](https://github.com/wanderers-quill/docs/blob/main/architecture/invariants.md)
   — these are hard rules, not suggestions.
3. Read [`CONTRIBUTING.md`](./CONTRIBUTING.md) for the workflow.
4. Pick an issue labeled `good first issue` and open a PR.

### For AI agents

If you are an AI agent working in this organization:

- Start with `docs/architecture/architecture.md` and `docs/architecture/invariants.md`.
- Treat every invariant as a hard constraint. If a change would violate one,
  stop and open an issue instead.
- Check the "Quick reference" table at the end of `invariants.md` before writing
  code.
- Update `architecture.md` (or write a new ADR) in the same PR that changes the
  architecture. Documentation updated "later" is documentation that never gets
  updated.

---

## Core principles

1. **The user owns their data.** No telemetry. No analytics. No third-party
   tracking. The only network calls the app makes are the ones required to
   function.
2. **Self-hosting is a first-class feature.** If it can't be deployed by one
   person on a Raspberry Pi, it's not done.
3. **Modularity over monoliths.** Each module is independently deployable. The
   core does not know about specific modules.
4. **Open source is not a marketing word.** AGPL-3.0, public roadmap, public
   decision records, public issues.
5. **Documentation is code.** It lives in the same repositories, is reviewed in
   the same PRs, and is updated in the same commits.

---

## License

Wanderers-Quill is licensed under the **GNU Affero General Public License v3.0
(AGPL-3.0)**. See [`LICENSE`](./LICENSE) for the full text.

In short: you can use, modify, and distribute this software freely, but if you
run a modified version as a network service, you must make the source available
to your users.

---

## Contact

- **Issues:** use the issue tracker of the relevant repository.
- **Security:** see [`SECURITY.md`](./SECURITY.md). Do not open public issues for
  security vulnerabilities.
- **Everything else:** open a discussion in the relevant repository.
```
