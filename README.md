# Vue Community Translation Guidelines

If you are here, you are likely interested in contributing to the translation of the Vue.js documentation. Thank you! Before you start, make sure to read the following guidelines to get an understanding of the workflow.

## High Level Steps of Working on a New Translation

1. Open a thread in the Discussion tab to indicate your intention of working on a translation. Make sure to check if there is already one created for your language - this can help avoid duplicated efforts. Use the thread to find fellow collaborators to form a translation team. We strongly suggest working as a team because peer reviews are necessary to ensure translation quality.

2. Fork [vuejs/docs](https://github.com/vuejs/docs) to start the translation process in your own repo (you can create a dedicated organization for it if you want). Make sure to read the [Workflow Recommendations](#workflow-recommendations) section below before you start! Feel free to deploy your own preview with Vercel or Netlify during this phase.

3. Send us a Pull Request to add your WIP repo to the end of this README file.

4. Once you have completed translation for more than 50% of the content, you can ping us in the original discussion thread to request officially transferring the repo into the `vuejs-translations` organization. We will invite you and other collaborators to the organization so you can continue working on it (Note: when you first transfer the repo, you likely won't have write access to it because the repo will need to be assigned to the team for proper permissions, let us know once the transfer is done so we can set it up).

We will also create an official deployment under preview URL (we have partnerships with hosting platforms so you don't need to bear the cost in case the traffic gets high).

5. Once translation is finished, you can request to publish it under `*.vuejs.org` URLs. We will also add it to the list of existing translations on the English docs, and announce the translation from the official Twitter account!

## Workflow Recommendations

### Setup

Read the [Contributing Section](https://github.com/vuejs/docs#contributing) of the English docs. Make sure to use `pnpm` and Node.js v14+. Familiarize yourself with [VitePress' markdown extension features](https://vitepress.vuejs.org/guide/markdown.html).

### Use Issues and Pull Requests

It's recommended to manage the workload using issues and pull requests. Create an issue for each page that still needs translation, then let team members self-assign to claim the work. Create a pull request for the translation of each page. This way, other collaborators can review and provide feedback before the the PR is merged. It is also recommended to use "Squash and Merge" for the PRs so you have a clean history.

### Document Translation Conventions

When working as a team, make sure to use consistent translations for common terminologies to avoid confusion. It's best to have a place to document the conventions and consensus generated from reviews. You can use GitHub wiki, team discussions thread, or directly as a markdown file in the repo itself. If a term is particularly tricky to concisely translate in your language, consider leaving it untranslated.

### Translating Theme Text

Some text are part of the VitePress theme instead of markdown content. You can translate these as well by providing the `themeConfig.i18n` option in `.vitepress/config.ts`. [Example usage in Chinese translation](https://github.com/vuejs-translations/docs-zh-cn/blob/main/.vitepress/config.ts#L554-L588)

### Retaining Original Anchors

VitePress automatically generates header anchor links (links that start with `#`) based on the text. Since we have a lot of cross-linking to headers within the site, it is easier to retain original English header links so that you don't need to update links everywhere when you translate the headers. It also makes it easier to switch between different languages of the same header link.

To retain original English header link, first check the generated link in the English version (e.g. `#original-header`), then use the following syntax when translating:

```diff
- ## Originial Header
+ ## Translated Header {#original-header}
```

### Syncing with Upstream

It is recommended to set up an automated workflow to sync with upstream updates from time to time. If you don't have an existing preferred method of doing so, we have two recommendations:

1. Use [Ryu-Cho](https://github.com/vuejs-translations/ryu-cho) to track upstream updates and automatically open issue / PRs. See [example workflow](https://github.com/vuejs-translations/docs-ja/blob/main/.github/workflows/ryu-cho.yaml) in Japanese translation.

2. Create an `upstream` branch, and use [this GitHub Action](https://github.com/TobKed/github-forks-sync-action) to sync that branch with the English docs. Periodically create PRs between `upstream` and `main` to sync the content with necessary translations. See [example config](https://github.com/vuejs-translations/docs-zh-cn/blob/main/.github/workflows/autosync.yml) in Chinese translation.

You can reach out to the respective teams in their translations repo if you have questions on how to set up syncing.

## Complete Translations

- [Simplified Chinese](https://github.com/vuejs-translations/docs-zh-cn)
- [Japanese](https://github.com/vuejs-translations/docs-ja)

## Current Active Translations
