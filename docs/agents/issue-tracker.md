# Issue tracker: GitHub

GitHub Issues and pull requests are the canonical public tracker for platform work.

## Conventions

- Use one GitHub Issue per independently deliverable change.
- Link implementation pull requests to their originating Issue.
- Record triage state with the repository labels documented in `triage-labels.md`.
- Keep decisions and discussion on the Issue or pull request so outside contributors can follow them.

## Local planning

Files under `.scratch/` may be used for temporary private planning, prototypes, or working notes. They are never the canonical issue tracker and must not be cited as the public record of a decision.

## Skill operations

- When a skill says to publish to the issue tracker, create a GitHub Issue in this repository.
- When a skill says to fetch a ticket, read the referenced GitHub Issue and its linked pull requests.
- If GitHub access or the repository remote is unavailable, stop and ask rather than silently substituting a `.scratch/` file.
