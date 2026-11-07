# Contributing to FlowApps repositories

These are the defaults for every repository in the FlowApps organisation. A repository's own
`CONTRIBUTING.md` adds to these rules and wins where the two disagree.

## Branches

- Never commit to `main`. Every change reaches `main` through a reviewed pull request.
- Branch from the latest `main`: `feat/…`, `fix/…`, `docs/…`, `chore/…`, or
  `NNN-short-description` when the work belongs to issue `NNN`.
- Keep a branch to one feature or fix. Rebase onto `main` before asking for review if `main` has
  moved, so the merge cannot revert someone else's work.

## Commits

- Use [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `refactor:`,
  `docs:`, `test:`, `build:`, `ci:`, `chore:`. Mark breaking changes with `!` (`feat!:`).
- Sign every commit (SSH or GPG). Unsigned commits are not merged.
- One behaviour change per commit, with a message that says why, not only what.

## Pull requests

- Fill in the pull request template: the user-visible change, how you verified it, and how it
  ships.
- CI must pass. Run the repository's checks locally first (its README or `CONTRIBUTING.md` lists
  them).
- Add a test for every bug fix and every new rule in business logic.
- Screenshots or a short recording for any UI change, in both light and dark mode where the app
  has both.

## Standards that apply everywhere

- **Secrets never enter git.** No API keys, tokens, passwords, keystores or service-account files
  in code, tests, fixtures or commit history. Use the environment or the platform's secret store.
  If one is committed by mistake, tell the team at once: rotate it first, then clean up.
- **Arabic and English.** User-facing text goes through the repository's translation system where
  it has one. Layouts must work right to left: use `start`/`end`, not `left`/`right`.
- **Tenant isolation (FlowApps platform).** Every query that reads or writes customer data is
  scoped to the tenant on the server. Frontend checks are never the only protection.
- **Privacy.** A change to what data a product collects, stores or sends updates its privacy text
  and store listing in the same pull request.
- **Dependencies.** Add a dependency only when it earns its place, and say why in the pull request.
  Commit the lockfile.

## Security issues

Do not open an issue or pull request that describes a vulnerability. Follow
[SECURITY.md](./SECURITY.md).
