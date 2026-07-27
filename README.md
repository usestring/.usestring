# .github

Org-wide GitHub configuration for [@usestring](https://github.com/usestring).

| Path | What it does |
| --- | --- |
| [`profile/README.md`](profile/README.md) | Renders as the org's public profile at [github.com/usestring](https://github.com/usestring). |
| [`.github/workflows/gitleaks.yml`](.github/workflows/gitleaks.yml) | Secret scanning on pushes and PRs to `main`. |
| [`.gitleaks.toml`](.gitleaks.toml) | Gitleaks ruleset. Loaded from the base branch on PRs, so a PR can't weaken its own scan. |

GitHub reads the profile README only from a repo named exactly `.github`, at exactly
`profile/README.md` — this repo was previously named `.usestring`, which is the *user*-profile
convention (repo name == username) and gets no special treatment on an org.

## Org-wide community health defaults

Every repo in the org that does **not** have its own copy of one of these files inherits the one
here. Adding a local file to a repo overrides the default for that repo only.

| Path | Applies to |
| --- | --- |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | How to contribute: when to open an issue first, PR expectations, Conventional Commit titles. |
| [`SECURITY.md`](SECURITY.md) | Vulnerability reporting via `support@usestring.ai`, and scope across repos + hosted services. |
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) | Expected conduct and the enforcement contact. |
| [`SUPPORT.md`](SUPPORT.md) | Where a question goes: repo issue vs. private support vs. security. |
| [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md) | Default PR body. |
| [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE) | Bug and feature forms, plus `config.yml` contact links. |

Two rules worth knowing before editing these:

- **`ISSUE_TEMPLATE/` is all-or-nothing.** If a repo has *anything* in its own
  `.github/ISSUE_TEMPLATE/`, GitHub ignores this entire directory for that repo rather than merging
  the two. Every other file overrides individually.
- **A `LICENSE` cannot be defaulted.** GitHub deliberately excludes it, because the license has to
  travel with the code when a repo is cloned or packaged. Licenses stay per-repo.

Lookup order within a repo is its own `.github/` folder, then its root, then `docs/`, and only then
this repo. Note that this only works while `.github` is **public** — a private default-files repo is
not supported.
