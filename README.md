# Hello, World! JavaScript Action

[![GitHub Super-Linter](https://github.com/jabidahscreationssystems-com/special-couscous/actions/workflows/linter.yml/badge.svg)](https://github.com/super-linter/super-linter)
![CI](https://github.com/jabidahscreationssystems-com/special-couscous/actions/workflows/ci.yml/badge.svg)

This action prints `Hello, World!` or `Hello, <who-to-greet>!` to the log. To
learn how this action was built, see
[Creating a JavaScript action](https://docs.github.com/en/actions/creating-actions/creating-a-javascript-action).

## Create Your Own Action

To create your own action, you can use this repository as a template! Just
follow the below instructions:

1. Click the **Use this template** button at the top of the repository
1. Select **Create a new repository**
1. Select an owner and name for your new repository
1. Click **Create repository**
1. Clone your new repository

> [!CAUTION]
>
> Make sure to remove or update the [`CODEOWNERS`](./CODEOWNERS) file! For
> details on how to use this file, see
> [About code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners).

## Usage

Here's an example of how to use this action in a workflow file:

```yaml
name: Example Workflow

on:
  workflow_dispatch:
    inputs:
      who-to-greet:
        description: Who to greet in the log
        required: true
        default: 'World'
        type: string

jobs:
  say-hello:
    name: Say Hello
    runs-on: ubuntu-latest

    steps:
      # Change @main to a specific commit SHA or version tag, e.g.:
      # jabidahscreationssystems-com/special-couscous@e76147da8e5c81eaf017dede5645551d4b94427b
      # jabidahscreationssystems-com/special-couscous@v1.2.3
      - name: Print to Log
        id: print-to-log
        uses: jabidahscreationssystems-com/special-couscous@main
        with:
          who-to-greet: ${{ inputs.who-to-greet }}
```

For example workflow runs, check out the
[Actions tab](https://github.com/jabidahscreationssystems-com/special-couscous/actions)!
🚀

## Inputs

| Input          | Default | Description                     |
| -------------- | ------- | ------------------------------- |
| `who-to-greet` | `World` | The name of the person to greet |

## Outputs

| Output | Description             |
| ------ | ----------------------- |
| `time` | The time we greeted you |

## Monitoring with CatLight

This repository is configured to work with
[CatLight](https://catlight.io/), a desktop build status notifier. CatLight
provides real-time notifications for GitHub Actions workflow status changes.

### Setting Up CatLight

1. Download CatLight from [catlight.io](https://catlight.io/) for Windows,
   macOS, or Linux
2. Connect your GitHub account in CatLight
3. Select this repository to monitor
4. Get instant desktop notifications when builds start, succeed, or fail

### Features

- **Desktop Notifications**: Get immediate alerts for workflow status changes
- **System Tray Icon**: Color-coded status indicator (green/yellow/red)
- **Build Dashboard**: See all action items in one prioritized view
- **Team Coordination**: Indicate when you're investigating a failed build

For more information, visit the
[CatLight GitHub Actions documentation](https://catlight.io/a/github-actions-desktop-notifications).
