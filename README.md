# My GitHub Actions Template

## Create Release workflow

Use `changesets` to create release note and a tag.
[What is the changesets?](https://github.com/changesets/changesets/blob/main/docs/intro-to-using-changesets.md)

1. Install `changesets`

```
npm install @changesets/cli && npx changeset init
```

2. Copy `.github/workflow/release.yml`

3. Create Personal Account Token (GitHub)

[GitHub Documents](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

permissions:

- Actions: read-only
- contents: read and write
- pull request: read and write

4. Set this token as secret variable (GitHub)

You have to set it up on - `Settings -> Secrets and variables -> Actions -> Create repository secrets`

You can set a name if you want and update `PATNAME` on release.yml

### If you want to run with github-actions bot...

Set up Workflow permissions on GitHub:

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

> Events done by the bot can NOT be used as triggers. (2023.07.10)

## Deployment with Amplify hosting

1. Copy `.github/workflow/deployment.yml`

On AWS Amplify, Disable automatic builds and create webhook:

2. Go to `App settings -> general` and disable automatic builds there. (AWS Amplify)

3. Go to `App settings -> Build Settings` and create a web hook (AWS Amplify)

4. Save the URL in GitHub as a secret (GitHub)

You can set a name if you want and update `WEBHOOK_URL` on deployment.yml
