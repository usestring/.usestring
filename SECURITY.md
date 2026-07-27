# Security Policy

## Reporting a vulnerability

**Please do not report security vulnerabilities in a public GitHub issue, pull request, or
discussion.** A public report tells everyone else about the problem before there's a fix.

Email **[support@usestring.ai](mailto:support@usestring.ai)** with:

- the repository and version, commit, or endpoint affected
- a clear reproduction — the smallest one that demonstrates it
- what an attacker gets out of it, if that isn't obvious

We'll acknowledge the report, work the fix privately, and tell you when it ships. If you'd like
credit in the release notes, say so and we'll include it; if you'd rather stay anonymous, that's
fine too.

## Scope

This is the org-wide default and covers the repositories under
[@usestring](https://github.com/usestring), plus our hosted services — the Web Access API
(`request.usestring.ai`), the hosted MCP endpoint (`mcp.usestring.ai`), and the portal
(`portal.usestring.ai`).

A repository with its own `SECURITY.md` overrides this file for that repository.

## Testing against our own API

Our product fetches arbitrary URLs on your behalf, so the line between "using the API" and
"attacking it" can be genuinely unclear. Two asks:

- **Test against your own infrastructure, or ours.** Don't use a String API key to attack a third
  party and call it research.
- **Rate-limit yourself.** If you're probing for a denial-of-service condition, tell us first rather
  than demonstrating it against production.

If you're unsure whether something is in scope, email and ask — we'd much rather have that
conversation up front.

## What we ask in return

Give us a reasonable window to ship a fix before publishing. We don't currently run a paid bug
bounty; we do respond, we do fix things, and we do give credit.
