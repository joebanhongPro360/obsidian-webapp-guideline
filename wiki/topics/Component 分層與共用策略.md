---
type: topic
status: active
language: zh-TW
created: 2026-05-26
updated: 2026-05-26
source_count: 1
---

# Component 分層與共用策略

## Definition

本主題記錄 web app 開發中 component 的分層方式、共用元件查找順序，以及何時應該建立可複用元件。

## Current Guideline

- Component 分為 `base component` 與 `ui layer component`。
- `base component` 主要位於 [[web-common]]，例如 Storybook 中的共用元件。
- `ui layer component` 可從 [[web-app]] 的 `web-app/modules/components` 查找，適合大區塊、多頁複用的 UI 元件。
- 開發新元件時，優先順序應為：
  - 先查 [[web-common]] 是否已有共用元件。
  - 若沒有，再查 [[web-app]] 的 `web-app/modules/components` 是否已有可複用的 ui layer component。
  - 若不需要通用，才寫在當頁畫面直接使用。
- 若元件可能共用，應與 UI 討論是否沿用 [[web-common]] 既有設計，以增加共用性。
- Storybook 是 [[web-common]] 元件給人閱讀與溝通的文件來源。

## Rationale

- 先使用 [[web-common]] 可降低重複實作，並讓 [[web-app]] 與 [[web-front]] 共享一致的 base component。
- 先查既有 ui layer component 可避免在頁面內重複建立大區塊 UI。
- Storybook 能作為開發與 UI 討論元件設計、沿用舊設計與共用性的共同基準。

## Related Sources

- [[開發與維護 Summary]]

## Related Topics

- [[CSS 模組與 SCSS 遷移]]

## Related Entities

- [[web-common]]
- [[web-app]]
- [[web-front]]

## Open Questions

- `base component` 與 `ui layer component` 的邊界是否需要更明確的判斷表？
- 哪些元件應提升到 [[web-common]]，哪些應留在 [[web-app]]，目前尚缺正式準則。
