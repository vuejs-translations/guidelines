# Vue Community Translation Guidelines

This repository is now primarily kept as a reference for existing Vue documentation translations and their maintenance workflows.

> Vue core docs are no longer accepting new translations. Existing translations that are not actively maintained may lose official `*.vuejs.org` domain support and be redirected to the English docs. For Vue ecosystem projects, see [Vue Ecosystem Translation Guidelines](README_ECOSYSTEM.md).

## Translation Policy

1. We are not accepting new translations of the Vue core docs.
2. We are not onboarding new translation repos into `vuejs-translations`, and we are not adding new translation links to `vuejs.org`.
3. Existing translations need active maintainers and reasonably timely upstream sync to keep official support.
4. If a translation is no longer actively maintained, its official domain support may be removed and redirected to the English docs.
5. Teams that still want to maintain a translation can continue doing so in their own repos, but official Vue support is limited to actively maintained translations.

## Why We Are Making This Change

This change is mainly about sustainability, not a judgment on the value of past community translations. Those translations helped many users, and we appreciate the work that went into them.

1. AI-assisted translation quality is now high enough that the benefit of maintaining a separate official translation is much smaller than it used to be.
2. For maintainers, translation is not only initial writing work. It becomes ongoing operational work: tracking upstream changes, reviewing terminology, resolving drift, and keeping versions aligned over time.
3. Vue docs evolve continuously. Once an official translation falls behind, users may reasonably assume it is current because it is on an official domain, which can create more confusion than sending them to the English docs directly.
4. Official support also creates continuing coordination cost for both translation teams and the core team: repo transfers, access management, review expectations, link curation, and domain support.
5. Given the lower ROI of manual maintenance today, we would rather avoid creating expectations that volunteer maintainers need to keep carrying a long-term sync burden just to preserve official status.

## Workflow Recommendations for Existing Translation Teams

If you are already actively maintaining a translation, the following recommendations still apply.

### Setup

Read the [Contributing Section](https://github.com/vuejs/docs#contributing) of the English docs. Make sure to use `pnpm` and Node.js v14+. Familiarize yourself with [VitePress' markdown extension features](https://vitepress.vuejs.org/guide/markdown.html).

### Use Issues and Pull Requests

It's recommended to manage the workload using issues and pull requests. Create an issue for each page that still needs translation, then let team members self-assign to claim the work. Create a pull request for the translation of each page. This way, other collaborators can review and provide feedback before the the PR is merged. It is also recommended to use "Squash and Merge" for the PRs so you have a clean history.

### Document Translation Conventions

When working as a team, make sure to use consistent translations for common terminologies to avoid confusion. It's best to have a place to document the conventions and consensus generated from reviews. You can use GitHub wiki, team discussions thread, or directly as a markdown file in the repo itself. If a term is particularly tricky to concisely translate in your language, consider leaving it untranslated.

### Translating Non-Content Text

Some text are part of the VitePress theme instead of markdown content. You can translate these in `.vitepress/config.ts`. In addition to navigation and sidebar items, you can also customize most of the theme text by providing the `themeConfig.i18n` option. [Example usage in Chinese translation](https://github.com/vuejs-translations/docs-zh-cn/blob/main/.vitepress/config.ts#L554-L588)

### Translating Images

All the images are embeded into docs with the Figma URLs set aside as code comments. You can search them out by this link:

https://github.com/search?q=repo%3Avuejs%2Fdocs%20figma&type=code

To translate the text in those images, we recommend to:

1. fork the Figma docs accordingly,
2. translate the text in Figma, and
3. export the new image.

You can add specific suffixes to the new images according to your language code. Adding the forked Figma URL in the code comment is also welcome. [Example practice in Chinese translation](https://github.com/vuejs-translations/docs-zh-cn/pull/858)

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

The lists below are kept for reference. Being listed here does not by itself guarantee continued official domain support.

- [Simplified Chinese](https://github.com/vuejs-translations/docs-zh-cn)
- [Japanese](https://github.com/vuejs-translations/docs-ja)
- [Ukrainian](https://github.com/vuejs-translations/docs-uk)
- [French](https://github.com/vuejs-translations/docs-fr)
- [Korean](https://github.com/vuejs-translations/docs-ko)
- [Portuguese](https://github.com/vuejs-translations/docs-pt)
- [Bangla](https://github.com/vuejs-translations/docs-bn)
- [Italian](https://github.com/vuejs-translations/docs-it)
- [Persian](https://github.com/vuejs-translations/docs-fa)
- [Russian](https://github.com/translation-gang/docs-ru)
- [Czech](https://github.com/vuejs-translations/docs-cs)
- [Traditional Chinese (Hong Kong)](https://github.com/vuejs-translations/docs-zh-hk)
