# Vue Community Translation Guidelines

If you are here, you are likely interested in contributing to the translation of the Vue.js documentation. Thank you! Before you start, make sure to read the following guidelines to get an understanding of the workflow.

## High Level Steps of Working on a New Translation

1. Open a thread in the Discussion tab to indicate your intention of working on a translation. Make sure to check if there is already one created for your language - this can help avoid duplicated efforts. Use the thread to find fellow collaborators to form a translation team. We strongly suggest working as a team because peer reviews are necessary to ensure translation quality.

2. Fork [vuejs/docs](https://github.com/vuejs/docs) to start the translation process in your own repo (you can create a dedicated organization for it if you want). Make sure to read the [Workflow Recommendations](#workflow-recommendations) section below before you start! Feel free to deploy your own preview with Vercel or Netlify during this phase.

3. Send us a Pull Request to add your WIP repo to the end of this README file.

4. Once you have completed translation for more than 50% of the content, you can ping us in the original discussion thread to request officially transferring the repo into the `vuejs-translations` organization. We will invite you and other collaborators to the organization so you can continue working on it.

   We will also create an official deployment with `*.vuejs.org` URL (we have partnerships with hosting platforms so you don't need to bear the cost in case the traffic gets high).

   Some Notes:

   - Before performing the transfer, use the GitHub support request to [detach your fork](https://support.github.com/request/fork). This is necessary because GitHub doesn't allow multiple forks of the same source repo to co-exist in the same organization.

   - When you first transfer the repo, you likely won't have write access to it because the repo will need to be assigned to the team for proper permissions, let us know once the transfer is done so we can set it up.

   - For consistency, the team and repo names are determined based on the [ISO 639-1 language codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes).

5. Once translation is finished, Send us a Pull Request to add a link to the translation on `vuejs.org`. See [example 1](https://github.com/vuejs/docs/pull/2448) and [example 2](https://github.com/vuejs/docs/pull/2508). We will merge it and announce the translation from the official Twitter account!

## Workflow Recommendations

### Setup

Read the [Contributing Section](https://github.com/vuejs/docs#contributing) of the English docs. Make sure to use `pnpm` and Node.js v14+. Familiarize yourself with [VitePress' markdown extension features](https://vitepress.vuejs.org/guide/markdown.html).

### Use Issues and Pull Requests

It's recommended to manage the workload using issues and pull requests. Create an issue for each page that still needs translation, then let team members self-assign to claim the work. Create a pull request for the translation of each page. This way, other collaborators can review and provide feedback before the the PR is merged. It is also recommended to use "Squash and Merge" for the PRs so you have a clean history.

### Document Translation Conventions

When working as a team, make sure to use consistent translations for common terminologies to avoid confusion. It's best to have a place to document the conventions and consensus generated from reviews. You can use GitHub wiki, team discussions thread, or directly as a markdown file in the repo itself. If a term is particularly tricky to concisely translate in your language, consider leaving it untranslated.

### Translating Non-Content Text

Some text are part of the VitePress theme instead of markdown content. You can translate these in `.vitepress/config.ts`. In addition to navigation and sidebar items, you can also customize most of the theme text by providing the `themeConfig.i18n` option. [Example usage in Chinese translation](https://github.com/vuejs-translations/docs-zh-cn/blob/main/.vitepress/config.ts#L554-L588)

### Retaining Original Anchors

VitePress automatically generates header anchor links (links that start with `#`) based on the text. Since we have a lot of cross-linking to headers within the site, it is easier to retain original English header links so that you don't need to update links everywhere when you translate the headers. It also makes it easier to switch between different languages of the same header link.

We already added header anchor links in the original English document, use the following syntax when translating to retain them:

```diff
- ## Original Header {#original-header}
+ ## Translated Header {#original-header}
```

You may also notice that some headers are followed by one or two `\*` markers:

```md
### `<script setup>` \*\* {#script-setup}
```

These are custom markers we use to differentiate between Options-API-only and Composition-API-only sections. We use a custom markdown plugin to wrap these sections in additional divs that can be shown / hidden by toggling CSS classes. Please keep them when translating the headers!

### Syncing with Upstream

It is recommended to set up an automated workflow to sync with upstream updates from time to time. If you don't have an existing preferred method of doing so, we have two recommendations:

1. Use [Ryu-Cho](https://github.com/vuejs-translations/ryu-cho) to track upstream updates and automatically open issue / PRs. See [example workflow](https://github.com/vuejs-translations/docs-ja/blob/main/.github/workflows/ryu-cho.yaml) in Japanese translation.

2. Create an `upstream` branch, and use [this GitHub Action](https://github.com/TobKed/github-forks-sync-action) to sync that branch with the English docs. Periodically create PRs between `upstream` and `main` to sync the content with necessary translations. See [example config](https://github.com/vuejs-translations/docs-zh-cn/blob/main/.github/workflows/autosync.yml) in Chinese translation.

You can reach out to the respective teams in their translations repo if you have questions on how to set up syncing.

## Complete Translations (in completion order)

- [Simplified Chinese](https://github.com/vuejs-translations/docs-zh-cn)
- [Japanese](https://github.com/vuejs-translations/docs-ja)
- [Ukrainian](https://github.com/vuejs-translations/docs-uk) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/25)
- [French](https://github.com/vuejs-translations/docs-fr) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/2)
- [Korean](https://github.com/vuejs-translations/docs-ko) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/57)
- [Portuguese](https://github.com/vuejs-translations/docs-pt) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/26)
- [Bangla](https://github.com/vuejs-translations/docs-bn) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/66)

## Current Active Translations (in alphabetical order)

- [Arabic](https://github.com/Abdelaziz18003/vuejs-docs-ar) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/60)
- [Czech](https://github.com/AloisSeckar/vuejs-docs-cs) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/64)
- [German](https://github.com/roma-marshall/docs-de) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/49)
- [Italian](https://github.com/phox081/docs-it) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/23)
- [Malay](https://github.com/mujahidfa/docs-ms) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/53)
- [Persian](https://github.com/vuejs-translations/docs-fa) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/6)
- [Polish](https://github.com/WojciechSkirlo/docs) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/31)
- [Russian](https://github.com/translation-gang/docs-ru) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/12)
- [Serbian](https://github.com/vuejs-rs/docs) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/27)
- [Spanish](https://github.com/drfcozapata/docs/) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/3)
- [Uzbek](https://github.com/Zikoi5/docs-uz) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/32)
- [Vietnamese](https://github.com/vuejs-vn/docs) [(discussions)](https://github.com/vuejs-translations/guidelines/discussions/13)
