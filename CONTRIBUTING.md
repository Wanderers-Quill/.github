# Contributing to Wanderers-Quill

Thanks for your interest in contributing. This document explains how to propose
a change, what we expect from a pull request, and where to find the details.

> **Before you start:** Read [`docs/architecture/architecture.md`](https://github.com/wanderers-quill/docs/blob/main/architecture/architecture.md)
> and [`docs/architecture/invariants.md`](https://github.com/wanderers-quill/docs/blob/main/architecture/invariants.md).
> The invariants are hard rules, not suggestions.

---

## How to propose a change

### For bugs and small fixes

Open an issue first if the bug is not already reported. For a one-line typo fix,
you can open a pull request directly.

### For features and larger changes

**Open an issue before writing code.** Describe what you want to change and why.
A maintainer will respond with whether the change fits the project's scope and
architecture. This avoids the situation where you spend hours on a PR that
cannot be merged.

If the change touches an invariant or the architecture, it also requires an ADR
(see `docs/architecture/adr/`). The ADR and the code change go in the same PR.

---

## Local development

See [`docs/development/setup.md`](https://github.com/wanderers-quill/docs/blob/main/development/setup.md)
for the full setup guide. The short version:

1. Clone `core` and `timeline`.
2. `cp .env.example .env` in `core`.
3. `docker compose up -d postgres` in `core`.
4. `pnpm install` in both repositories.
5. `pnpm db:migrate && pnpm db:seed` in `core`.
6. `pnpm dev` in `core` and in `timeline`.
7. Run tests: `pnpm test` in each repository.

---

## Pull request checklist

Every PR must include:

- **Tests** for new behavior (per invariant I-17 and I-18).
- **Documentation update** if the change affects architecture, invariants, or
  setup (per invariant I-19).
- **A passing CI run.** No PR merges with failing tests.
- **A clear description** of what changed and why.

Keep PRs small and focused. A PR that changes three unrelated things is harder
to review and harder to revert if something goes wrong.

---

## Commit messages

Use clear, descriptive commit messages. We do not enforce a formal convention,
but a commit message should answer: what changed, and why?

Good: `fix: prevent duplicate events on reconnect`
Bad: `fix stuff`

---

## What we do not accept

- Dependencies that are incompatible with AGPL-3.0 (see invariant I-15).
- Changes that violate an invariant without an accompanying ADR.
- PRs that add features outside the current milestone without prior discussion.

---

## Security issues

**Do not open public issues for security vulnerabilities.** See
[`SECURITY.md`](./SECURITY.md).

---

## Code of conduct

Be respectful. We do not have a formal Code of Conduct file yet, but the
expectation is simple: treat others as you want to be treated. Harassment,
personal attacks, and dismissive behavior are not welcome.

---

## Questions?

Open a discussion in the relevant repository. For general questions about the
project, use the `core` repository's Discussions tab.
