# Reusable WordPress Workflows

[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Support Level](https://img.shields.io/badge/support-may_take_time-yellow.svg)](#support-level)

Reusable WordPress Workflows to increase our productivity instead of deploying in the "cowboy" style through FTP.

## Check for WordPress Coding Standards

- [Check-Standards](https://github.com/sarahcssiqueira/reusable-wordpress-workflows/tree/master/check-standards)

## Deploy

- [Deploy Plugin in a LAMP server](https://github.com/sarahcssiqueira/reusable-wordpress-workflows/blob/master/deploy/deploy-plugin.yml)
- [Deploy Theme in a LAMP server](https://github.com/sarahcssiqueira/reusable-wordpress-workflows/blob/master/deploy/deploy-theme.yml)
- [Deploy Plugin in a EC2 instance](https://github.com/sarahcssiqueira/reusable-wordpress-workflows/blob/master/deploy/deploy-plugin-aws.yml)
- [Deploy Theme in a EC2 instance](https://github.com/sarahcssiqueira/reusable-wordpress-workflows/blob/master/deploy/deploy-theme-aws.yml)

## Release

- [Automatic Releases on new Tags](https://github.com/sarahcssiqueira/reusable-wordpress-workflows/blob/master/release/create-release.yml)

## Tests

[To do]

# Usage

Copy and paste the **.yml** file more suitable for your needs in the **.github/workflows** folder of your repository. If you still don't have a .github/workflows folder, create one.

Change the paths and [save the secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository) on the appropriate environment.

## Triggers

The most common trigger for the workflows on this repository is run after a push to the master branch:

```
on:
  push:
    branches: [master]
```

But as you can see, for the create [release workflow](https://github.com/sarahcssiqueira/reusable-wordpress-workflows/blob/master/release/create-release.yml), it is triggered when a tag is added to the branch.

```
on:
  push:
    tags:
      - v*
```

I would recommend using on push tag trigger for your deployments workflows too, so the deployed version of your project will always reflect the latest release of your project. For more details about Workflow triggers, please refer to [GitHub documentation](https://docs.github.com/en/actions/using-workflows/triggering-a-workflow#about-workflow-triggers).

## Environments

You can configure custom environments according to your project needs:

```
jobs:
  deploy:
    name: Deploy WordPress Theme
    runs-on: ubuntu-20.04
    environment: production
```

For more details about setting GitHub environments, please refer to [GitHub documentation](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment#about-environments)

# Contributing

Contribute to adding new workflows samples for other needs or other needs through [pull requests](https://github.com/sarahcssiqueira/reusable-wordpress-workflows/pulls), inform about [issues](https://github.com/sarahcssiqueira/reusable-wordpress-workflows/issues) or even add some improvements ideas.

# License

This repository is licensed under the [MIT](https://opensource.org/license/mit/) license.
