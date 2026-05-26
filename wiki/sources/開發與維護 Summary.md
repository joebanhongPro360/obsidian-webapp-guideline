---
type: source-summary
status: active
language: zh-TW
source_path: raw/sources/開發與維護.md
source_type: development-note
title: 開發與維護
author_or_origin: Ray, Vincent, Joe 討論
source_date: 2026-05-26
created: 2026-05-26
updated: 2026-05-26
---

# 開發與維護 Summary

## Source

- Path: `raw/sources/開發與維護.md`
- Type: 開發與維護討論筆記
- Author or origin: Ray, Vincent, Joe 討論
- Date: 2026-05-26

## Summary

這份筆記整理 web app 開發時的 component 分層、共用元件查找順序，以及 CSS 技術方向。Component 分為 [[Component 分層與共用策略|ui layer component 與 base component]]：base component 主要來自 [[web-common]]，並透過 Storybook 作為人可讀的元件文件；ui layer component 則可從 [[web-app]] 的 `web-app/modules/components` 查找。開發新元件時，應先查 [[web-common]] 是否已有共用元件，再查 [[web-app]] 是否已有可複用的 ui layer component；若不需要通用，才寫在當頁畫面中。

CSS 方面，專案早期使用 `stylus`，但為了讓 [[web-app]] 與 [[web-common]] 使用相同 CSS 套件，未來方向是採用 `scss`。目前 CSS 會與 component 放在一起使用，例如 `Button.js` 與 `Button.module.scss`。

## Key Points

- Component 分為 `ui layer component` 與 `base component`。
- `base component` 主要位於 [[web-common]]，並以 Storybook 作為元件文件與 UI 溝通依據。
- `ui layer component` 可從 [[web-app]] 的 `web-app/modules/components` 查找，適合大區塊多頁複用的 UI 元件。
- 新增元件時的優先順序是：先查 [[web-common]]，再查 [[web-app]] 的 ui layer component，最後才寫成當頁專用元件。
- [[web-common]] 使用於 [[web-app]] 與 [[web-front]]。
- [[CSS 模組與 SCSS 遷移|CSS 技術方向]] 是從早期 `stylus` 朝 `scss` 收斂。
- CSS 目前與 component 共置，例如 `Button.js` 搭配 `Button.module.scss`。

## Relevant Topics

- [[Component 分層與共用策略]]
- [[CSS 模組與 SCSS 遷移]]

## Relevant Entities

- [[web-common]]
- [[web-app]]
- [[web-front]]

## Claims And Evidence

- Claim: 元件開發應優先使用 [[web-common]] 既有共用元件。
  - Evidence: 來源指出「先從 web-common 內看有沒有共用，有的話先拿出來用」。
  - Source reference: `raw/sources/開發與維護.md`
- Claim: 若 [[web-common]] 沒有可用元件，下一步應查 [[web-app]] 的 `web-app/modules/components`。
  - Evidence: 來源指出「如果 web-common 沒有的話，可以從 web-app/modules/components 查找有沒有 ui layer component」。
  - Source reference: `raw/sources/開發與維護.md`
- Claim: Storybook 是 [[web-common]] 元件文件，也是與 UI 溝通設計沿用與共用性的依據。
  - Evidence: 來源指出 `web-common` 人看的話先讀 Storybook，且 Storybook 主要是與 UI 溝通可以讀的文件。
  - Source reference: `raw/sources/開發與維護.md`
- Claim: CSS 技術方向是從 `stylus` 逐步轉向 `scss`。
  - Evidence: 來源指出早期使用 `stylus`，未來為了讓 [[web-app]] 與 [[web-common]] 使用相同 CSS 套件而採用 `scss`。
  - Source reference: `raw/sources/開發與維護.md`

## Open Questions

- [[web-front]] 在此 guideline 中的職責目前只知道是 [[web-common]] 的使用專案之一，尚未有更完整描述。
- `ButtonV2.jsx` 與 `menu` 目前僅作為例子，是否需要建立元件清單或命名規範仍待後續來源補充。
- `stylus` 到 `scss` 的遷移範圍、時程與相容策略尚未定義。

## Links

- Topics: [[Component 分層與共用策略]], [[CSS 模組與 SCSS 遷移]]
- Entities: [[web-common]], [[web-app]], [[web-front]]
- Syntheses:
