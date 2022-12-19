# Vue 커뮤니티 번역 지침

여기 계신 분들은 Vue.js 문서 번역에 관심이 있을 것입니다. 감사해요! 시작하기 전에 워크플로를 이해하려면 다음 지침을 반드시 읽으십시오.

## 새로운 번역 작업의 고급 단계

1. [토론] 탭에서 스레드를 열어 번역 작업에 대한 의도를 나타냅니다. 해당 언어에 대해 이미 만들어진 언어가 있는지 확인하십시오. 이렇게 하면 중복되는 작업을 피할 수 있습니다. 스레드를 사용하여 번역 팀을 구성할 동료 공동작업자를 찾습니다. 번역 품질을 보장하기 위해서는 동료 검토가 필요하기 때문에 우리는 팀으로 일하는 것을 강력하게 제안합니다.

2. [vuejs/https](https://github.com/vuejs/docs)를 클릭하여 자신의 레포에서 번역 프로세스를 시작합니다(원하는 경우 전용 조직을 만들 수 있음). 시작하기 전에 아래의 [워크플로우 권장사항](#워크플로우 권장사항) 섹션을 반드시 읽어보십시오! 이 단계에서 Vercel 또는 Netlify를 사용하여 원하는 미리 보기를 배포하십시오.

3. 이 README 파일의 끝에 WIP 레포를 추가하려면 풀 요청을 보내 주십시오.

4. 내용의 50% 이상 번역을 마치면 원래 토론 스레드에서 ping을 실행하여 repo를 vuejs-translations 조직으로 정식 이관할 것을 요청할 수 있습니다. 계속 작업할 수 있도록 사용자와 다른 공동작업자를 조직으로 초대합니다.

  우리는 또한 "*.vuejs.org" URL로 공식 배포를 만들 것입니다(우리는 호스팅 플랫폼과 파트너십을 맺고 있기 때문에 트래픽이 많아질 경우 비용을 부담할 필요가 없습니다).

  일부 참고 사항:

  - 전송을 수행하기 전에 GitHub 지원 요청을 사용하여 [포크 다운로드](https://support.github.com/request/fork)를 참조하십시오. GitHub에서는 동일한 소스 레포의 여러 포크가 동일한 조직에 공존할 수 없기 때문에 필요합니다.

  - 레포를 처음 전송할 때 적절한 권한을 얻으려면 팀에 레포를 할당해야 하므로 레포에 대한 쓰기 액세스 권한이 없을 수 있습니다. 전송이 완료되면 알려주시면 설정할 수 있습니다.

  - 일관성을 위해 [ISO 639-1 언어 코드](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)에 따라 팀과 이름을 결정합니다.

5. 번역이 완료되면 'vuejs.org'에서 WIP에서 완성된 언어로 옮기고, 공식 트위터 계정에서 번역을 공지할 예정입니다!

## 워크플로 권장 사항

### 설정

영문 문서의 [기여 섹션](https://github.com/vuejs/docs#contributing)을 참조하십시오. pnpm과 Node.js v14+를 사용해야 합니다. [VitePress의 마크다운 확장 기능](https://vitepress.vuejs.org/guide/markdown.html)을 숙지하십시오.

### 문제 사용 및 풀 요청

문제 및 풀 요청을 사용하여 워크로드를 관리하는 것이 좋습니다. 각 페이지에 대해 여전히 번역이 필요한 이슈를 작성한 후 팀 구성원이 자체적으로 작업을 할당하도록 합니다. 각 페이지의 번역에 대한 풀 요청을 작성합니다. 이렇게 하면 다른 공동작업자가 PR이 병합되기 전에 검토하고 피드백을 제공할 수 있습니다. 또한 PR에 "스쿼시 및 병합"을 사용하는 것이 좋습니다. 그러면 기록이 깨끗해집니다.

### 문서 변환 규칙

팀으로 작업할 때는 혼동을 피하기 위해 공통 용어에 일관된 번역을 사용해야 합니다. 리뷰를 통해 생성된 컨벤션과 합의를 문서화할 수 있는 곳이 가장 좋습니다. GitHub Wiki, 팀 토론 스레드 또는 레포 자체의 마크다운 파일로 직접 사용할 수 있습니다. 만약 어떤 용어가 당신의 언어로 간결하게 번역하기가 특히 어렵다면, 그것을 번역하지 않은 채로 두는 것을 고려해보세요.

### 내용이 아닌 텍스트 변환

Some text are part of the VitePress theme instead of markdown content. You can translate these in `.vitepress/config.ts`. In addition to navigation and sidebar items, you can also customize most of the theme text by providing the `themeConfig.i18n` option. [Example usage in Chinese translation](https://github.com/vuejs-translations/docs-zh-cn/blob/main/.vitepress/config.ts#L554-L588)

### 원래 앵커 유지

VitePress는 텍스트를 기반으로 헤더 앵커 링크('#'로 시작하는 링크)를 자동으로 생성합니다. 사이트 내에 헤더에 대한 교차 링크가 많기 때문에 헤더를 번역할 때 모든 곳의 링크를 업데이트할 필요가 없도록 원본 영어 헤더 링크를 유지하는 것이 더 쉽습니다. 또한 동일한 헤더 링크의 다른 언어 간에 쉽게 전환할 수 있습니다.

우리는 이미 원본 영어 문서에 헤더 앵커 링크를 추가했고, 그것들을 유지하기 위해 번역할 때 다음 구문을 사용한다:

```diff
- ## Originial Header {#original-header}
+ ## Translated Header {#original-header}
```

### 업스트림과 동기화

업스트림 업데이트와 수시로 동기화되도록 자동화된 워크플로우를 설정하는 것이 좋습니다. 기존에 선호하는 방법이 없는 경우 두 가지 권장 사항이 있습니다.:

1. [Ryu-Cho](https://github.com/vuejs-translations/ryu-cho)를 사용하여 업스트림 업데이트를 추적하고 자동으로 이슈 / PR을 엽니다. 일본어 번역은 [[https://github.com/vuejs-translations/docs-ja/blob/main/.github/https/https-cho.html](https://github.com/vuejs-translations/docs-ja/blob/main/.github/workflows/ryu-cho.yaml)] 을 참조하십시오.

2. 'bunch' 분기를 만들고 [this GitHub Action](https://github.com/TobKed/github-forks-sync-action)을 사용하여 해당 분기를 영어 문서와 동기화합니다. 'upstream'과 'main' 사이에 PR을 주기적으로 생성하여 필요한 번역과 내용을 동기화합니다. 중국어 번역에서는 [https://github.com/vuejs-translations/docs-zh-cn/blob/main/.github/sync/autosync.yml] 을 참조하십시오.

동기화 설정 방법에 대해 궁금한 점이 있으면 번역 보고서의 각 팀에 문의할 수 있습니다.

## 완전한 번역

- [간체 중국어] (https://github.com/vuejs-translations/docs-zh-cn)
- [일본어](https://github.com/vuejs-translations/docs-ja)

## Current Active Translations

- [프랑스어](https://github.com/vuejs-translations/docs-fr) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/2)
- [폴란드어](https://github.com/WojciechSkirlo/docs) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/31)
- [포르투갈어](https://github.com/nazarepiedady/vue3-docs-pt) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/26)
- [세르비아어](https://github.com/vuejs-rs/docs) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/27)
- [스페인어](https://github.com/drfcozapata/docs/) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/3)
- [터키어](https://github.com/ssibrahimbas/vue-docs-tr) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/30)
- [우크라이나어](https://github.com/vuejs-translations/docs-uk) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/25)
- [우즈베키스탄어](https://github.com/Zikoi5/docs-uz) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/32)
- [베트남어](https://github.com/vuejs-vn/docs) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/13)
- [독일어](https://github.com/roma-marshall/docs-de) [(논의)](https://github.com/vuejs-translations/guidelines/discussions/49)
