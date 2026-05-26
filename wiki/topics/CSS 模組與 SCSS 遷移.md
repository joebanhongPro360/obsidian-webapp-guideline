---
type: topic
status: active
language: zh-TW
created: 2026-05-26
updated: 2026-05-26
source_count: 1
---

# CSS 模組與 SCSS 遷移

## Definition

本主題記錄 web app 中 CSS 與 component 的組織方式，以及從 `stylus` 朝 `scss` 收斂的技術方向。

## Current Guideline

- 專案早期使用 `stylus`。
- 未來方向是採用 `scss`，讓 [[web-app]] 與 [[web-common]] 使用相同 CSS 套件。
- CSS 目前與 component 放在一起直接使用。
- 常見檔案搭配例子包括 `Button.js` 與 `Button.module.scss`。

## Rationale

- [[web-app]] 與 [[web-common]] 使用相同 CSS 套件可降低跨專案元件共用時的樣式落差。
- CSS 與 component 共置可讓元件結構與樣式維護位置更接近，有助於日常開發與維護。

## Related Sources

- [[開發與維護 Summary]]

## Related Topics

- [[Component 分層與共用策略]]

## Related Entities

- [[web-common]]
- [[web-app]]

## Open Questions

- `stylus` 到 `scss` 的遷移時程尚未定義。
- 舊 `stylus` 檔案是否保留、逐步轉換或集中重構，仍待補充。
- `scss` module 的命名規則與目錄規則尚未建立。
