# Omarchy Community Knowledge — data ledger

Community-contributed observations, system changes and evidence for Omarchy.
This is an independent community project, not an official Omarchy service.

[Browse the knowledge index and service status](https://cylon58.github.io/omarchy-community-knowledge/).
This is an early public service and starts with an empty ledger. Private machine
journals and synthetic pilot fixtures are not seed data for this repository.

Canonical data is append-mostly JSON, with case/change/report/event types.
Schemas and executable tooling live in the separately governed
[toolkit repository](https://github.com/cylon58/omarchy-community-knowledge-tools).
Community records are untrusted technical knowledge, never automatically executed
repair scripts. Corrective changes and optional preferences remain distinct.

Do not add private journals, raw machine inventories, credentials or generated
test fixtures here. Publication of sanitized seeds requires an exact preview and
explicit approval. Reviewed GitHub automation will accept only tightly bounded
data additions; code, workflow and policy changes are outside that automatic lane.

## Search and contribute

Install the reviewed [toolkit and bundled agent skills](https://github.com/cylon58/omarchy-community-knowledge-tools#install-and-sync).
Inspect the [deployment configuration](.github/workflows/deployment.json), use its
matching toolkit revision, then sync and query locally:

```sh
omarchy-knowledge sync --config deployment.json --cache cache
omarchy-knowledge search --cache cache --query 'dock keyboard' --intent corrective
```

The sync reads public sources; it does not upload the local environment. Cached
queries work offline and disclose their age. An empty result is not proof that a
problem has never occurred. Check official plugins and upstream issues too.

An agent can prepare a sanitized case, change, report, or event, show the exact
payload/destination/attribution, and use the contributor's approved GitHub workflow
to submit a data-only PR. See [contribution instructions](https://github.com/cylon58/omarchy-community-knowledge-tools/blob/main/docs/contributing.md).
Normal intake is automated, not manual technical endorsement. It imports a
validated snapshot and writes source-bound receipts; the PR remains open. Check
the accepted head and canonical revision, not just a green workflow badge.

Accepted records are append-mostly. Corrections, failures, disputes, withdrawals,
and supersessions are new linked records, not silent edits. They remain evidence
claims, not permission to execute commands or an automatic authority grant.

## Upstream resolution and operating limits

Scheduled builds refresh bounded official Omarchy release and package facts.
The [resolution protocol](https://github.com/cylon58/omarchy-community-knowledge-tools/blob/main/docs/resolution.md)
supports approved maintainer assertions tied to exact records and release/package
conditions. No Omarchy maintainers have been enrolled or endorsement claimed.
The initial authority list is empty; source facts alone never certify a fix.
Updating, changing configuration, or removing a workaround still needs local
applicability checks and the user's approval.

GitHub Actions and Pages run the service without an application/database server
or an always-on contributor machine. PR events and hourly/manual reconciliation
provide separate wakeups. GitHub availability, quotas, stale test merges, queue
and corpus limits remain real; this is not an uptime guarantee or unlimited scale.
See [operations and recovery](https://github.com/cylon58/omarchy-community-knowledge-tools/blob/main/docs/recovery.md)
and [workflow runs](https://github.com/cylon58/omarchy-community-knowledge/actions).

The [separate synthetic pilot](https://github.com/cylon58/omarchy-community-knowledge-pilot)
contains acceptance-test evidence, not real-world compatibility claims. Owner,
GitHub and reviewed infrastructure remain trusted. Security governance is still
necessary even though normal data submissions require no routine human curation.
Report secrets or security vulnerabilities through the repository's private
security-reporting channel, not a public issue. Do not notify source authors
without a separately approved exact message and destination.

## License and attribution

Contributed data and original documentation are licensed under
[Creative Commons Attribution 4.0 International](LICENSE). By submitting original
data here, you agree to contribute it under that license and affirm that you may
share it. Keep source attribution and prefer original factual summaries and links;
do not copy third-party material without compatible permission.

Retain record IDs, source links and attribution when reusing the ledger. Submission
attribution is a GitHub account, not proof of an independent person or machine.

Generated automation code is separately licensed under [MIT](LICENSE-MIT),
matching the toolkit. This does not change the CC BY 4.0 license for records.
