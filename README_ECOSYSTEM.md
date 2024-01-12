# Vue Ecosystem Translation Guidelines

_THIS IS A DRAFT YET._

Here are the guidelines for translating docs in Vue ecosystem, including official libraries like Pinia, Vue Router, etc.

## Concepts

1. **Language**: Every project might have English docs by default. And it's welcome to add docs in other languages. Usually, they are the translations of the English docs.
    - **Language List UI**: It's a menu list for all the available languages on the doc site. It's helpful for users to switch the docs to their prefered language.
2. **Checkpoint**: Since the English docs are keep updating. It's very important for other language docs to have some "checkpoints". A checkpoint is the hash and date of the latest commit when you update the translation. It's crucial for long-term maintenance since all the further translation sync-ups are based on their previous checkpoints.
3. **Translation Status**: It's the checkpoints information for all the languages that we have translated.
    - **Translation Status UI**: It's a block of UI displaying the _Translation Status_. Usually, it's the date of the latest update for the current language. It's helpful for users to know how fresh the current translation is. Also, it's an invisible encouragement for users to contribute the translations when they find anything outdated.

## High Level Steps

If you want to start translating the docs in a new language:

1. Set up the new language in the repo
2. Translate all the content into the new language
3. Initialize the checkpoint information into the _Translation Status_
4. Commit all the changes

If you want to keep a translation up-to-date:

1. Compare the English docs between the latest one and the one on the current language checkpoint.
2. Create a git branch and update the translation according to the compare result.
3. Update the current langauge checkpoint.
4. Commit all the changes

## Some practical advice

_Here is some practical advice for the translation. However, when you contribute, please do follow the guidelines of the project for more details._

Usually, the docs of a project is a sub-package based on VitePress in their repo/workspace. So this part is all based on VitePress.

To translate the docs, you have 2 options to follow:

### Translate in the official repo

1. You can add a locale information in the VitePress config.
2. You can translate all the menu items and navigation items in the new locale of the VitePress config.
3. You can translate all the i18n info in the new locale of the VitePress config.
4. The content can be translated and put into a `<lang>` sub-folder.

In this way above, you will get the translation in the _same_ doc site with:
- A new link to your translation in the _Language List UI_
- A sub-path for your translation. (e.g. in Vue Router docs https://router.vuejs.org/, the URL of the Chinese translation is https://router.vuejs.org/zh/)

_For better doing that, we have prepared a project named [`vitepress-translation-helper`](https://github.com/vuejs-translations/vitepress-translation-helper) to help you. See more usage details on its README._

### Self-host the translation

1. You can translate all the menu items and navigation items directly in the VitePress config.
2. You can translate all the i18n info directly in the VitePress config.
3. You can translate all the content directly.
4. You need to self-host your doc site with necessarily config change like the domain, the deployment config, etc.
5. You are highly encouraged to create a pull request to the official doc site to add a new link to your translation doc site in the _Language List UI_.

In this way above, you will get the translation in your own host.

### For Right-to-Left language

See more information on the [VitePress Internationalization](https://vitepress.dev/guide/i18n#rtl-support-experimental) page.

Also, in VitePress v1.0.0-rc35 and above, it supports `dir` field in frontmatter for each page.

## Current official libraries to translate their docs

- [Vue Router](https://router.vuejs.org/) ([GitHub repo](https://github.com/vuejs/router)) ([translation guidelines](https://github.com/vuejs/router/blob/main/.github/contributing.md#contributing-docs))
- [Pinia](https://pinia.vuejs.org/) ([GitHub repo](https://github.com/vuejs/pinia)) (translation guidelines under preparation)
- [Vue Test Utils](https://test-utils.vuejs.org/) ([GitHub repo](https://github.com/vuejs/test-utils/)) (translation guidelines under preparation)
- [Vue 3 Migration Guide](https://v3-migration.vuejs.org/) ([GitHub repo](https://github.com/vuejs/v3-migration-guide)) (translation guidelines under preparation)

## Other Vue ecosystem projects

_If you have a project would like to show and call for translations, feel free to add it here and create a pull request._
