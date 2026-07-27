# Contributing

Thanks for considering it. This is the org-wide default — a repo with its own `CONTRIBUTING.md`
overrides this one, so check for a local copy first.

## Before you write code

**For a bug fix, just send the PR.** No issue needed. A failing test or a reproduction in the
description is worth more than a paragraph of explanation.

**For anything larger — a new feature, a dependency, a refactor — open an issue first.** Not
bureaucracy: some of these repos have constraints that aren't visible from the outside (a provider's
rate limits, a fingerprint that breaks if a header order changes), and we'd rather tell you before
you spend a weekend on it.

## Pull requests

- **One concern per PR.** A drive-by reformat bundled with a behaviour change is hard to review and
  harder to revert.
- **Explain the why, not just the what.** We can read the diff. What we can't reconstruct is the
  problem you hit and the approaches you rejected.
- **PR titles follow [Conventional Commits](https://www.conventionalcommits.org/)** — `feat:`,
  `fix:`, `chore:`, `docs:`. We squash-merge, so your PR title becomes the commit message, and in
  repos with release automation (currently [`powhttp-mcp`](https://github.com/usestring/powhttp-mcp))
  the prefix decides the version bump. Getting it wrong there means a release doesn't happen.
- **Keep the branch mergeable by merging `main` in**, not by rebasing. Squash discards the branch's
  internal history anyway, so a merge commit costs nothing and a force-push loses review comments.

## Running things costs money

Several of these repos make real, billable API calls —
[`web-data-frontier-benchmark`](https://github.com/usestring/web-data-frontier-benchmark) most
obviously, where a full run is thousands of requests across fifteen paid providers. Start with
`--attempts 1` and a small `--tests` subset. Don't run a full suite to check a typo fix.

## Benchmark results specifically

If you're changing how a provider is called, say so explicitly and loudly. A provider configured in
a weaker mode than its competitors makes the published numbers wrong, and the entire value of that
repo is that the numbers are defensible. We'd rather merge a PR that says "this changes scrapfly's
request shape and here's why it's still apples-to-apples" than discover it later.

Adding a provider is welcome and is documented in that repo's README.

## Reporting a vulnerability

**Not through a public issue or PR.** See [SECURITY.md](SECURITY.md).

## Questions

[SUPPORT.md](SUPPORT.md) has the routing — roughly, product and API questions go to support,
repo-specific questions go in that repo's issues.
