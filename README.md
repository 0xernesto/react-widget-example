# React Widget Example

![Static Badge](https://img.shields.io/badge/license-MIT-yellow)
![GitHub Workflow Status (with event)](https://img.shields.io/github/actions/workflow/status/0xernesto/react-widget-example/ci.yml?label=tests)
[![Latest npm version](https://img.shields.io/npm/v/%400xernesto%2Freact-widget-example?logo=npm&label=latest&color=blue)](https://www.npmjs.com/package/@0xernesto/react-widget-example)
![npm](https://img.shields.io/npm/dt/%400xernesto%2Freact-widget-example?label=downloads&color=green)

## Overview

This project is an example of how to create an embeddable React widget. Technically, this is a React component library, but the only export is `MyWidget`. The output package is framework-agnostic, which means it can be used by third-party apps, regardless of the React framework they use (Create-React-App, Next.js, etc). This project was largely inspired by the [Uniswap Swap Widget](https://github.com/Uniswap/widgets).

The output package is published as [@0xernesto/react-widget-example](https://www.npmjs.com/package/@0xernesto/react-widget-example).

## Development Tools Used

-   **Language:** Typescript
-   **Bundler:** Rollup
-   **Formatter:** Prettier
-   **Linter:** ESLint
-   **Styling:** TailwindCSS
-   **Testing:** Jest

## MyWidget

`MyWidget` is a simple counter widget that consists of a container (blue outline), an "Increase count!" button, and a text element that displays the decimal and hexadecimal count.

Below is a screenshot of a Next.js 13 app that uses `MyWidget`. The red container is part of the app, and the blue container is part of the widget.

## ![nextjs_app_example](https://github.com/0xernesto/react-widget-example/blob/main/src/assets/nextjsExample.png)

### <p align="center">Figure 1: Next.js 13 app using `MyWidget`.</p>

## Contributing

-   On a new branch, open a PR for a particular set of changes.
-   Name the PR according to [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/#specification) guidelines.
-   All commits must be related to the PR name and commit messages must follow [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/#specification) guidelines.
-   To make the enforcement of these guidelines easier, husky, commitlint, commitizen, and GitHub Actions have been configured for this project.

**When making git commits, run the folowing command instead of `git commit`, and follow the instrucitons.**

```sh
npm run commit
```

## Publishing

This project is set up to publish the package via GitHub Actions, only after a new release is created.
If this is the first time the package is published, the following command should be used:

```sh
npm publish --access public
```

After the package has been published for the first time, the following is an example step-by-step process for publishing new releases. Please refer to the [npm docs](https://docs.npmjs.com/cli/v8/commands/npm-version) to better understand the `npm version` command.

**NOTE:** `NPM_TOKEN` must be obtained from your npm account and added to the repo's GitHub Actions secrets. `GITHUB_TOKEN` is a special secret that is automatically created for the repo, so there is no need to explicitely define it anywhere.

1. On your local machine, create a new local branch - for example, `fix_for_the_bug`.

```sh
git checkout -b fix_for_the_bug
```

2. Make code changes and commit as necessary.

```sh
git add -A
```

```sh
npm run commit
```

Follow the commitizen prompts, and the final commit message should be something like `fix: "fix part 1 of 5 of the bug"`

3. Push the branch to the remote GitHub repo.

```sh
git push origin fix_for_the_bug
```

4. Create a new pull request from the `fix_for_the_bug` branch, review the code, and address any changes necessary. Make sure the pull request name follows [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/#specification) guidelines.

5. After the changes have been reviewed, the PR can be merged to the main branch. This will trigger the GitHub Action workflow that publishes the new release.

The process above ensures that the code in the main branch always reflects that latest package version, and also keeps package versions consistent between npm and GitHub Packages.

## License

This project is released under the MIT License - see the [LICENSE.md](https://github.com/0xernesto/react-widget-example/blob/main/LICENSE.md) file for details.
