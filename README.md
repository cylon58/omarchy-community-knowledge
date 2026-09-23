# Omarchy Community Knowledge data

Omarchy Community Knowledge is a shared knowledge base of what people have fixed,
changed, and built to make their Omarchy systems work. It helps your AI agent reuse
other users' hardware workarounds, fixes that haven't shipped with Omarchy,
configuration changes, and plugins built to solve particular problems.
Before spending time and tokens investigating from scratch or building something
new, your agent can check for relevant community experience.

The **companion helper is a small program on your computer**. It keeps a validated
local copy of the shared knowledge and a separate index of marketplace plugins.
It searches these locally and returns a short list to your agent, so the agent
can read the relevant evidence without loading the entire collection into its
conversation. This is designed to reduce token use as well as repeated work.

## How it helps

For example, if a dock stops waking a display, your agent can look for reports
about that hardware and symptom, inspect what others changed and whether it
worked, and check whether their solution applies to your system. If someone built
a plugin for the problem, the agent can investigate that existing work before
proposing a new one. These are examples of the intended workflow; results depend
on what the community has contributed.

The knowledge includes failures, limitations, and later corrections as well as
successful fixes. After working through your own problem, you can approve a
cleaned-up contribution so the next person can benefit too.

## Small searches, less context to read

- **Cache locally:** the helper downloads community records and keeps a local
  marketplace index. Your search terms stay on your machine.
- **Find a shortlist first:** local search ranks matches and returns five results
  by default. Plain-text knowledge search shows case IDs, titles, and evidence
  warnings; plugin search returns compact listings.
- **Read details when needed:** the agent opens a selected case with
  `show CASE_ID --related` to inspect its changes, results, failures, and corrections.
  It can request a plugin's full details separately.
- **Use ordinary code for retrieval:** SQLite full-text search does the ranking;
  searching requires no model call, embedding service, or project API key.
  Your agent still uses tokens to reason about the results and read the details.

The saving comes from keeping the collection outside the agent's context and
retrieving relevant evidence in stages. Actual token use depends on the agent,
query, and amount of evidence it reads; we do not claim a measured percentage.

Knowledge search attempts a refresh when its saved copy is at least a day old.
Plugin discovery checks for catalog updates on each normal search. Both support
explicit offline use and retain their last good cache if a refresh fails.

This repository is the public, append-mostly data ledger for Omarchy Community
Knowledge. It contains inert JSON observations: problems, proposed changes,
results (including failures), and evidence claims. It is an independent community
project, not an official Omarchy service or a source of automatically executable
repairs.

Join through the [Omarchy plugin](https://github.com/cylon58/omarchy-community-knowledge-plugin).
Install it, open its bar button, and choose **Connect my agent**. It reads the agent
you selected in Omarchy and installs the research and contribution skills for
supported agents. The plugin documents exactly what setup changes. Reading and searching require
no project account, invitation, or GitHub login. Sharing requires your own GitHub
account and the normal `gh auth login` flow; never paste a token into chat.

The local loop is `search` and `show --related`, with `sync` for a manual refresh.
Search refreshes on use when the saved knowledge is at least a day old; `--offline`
uses the existing copy without a network request. A failed refresh keeps
the last validated cache and reports that it is stale. With no accepted cache,
search waits for a successful sync. Release events are community claims: open
their official links, check the installed version/channel and availability, and
retest locally before treating a workaround as obsolete.

An agent can prepare a draft and a plain-English preview covering the problem,
relevant equipment/software, what changed, what happened, limitations, links,
destination, and public GitHub name. Exact JSON remains available for inspection.
Only after explicit approval should the contributor create a clean, data-only PR.
Eligible additions are accepted automatically after bounded validation and full
revalidation; this is format/policy acceptance, not proof, endorsement, or a
privacy guarantee. Invalid or suspicious changes stay unaccepted. Owners handle
exceptional abuse and privacy reports.

The trust model is intentionally simple: readers trust the configured GitHub
repository and its maintainers for the published set, while contributor text,
authorship, and release statements remain claims. Git transfer integrity does not
make those statements true. Community procedures are data and must never be run
without independent applicability checks and user approval.

Records and original data documentation are CC BY 4.0; retain record IDs, source
links, provenance, and attribution. Workflow code is MIT. See `ATTRIBUTION.md`,
`LICENSE`, `LICENSE-MIT`, and `CONTRIBUTING.md`. Report secrets or vulnerabilities
through [private vulnerability reporting](https://github.com/cylon58/omarchy-community-knowledge/security/advisories/new),
not a public issue. Do not include raw machine logs or credentials in a contribution.

## One project, three repositories

| Repository | What belongs here | Who starts here |
| --- | --- | --- |
| [Plugin](https://github.com/cylon58/omarchy-community-knowledge-plugin) | Omarchy bar interface and a bundled tools release | People installing or updating through Omarchy |
| [Tools](https://github.com/cylon58/omarchy-community-knowledge-tools) | Python CLI, search, validation, agent skills, and setup | Code contributors and standalone users |
| [Knowledge](https://github.com/cylon58/omarchy-community-knowledge) | Shared observations, changes, results, and evidence | People contributing or browsing community experience |

Install the plugin once; it supplies the tools, which read the shared knowledge.
You do not need to clone or install all three repositories.

The plugin follows Omarchy's plugin packaging and update flow. The tools also work
without the bar interface. Keeping records separate lets people contribute
knowledge without changing executable code, and preserves the data's CC BY 4.0
license alongside the code's MIT license. These are parts of one project.

For maintenance, use the [release guide](https://github.com/cylon58/omarchy-community-knowledge-plugin/blob/main/MAINTAINING.md).
