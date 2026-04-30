# Vue Ecosystem Translation Guidelines

This document is now primarily kept as a reference for existing translation efforts in the Vue ecosystem, including official libraries like Pinia, Vue Router, and others.

> Vue ecosystem projects are likewise not accepting new translations through this repository. Official links or domains should only point to translations that have active maintainers and regular upstream sync. When a translation is no longer actively maintained, projects should prefer directing users to the English docs.

## Translation Policy

1. Do not use this guide as a request channel for starting a new official translation.
2. Keep official translation links only for locales that still have active maintainers.
3. When a translation stops being actively maintained, prefer removing official support and directing users back to the English docs.
4. The rest of this document is historical and practical reference material for teams that still maintain an existing translation or self-host one independently.

## Why We Are Making This Change

This change is mainly about sustainability, not a dismissal of previous translation efforts. Community translations have been valuable, but the tradeoffs are different now.

1. AI-assisted translation quality is now good enough that the incremental benefit of maintaining many separate official translations is much lower than before.
2. For project maintainers, supporting an official translation means ongoing coordination work, not just accepting an initial contribution: keeping checkpoints current, reviewing terminology, and tracking upstream changes release after release.
3. Ecosystem docs also move quickly. When an official translation becomes stale, users may still treat it as current because it appears in official navigation, which makes version skew harder to notice.
4. Maintaining official links and domains for inactive translations creates management overhead that is difficult to justify when the English docs are the most reliable source of truth.
5. Projects should still support active translation teams where that is clearly sustainable, but they should not feel obligated to keep official support for translations that no longer have maintainers.

## Concepts

1. **Language**: Every project has English docs by default. Some projects may also keep docs in other languages when there is an active team maintaining them.
    - **Language List UI**: It's a menu list for all the available languages on the doc site. It's helpful for users to switch the docs to their prefered language.
2. **Checkpoint**: Since the English docs are keep updating. It's very important for other language docs to have some "checkpoints". A checkpoint is the hash and date of the latest commit when you update the translation. It's crucial for long-term maintenance since all the further translation sync-ups are based on their previous checkpoints.
3. **Translation Status**: It's the checkpoints information for all the languages that we have translated.
    - **Translation Status UI**: It's a block of UI displaying the _Translation Status_. Usually, it's the date of the latest update for the current language. It's helpful for users to know how fresh the current translation is. Also, it's an invisible encouragement for users to contribute the translations when they find anything outdated.

## High Level Steps for Existing Translation Teams

If you want to keep a translation up-to-date:

1. Compare the English docs between the latest one and the one on the current language checkpoint.
2. Create a git branch and update the translation according to the compare result.
3. Update the current langauge checkpoint.
4. Commit all the changes

The typical workflow is like this:

![typical translation workflow](./assets/ecosystem-workflow.svg)

## Some practical advice

_Here is some practical advice for teams maintaining an existing translation. However, please do follow the guidelines of the project for more details._

Usually, the docs of a project is a sub-package based on VitePress in their repo/workspace. So this part is all based on VitePress.

Projects that still maintain translations typically use one of these 2 setups:

### Maintain a translation in the official repo

This only makes sense when the project already supports that locale and has active maintainers.

1. Keep the locale information in the VitePress config up to date.
2. Translate the menu items and navigation items for that locale in the VitePress config.
3. Translate the i18n info for that locale in the VitePress config.
4. Keep the translated content in its `<lang>` sub-folder.

In this setup, the translation lives in the _same_ doc site with:
- A link in the _Language List UI_
- A sub-path for the translation. (e.g. in Vue Router docs https://router.vuejs.org/, the URL of the Chinese translation is https://router.vuejs.org/zh/)

_For better doing that, we have prepared a project named [`vitepress-translation-helper`](https://github.com/vuejs-translations/vitepress-translation-helper) to help you. See more usage details on its README._

![typical translation workflow for regular update](./assets/ecosystem-workflow-update.svg)

### Self-host a translation

1. You can translate all the menu items and navigation items directly in the VitePress config.
2. You can translate all the i18n info directly in the VitePress config.
3. You can translate all the content directly.
4. You need to self-host your doc site with necessarily config change like the domain, the deployment config, etc.
5. Only add a link from the official doc site if the project team explicitly agrees to support it. Otherwise, keep the translation independent.

In this setup, the translation lives on your own host.

### For Right-to-Left language

See more information on the [VitePress Internationalization](https://vitepress.dev/guide/i18n#rtl-support-experimental) page.

Also, in VitePress v1.0.0-rc35 and above, it supports `dir` field in frontmatter for each page.

## Project-specific docs repositories

- [Vue Router](https://router.vuejs.org/) ([GitHub repo](https://github.com/vuejs/router)) ([translation guidelines](https://github.com/vuejs/router/blob/main/.github/contributing.md#contributing-docs))
- [Pinia](https://pinia.vuejs.org/) ([GitHub repo](https://github.com/vuejs/pinia)) ([translation guidelines](https://github.com/vuejs/pinia/blob/v2/.github/CONTRIBUTING.md#contributing-docs))
- [Vue Test Utils](https://test-utils.vuejs.org/) ([GitHub repo](https://github.com/vuejs/test-utils/))
- [Vue 3 Migration Guide](https://v3-migration.vuejs.org/) ([GitHub repo](https://github.com/vuejs/v3-migration-guide))

## Other Vue ecosystem projects

_Historically, this section collected projects looking for translations. We are no longer collecting new requests here._
