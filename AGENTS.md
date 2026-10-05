# AGENTS.md

## Communication

Be concise, precise, and information-dense in your communication.
No flattery.
No emojis.
Do not waste my time or your tokens.

## Tools

Use CLI tools instead of complicated MCP servers etc. whenever possible.

## Work products

Make as much of your work reproducible as you can. Store artifacts (files, etc.) and scripts for how to make use of them. Always make a directory (even a temporary one) for each group of files, unless one has already been specified.
Always respect .gitignore

## Git

Do not claim credit on commit messages and PR descriptions.
NEVER amend commits. Always create new commits. No exceptions.
NEVER rebase. Use merge commits to integrate changes.

## This repository

merits catalogs merits and demerits of AI models and agents: observed behaviors, the public databases that record them, and the taxonomies that name them.

For now the repository holds documentation only. This will change.

## Catalog conventions

These apply to `sources.md` and to any future catalog file or dataset.

Every entry carries: name, maintainer, URL, a terse description, and maintenance status.

Do not state a count, date, or version you have not traced to a primary source. Mark anything unverified inline with `[?]` and say what is unverified. An inferred figure is not a published figure; label it.

Never silently drop a resource because it is dead. List defunct, stale, frozen, and non-public resources and flag them as such. Absence of a resource is itself a finding — record gaps explicitly rather than leaving them implied.

Distinguish the kinds of artifact. An incident log, a risk taxonomy, a behavior/eval repository, and a capability threshold are four different things and should not be merged into one list without saying which is which.

Prefer primary sources. Where a figure rests only on a secondary source, say so in the entry.
