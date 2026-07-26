<!--
Org-wide default PR template for @usestring.
A repo with its own .github/PULL_REQUEST_TEMPLATE.md overrides this.
-->

## Summary

<!--
What changed AND why. Lead with the problem — we can read the diff, but we can't reconstruct
the reasoning behind it. If you rejected an alternative approach, that's worth a line.
-->

## Testing

<!--
What you actually ran, not what could theoretically be run.
If you changed how a provider is called in the benchmark, say so explicitly — a provider in a
weaker mode than its peers invalidates the published numbers.
-->

## Notes for the reviewer

<!--
Optional. Anything that would otherwise cost the reviewer twenty minutes to work out:
a non-obvious constraint, a deliberate omission, a follow-up you're leaving for later.
Delete this section if there's nothing.
-->

---

- [ ] PR title follows [Conventional Commits](https://www.conventionalcommits.org/) (`feat:`,
      `fix:`, `chore:`, `docs:`) — it becomes the squash commit message, and drives the version
      bump in repos with release automation
- [ ] Read [CONTRIBUTING.md](https://github.com/usestring/.github/blob/main/CONTRIBUTING.md)
