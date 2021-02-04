# automatic-versioning-test

Testing for automatic versioning

### Environment variables

Copy `.env.example` to `.env` with relevant `GIT_CREDENTIALS` (assuming write permissions available)

Other authentication options available [here](https://github.com/semantic-release/semantic-release/blob/master/docs/usage/ci-configuration.md#authentication).

### Local testing

Use this to preview all changes (dry-run)
```
npm run release:test
```

### Running on CI

Use this to automatically bump the package json, update changelog, commit and push
```
npm run release:generate
```

### Rules

Uses the following [rules](https://github.com/semantic-release/commit-analyzer/blob/master/lib/default-release-rules.js):

```js
// ESLint
{tag: 'Breaking', release: 'major'},
{tag: 'Fix', release: 'patch'},
{tag: 'Update', release: 'minor'},
{tag: 'New', release: 'minor'},
```

### Commit messages

Example [commits](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-eslint):

```
Tag: Short description (fixes #1234)

Longer description here if necessary
```

### Pull request merging

Need to use the `rebase` strategy for completing pull requests

## Additional Info

### Plugin delegation

- `@semantic-release/commit-analyzer`: Analyses commits and decides which type of version to bump
- `@semantic-release/release-notes-generator`: Generate notes based on commits
- `@semantic-release/changelog`: writes to changelog
- `@semantic-release/npm`: does actual version bump on package.json and package-lock.json
- `@semantic-release/git`: creates commit message and pushes, finalising all the above changes
