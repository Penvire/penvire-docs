# Penvire documentation

Cross-cutting documentation for Penvire: charter, architecture, glossary and architecture decision records. Build and tooling details stay in each repository's README.

## Repository map

```text
charter.md        why Penvire exists, scope, rules
architecture.md   how the system is built
GLOSSARY.md       domain vocabulary
adr/              decision records, numbered from 0001; never edited once accepted
guides/           later: operator and user documentation
```

## Development environment

Enter the environment with `devenv shell`, or run `direnv allow` once. It provides markdownlint and Vale (run as pre-commit hooks) and lychee. Always run tools through it.

Git hooks run automatically: a commit-msg hook rejects messages that are not Conventional Commits (the same rule as CI), and actionlint checks workflow files; markdownlint and Vale check Markdown.

Check links with `lychee .`. Run `vale <file>` or `markdownlint <file>` directly to see prose and style findings before committing.

## Rules

- Never push to `main`. Create a branch (`feat/`, `fix/` or `chore/`), push it and open a pull request. The maintainer merges.
- Pull requests are squash-merged. The PR title becomes the commit on `main`, so it must be a Conventional Commit; mark breaking changes with `!`.
- Commits are GPG-signed; `main` rejects unsigned commits.
- PR body: a one-paragraph summary, then a `## Test plan` section.
- Penvire never ships hand-written authentication.

## Agent docs

- [Issue tracker](docs/agents/issue-tracker.md): GitHub Issues for `Penvire/penvire-docs`
- [Triage labels](docs/agents/triage-labels.md)
- [Domain docs](docs/agents/domain.md): where the glossary and ADRs live

## Related repositories

- `~/Projects/penvire/prod/contracts`: [penvire-contracts](https://github.com/Penvire/penvire-contracts)
- `~/Projects/penvire/prod/backend`: [penvire-backend](https://github.com/Penvire/penvire-backend)
- `~/Projects/penvire/prod/clients`: [penvire-clients](https://github.com/Penvire/penvire-clients)
