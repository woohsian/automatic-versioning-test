# automatic-versioning-test

Testing for automatic versioning

### Rules

Follows the following [rules](https://github.com/semantic-release/commit-analyzer/blob/master/lib/default-release-rules.js):

```js
// ESLint
{tag: 'Breaking', release: 'major'},
{tag: 'Fix', release: 'patch'},
{tag: 'Update', release: 'minor'},
{tag: 'New', release: 'minor'},
```

### Commit styles

Example [commits](https://github.com/conventional-changelog/conventional-changelog/tree/master/packages/conventional-changelog-eslint):

```
Tag: Short description (fixes #1234)

Longer description here if necessary
```