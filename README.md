# workflows

Reusable GitHub Actions workflows shared by the [@douglasjunior](https://github.com/douglasjunior) repositories.

## Commit authors

Checks the commits of a pull request or push:

- No commit may be authored, committed or co-authored by a known AI agent, or carry an agent signature in its message.
- On pull requests opened by the repository owner, every author and committer must be one of the owner's identities.

```yaml
name: Commit authors

on:
  pull_request:
  push:
    branches: ['**']

permissions:
  contents: read

jobs:
  commit-authors:
    name: Commit authors
    uses: douglasjunior/workflows/.github/workflows/commit-authors.yml@v1
```

The check reports as `Commit authors / Check commit authors`, which is the name to require in a ruleset.

## Versioning

Callers pin the major tag (`@v1`). Compatible changes move `v1`; breaking changes get a new major tag.
