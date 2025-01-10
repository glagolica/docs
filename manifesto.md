Some small principles we should follow to end up with a good product:

- Overcommunicate;
- Make hard tasks simpler by leaving notes here and there;
- Enjoy the development, work on things you want to work on;
- Clean up things you consider mess;
- You don't have to be formal on communication, simple and short replies;
- Make smaller commits.

# Recommendations

## Commits

When developing a product, we should use [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) to differ commit meanings,
below I listed few of the details regarding convention.

1. We have following types of commits:

- `feat:` - Related to freshly added features or changes that were never present in Glagolica's ecosystem before
- `fix:` - Big and tiny fixes for every sort of problem: code style, bug, formatting etc.
- `perf:` - Performance-related improvements. Those include smaller bundle size, faster execution times and _shorter code_.
- `docs:` - Every sort of documentation: comments, doc comments, manuals, README.md, CONTRIBUTING.md, LICENSE etc.
- `test:` - Generally e2e and unit tests. For test commits, use private repositories.

2. We have following scopes:

- `(markdown)` - Markdown parser to AST
- `(pdf)` - PDF generator related things
- `(html)` - HTML generator related things (part of CLI)
- `(frontend)` - All frontend-related actions, including commits to CLI that interact with frontend
- `(cli)` - All CLI-related stuff like argparsing, commands etc.

> [!NOTE]
> If you can't find matching scope for commit, leave it empty. Instead of prefixing commit with `fix(idkscope):`, simply use `fix:`.

3. We don't have marks for breaking changes:

```diff
- git commit -m "feat(cli)!: some very important commit"
+ git commit -m "feat(cli): some very important commit"
```

4. Under the hood we use [changelogen](https://github.com/unjs/changelogen) to generate CHANGELOG.md,
   we will have to setup github actions for every new release.

## Linting

For Rust projects, we use [following linter rules](https://github.com/glagolica/glagolica/blob/9de0b655413b33caf11ba56ce66c04115d8be7ee/Cargo.toml#L5-L24).

For TypeScript projects, we use ESLint v8 + [@vercel/style-guide](https://github.com/vercel/style-guide) with corresponding exports.
Once style-guide is updated to support ESLint v9 we will update the ESLint version as well, else we will switch to better ESLint config.
