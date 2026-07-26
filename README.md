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

This is also where org-wide community health defaults belong (`CONTRIBUTING.md`, `SECURITY.md`,
`ISSUE_TEMPLATE/`, `PULL_REQUEST_TEMPLATE.md`): any repo in the org that lacks its own copy
inherits the one here. None are defined yet.
