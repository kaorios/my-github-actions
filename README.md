# My GitHub Actions Template

## Release

Use `changesets` to create release note and a tag.
https://github.com/changesets/changesets/blob/main/docs/intro-to-using-changesets.md

1. Install `changesets`

```
npm install @changesets/cli && npx changeset init
```

2. Copy `.github/workflow/release.yml`

3. Set up Workflow permissions:

You have to configure your repository - `Settings -> Action -> General -> Workflow permissions`

- choose read and write permissions
- turn on "Allow GitHub Actions to create and approve pull requests"

Error messages:

```
fatal: unable to access 'https://github.com/suige/my-github-actions/': The requested URL returned error: 403
Error: Error: The process '/usr/bin/git' failed with exit code 128
Error: The process '/usr/bin/git' failed with exit code 128
```

```
Error: HttpError: GitHub Actions is not permitted to create or approve pull requests.
Error: GitHub Actions is not permitted to create or approve pull requests.
```
